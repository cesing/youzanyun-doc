# 个人敏感信息加解密指南

> 来源：[数据加密方案简介](https://doc.youzanyun.com/resource/doc/3020)、[基于 API 解密](https://doc.youzanyun.com/resource/doc/8730)

## 背景

有赞云对订单中的**手机号、身份证、银行卡号、收货人信息**等敏感字段默认返回**密文**，以保护消费者隐私。开发者必须在自己的数据库中以**密文方式存储**，使用时再解密。

> 💡 **密钥是店铺维度的**，即每个店铺的数据使用不同密钥加密。存储密文时必须同时记录店铺 ID。

---

## 一、加解密 API 清单

| API | 作用 | 备注 |
|-----|------|------|
| `youzan.cloud.secret.encrypt.single.1.0.0` | 单项加密 | 若已是密文则直接返回 |
| `youzan.cloud.secret.encrypt.batch.1.0.0` | 批量加密 | 批量处理 |
| `youzan.cloud.secret.decrypt.single.1.0.0` | 单项解密 | 若已是明文则直接返回 |
| `youzan.cloud.secret.decrypt.batch.1.0.0` | 批量解密 | 批量处理 |
| `youzan.cloud.secret.verify.isencrypt.1.0.0` | 判断是否密文 | 返回 true/false |
| `youzan.cloud.secret.verify.isencryptlist.1.0.0` | 批量判断是否密文 | 全部密文返回 true |
| `youzan.cloud.secret.decryptmask.single.1.0.0` | 解密并脱敏 | 解密后手机号显示 138****8000 |
| `youzan.cloud.secret.decryptmask.batch.1.0.0` | 批量解密并脱敏 | 批量处理 |
| `youzan.cloud.secret.encryptsearch.digest.1.0.0` | 生成密文检索摘要 | 支持模糊匹配 |
| `youzan.cloud.secret.encryptsearch.batchdigest.1.0.0` | 批量生成检索摘要 | 批量处理 |

完整接口文档：[加解密 API 列表](https://doc.youzanyun.com/list/API/1308)

---

## 二、解密示例

### 单项解密

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.secret.decrypt.single/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -d '{
    "encrypt_data": "ENCRYPTED_DATA_PLACEHOLDER"
  }'
```

**响应：**
```json
{
  "response": {
    "decrypt_data": "13800138000"
  }
}
```

### 批量解密

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.secret.decrypt.batch/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -d '{
    "encrypt_list": [
      {"encrypt_data": "密文1", "kdt_id": 123456},
      {"encrypt_data": "密文2", "kdt_id": 123456}
    ]
  }'
```

---

## 三、加密示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.secret.encrypt.single/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -d '{
    "raw_data": "13800138000"
  }'
```

**响应：**
```json
{
  "response": {
    "encrypt_data": "OaF/xZqb0f8..."
  }
}
```

---

## 四、密文检索（按手机号搜索订单）

**问题**：密文无法直接用 SQL `LIKE` 查询。

**解决方案**：使用**密文检索摘要**（应用维度，相同应用+相同明文 → 相同摘要）

### 存储时：生成摘要

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.secret.encryptsearch.digest/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -d '{
    "raw_data": "13800138000"
  }'
# 返回摘要，存入数据库字段 mobile_encrypt_digest
```

### 查询时：模糊匹配

```sql
SELECT * FROM orders
WHERE mobile_encrypt_digest LIKE '%DIGEST_PART%';
-- 只需截取摘要的部分字符即可模糊匹配
```

> ⚠️ 摘要长度约为明文的 6 倍，请合理评估数据库字段长度。

---

## 五、注意事项

1. **SDK（即将下线）**：2024-10-01 后创建的应用不允许使用 Java SDK，优先使用 API 方式
2. **密钥不可自行管理**：密钥由有赞云统一管理，不可持久化到本地
3. **解密需申请权限**：在控制台申请解密权限，仅限合理需求场景
4. **日志监控**：解密操作会被记录，异常调用将被监控处理

---

## 六、常见问题

**Q：不同店铺的相同手机号，密文相同吗？**
> 不同店铺密钥不同，密文也不同。存储时必须记录 `kdt_id`（店铺 ID）。

**Q：如何判断一个字段是否是密文？**
> 使用 `youzan.cloud.secret.verify.isencrypt` 接口。

**Q：历史明文数据如何处理？**
> 参考 [存量应用改造指南](https://doc.youzanyun.com/resource/doc/3021)，在规定时间内完成密文存储改造。
