---
apiName: "youzan.cardvoucher.giftcard.invalid.card.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4030"
---

# youzan.cardvoucher.giftcard.invalid.card.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

失效礼品卡的电子卡，仅激活之前的卡可进行失效

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.invalid.card/1.0.0`

**认证方式**: 凭证式

**请求参数**（2 个）:

```json
{
  "type": "object",
  "properties": {
    "operator_open_id": {
      "type": "java.lang.Long",
      "description": "操作人",
      "example": "xvJrRKC0702883114891939840"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "电子卡号",
      "example": "310200549496389"
    }
  },
  "required": [
    "operator_open_id",
    "card_no"
  ]
}
```

**响应参数**（7 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.InvalidCardResultDTO",
      "description": "",
      "example": ""
    },
    "invalid_result": {
      "type": "java.lang.Boolean",
      "description": "失效结果，true 成功，false失败",
      "example": "true"
    },
    "success": {
      "type": "boolean",
      "description": "是否请求成功",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "",
      "example": ""
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "",
      "example": ""
    },
    "error_data": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "",
      "example": ""
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "invalid_result": "true",
  "success": "true",
  "code": "200",
  "message": "",
  "request_id": "",
  "error_data": ""
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.invalid.card/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.invalid.card/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4030)*