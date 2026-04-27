---
apiName: "youzan.cardvoucher.giftcard.amount.query.3.0.0"
version: "3.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "queryGiftCardAmout"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/418"
---

# youzan.cardvoucher.giftcard.amount.query.3.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

根据店铺id查询该店铺下礼品卡的激活总数、激活金额总数、激活未使用的金额总数

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.amount.query/3.0.0`

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "com.youzan.pay.cardvoucher.biz.api.giftcard.request.QueryGiftCardAmountRequest",
      "description": "",
      "example": ""
    },
    "search_kdt_id": {
      "type": "java.lang.Long",
      "description": "查询店铺id，非必传，为了以后兼容",
      "example": "491491"
    },
    "card_type": {
      "type": "int",
      "description": "卡类型（101：礼品卡）",
      "example": "101"
    }
  },
  "required": [
    "request",
    "card_type"
  ]
}
```

**响应参数**（9 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.giftcard.response.GiftCardAmoutDTO",
      "description": "",
      "example": ""
    },
    "card_active_total": {
      "type": "long",
      "description": "卡激活的数量",
      "example": "10"
    },
    "card_active_amout": {
      "type": "long",
      "description": "卡激活的金额",
      "example": "10"
    },
    "card_remainingmount": {
      "type": "long",
      "description": "卡剩余的金额",
      "example": "10"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "网关返回码描述",
      "example": "successful"
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
  "card_active_total": "10",
  "card_active_amout": "10",
  "card_remainingmount": "10",
  "success": "true",
  "code": "200",
  "message": "successful",
  "request_id": ""
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.amount.query/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.amount.query/3.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/418)*