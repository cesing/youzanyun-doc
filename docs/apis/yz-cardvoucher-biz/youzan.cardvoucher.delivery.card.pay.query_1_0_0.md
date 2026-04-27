---
apiName: "youzan.cardvoucher.delivery.card.pay.query.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3381"
---

# youzan.cardvoucher.delivery.card.pay.query.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

提货卡核销结果查询

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.query/1.0.0`

**认证方式**: 凭证式

**请求参数**（2 个）:

```json
{
  "type": "object",
  "properties": {
    "pay_request_no": {
      "type": "java.lang.String",
      "description": "支付请求号（二选一必填）",
      "example": "test-delivery-0008"
    },
    "pay_order_no": {
      "type": "java.lang.String",
      "description": "支付订单号（二选一必填）",
      "example": "CDP211111115411000000"
    }
  },
  "required": []
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenDeliveryPayResultDTO",
      "description": "接口返回结果",
      "example": ""
    },
    "pay_request_no": {
      "type": "java.lang.String",
      "description": "支付请求号",
      "example": "test-delivery-0008"
    },
    "pay_order_no": {
      "type": "java.lang.String",
      "description": "支付订单号",
      "example": "CDP211111115411000000"
    },
    "status": {
      "type": "java.lang.String",
      "description": "支付状态（SUCCES：支付成功；FAIL：支付失败；ING：支付中）",
      "example": "SUCCESS"
    },
    "code": {
      "type": "java.lang.String",
      "description": "结果码",
      "example": "200"
    },
    "msg": {
      "type": "java.lang.String",
      "description": "状态描述",
      "example": "支付成功"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "有赞用户ID",
      "example": "7j3Gi1UH732330877366837248"
    },
    "mobile": {
      "type": "java.lang.String",
      "description": "用户手机号",
      "example": "18577820653"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "储值卡号",
      "example": "310210461184512"
    },
    "delivery_num": {
      "type": "java.lang.Long",
      "description": "提货数量",
      "example": "2"
    },
    "item_id": {
      "type": "java.lang.String",
      "description": "提货商品ID",
      "example": "393933357"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "pay_request_no": "test-delivery-0008",
  "pay_order_no": "CDP211111115411000000",
  "status": "SUCCESS",
  "code": "200",
  "msg": "支付成功",
  "yz_open_id": "7j3Gi1UH732330877366837248",
  "mobile": "18577820653"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3381)*