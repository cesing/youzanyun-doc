---
apiName: "youzan.pay.customs.declaration.reportpayment.report.1.0.2"
version: "1.0.2"
appName: "pay-gateway"
apiGroup: "跨境报关"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4557"
---

# youzan.pay.customs.declaration.reportpayment.report.1.0.2

> **所属分组**: 跨境报关

---

## 1. 场景说明

支付跨境报关接口

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.pay.customs.declaration.reportpayment.report/1.0.2`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.pay.customs.declaration.reportpayment.report/1.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.pay.customs.declaration.reportpayment.report/1.0.2"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4557)*