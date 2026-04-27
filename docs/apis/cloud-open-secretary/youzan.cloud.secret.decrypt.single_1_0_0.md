---
apiName: "youzan.cloud.secret.decrypt.single.1.0.0"
version: "1.0.0"
appName: "cloud-open-secretary"
apiGroup: "其它"
method: "singleDecrypt"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2630"
---

# youzan.cloud.secret.decrypt.single.1.0.0

> **所属分组**: 其它  **所属应用**: cloud-open-secretary

---

## 1. 场景说明

单项解密接口,请务必保证调用解密接口token的clientId(应用id)+kdtId(店铺id) 和 加密时token的保持一致,例如 加密时 使用应用A + 店铺A 生成token请求订单接口,订单接口响应加密的手机号,则解密时也要用应用A + 店铺A 来生成 token解密

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cloud.secret.decrypt.single/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.secret.decrypt.single/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cloud.secret.decrypt.single/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2630)*