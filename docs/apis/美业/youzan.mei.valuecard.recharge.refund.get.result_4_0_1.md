---
apiName: "youzan.mei.valuecard.recharge.refund.get.result.4.0.1"
version: "4.0.1"
appName: "mei-open"
apiGroup: "美业"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3813"
---

# youzan.mei.valuecard.recharge.refund.get.result.4.0.1

> **所属分组**: 美业

---

## 1. 场景说明

用于根据充值订单号或退款单号查询退款结果，退款成功后（youzan.mei.valuecard.recharge.refund.operate），可再次通过此接口退款结果

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.refund.get.result/4.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.refund.get.result/4.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.refund.get.result/4.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3813)*