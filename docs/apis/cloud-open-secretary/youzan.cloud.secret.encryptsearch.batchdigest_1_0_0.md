---
apiName: "youzan.cloud.secret.encryptsearch.batchdigest.1.0.0"
version: "1.0.0"
appName: "cloud-open-secretary"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4668"
---

# youzan.cloud.secret.encryptsearch.batchdigest.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

批量生成密文检索摘要，用来在加密场景下提供检索能力，支持模糊搜索和精确搜索；
参数可以是密文和明文，单次请求最多200个；如果参数是密文，有赞将解密成明文后生成检索摘要。摘要长度是明文的6倍；
场景案例：用户根据手机号搜索历史订单，应用拿到搜索关键字（手机号）请求有赞接口获取检索摘要，之后根据摘要在数据库存量摘要中搜索

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cloud.secret.encryptsearch.batchdigest/1.0.0`

**认证方式**: 凭证式

**请求参数**（0 个）:

```json
{
  "type": "object",
  "properties": {},
  "required": []
}
```

**响应参数**（0 个）:

```json
{
  "type": "object",
  "properties": {}
}
```

**成功响应示例**:

```json
{}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.secret.encryptsearch.batchdigest/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cloud.secret.encryptsearch.batchdigest/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4668)*