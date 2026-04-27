---
apiName: "youzan.pay.user.query.IdCertExist.1.0.3"
version: "1.0.3"
appName: "pay-gateway"
apiGroup: "大客CRM"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3258"
---

# youzan.pay.user.query.IdCertExist.1.0.3

> **所属分组**: 大客CRM

---

## 1. 场景说明

提供查询会员是否完成实名认证接口。
输入有赞openId，返回的data中pass为true代表已完成实名认证。
返回的data中pass为false代表未完成实名认证。
bizSuccess代表业务请求是否成功


---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.pay.user.query.IdCertExist/1.0.3`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.pay.user.query.IdCertExist/1.0.3' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.pay.user.query.IdCertExist/1.0.3"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3258)*