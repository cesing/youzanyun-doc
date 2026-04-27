# 新手指南

本文档面向**首次入驻有赞云的开发者**，说明从注册到调通第一个接口的完整流程。

## 开发前准备

### 1. 注册与认证

**步骤 1：注册账号**
1. 进入 [有赞云官网](https://open.youzanyun.com)，点击右上角**控制台**
2. 点击右下角**注册账号**，填写手机号等信息
3. 进入邮箱激活账号（邮件 15 分钟内有效）

> ⚠️ 注册手机号即为开发者账号，具有最高权限且不可更改。请谨慎选择。

**步骤 2：创建团队**
注册成功后需创建团队（可创建多个），用于管理成员、应用和费用。

**步骤 3：实名认证**
- 团队创建完成后需进行实名认证，才可创建应用
- 支持**个人认证**和**企业认证**，企业开发者请使用企业身份
- 认证审核时间：1 个工作日

---

### 2. 创建应用

有赞云应用按两个维度分类：

| 维度 | 类型 | 说明 |
|------|------|------|
| **用途** | 自用型 | 商家自研，将有赞数据对接自己的系统 |
| **部署** | 工具型 | 上架应用市场，为第三方商家提供服务 |
| **部署** | 有容器型 | 部署在有赞云服务器，支持后端扩展点 |
| **部署** | 无容器型 | 部署在自己的服务器，通过 HTTP 调用 |

**接入流程：**

```
自用型应用：
  注册账号 → 创建团队 → 实名认证 → 创建应用 → 开发调试 → 店铺授权

工具型应用：
  注册账号 → 创建团队 → 实名认证 → 创建应用 → 开发调试 → 上架应用市场 → 商家订购授权
```

具体操作步骤：
- [无容器接入流程](https://doc.youzanyun.com/resource/doc/3010)
- [有容器接入流程](https://doc.youzanyun.com/resource/doc/3014)

---

### 3. 获取 Access Token

调用任何 API 都需要有效的 `access_token`，获取方式：

```
1. 商家授权：用户访问授权链接 → 商家确认授权 → 获取 code → 用 code 换取 token
2. 自用型：控制台获取固定 token（适合测试）
```

**授权 URL 格式：**
```
https://open.youzanyun.com/oauth/authorize?client_id={app_id}&response_type=code&redirect_uri={回调地址}
```

**换取 Token：**
```bash
curl -X POST 'https://open.youzanyun.com/oauth/token' \
  -d 'client_id={app_id}' \
  -d 'client_secret={app_secret}' \
  -d 'grant_type=authorization_code' \
  -d 'code={code}'
```

---

### 4. 调通第一个接口

以查询店铺信息为例：

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.shop.basic/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{
    "fields": ["shop_id", "name", "logo"]
  }'
```

**响应示例：**
```json
{
  "response": {
    "shop_id": 123456,
    "name": "我的有赞店铺",
    "logo": "https://img.yzcdn.cn/..."
  }
}
```

**常见错误：**

| 错误码 | 说明 | 解决方法 |
|--------|------|----------|
| 10003 | access_token 过期或无效 | 重新获取 Token |
| 10004 | 无权限调用此接口 | 在控制台申请该接口权限 |
| 20001 | 调用频率超限 | 降低调用频率或购买套餐 |
| 20002 | 接口配额已用完 | 升级 API 套餐 |

---

### 5. 敏感数据处理

有赞云对订单中的**手机号、身份证、银行卡号**等敏感字段默认返回**密文**。

**解密流程：**
```bash
# 1. 调用解密接口
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.secret.decrypt.single/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -d '{"encrypt_data": "OaF/xZqb0f..."}'

# 2. 获取明文
# 响应: {"decrypt_data": "13800138000"}
```

> 💡 **密钥是店铺维度的**，存储密文时必须同时记录所属店铺 ID，否则无法解密。

详细说明：[个人敏感信息加解密指南](https://doc.youzanyun.com/resource/doc/3020)

---

### 6. 测试店铺

开发者可在控制台申请**免费测试店铺**，无需真实商家授权即可调通所有接口。

申请路径：控制台 → 工具 → 测试店铺

---

## 后续步骤

- 📖 [查看 API 文档](https://github.com/cesing/youzanyun-doc/tree/main/docs/apis)，按业务场景找到所需接口
- 💰 [了解 API 计费规则](pricing.md)，选择合适的套餐
- 🐛 [提交工单咨询](https://help.youzanyun.com/workorder/mine/work)，遇到问题联系技术支持
