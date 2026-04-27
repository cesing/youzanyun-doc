---
apiName: "youzan.cardvoucher.delivery.card.pay.apply.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "deliveryPay"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3379"
---

# youzan.cardvoucher.delivery.card.pay.apply.1.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

提供提货卡核销的功能，使用前需先调youzan.cardvoucher.delivery.card.list.info（查询用户可提货卡列表接口）来查询用户的提货卡及其提货商品信息。
注意：该接口不会扣在有赞后台配置的商品库存，也不会生成订单，如果有需要对接，请直接调库存接口，更新线上库存


---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.apply/1.0.0`

**请求参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "mobile": {
      "type": "java.lang.String",
      "description": "手机号码，手机号码或者用户有赞ID二选一必传",
      "example": "18534262387"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "用户有赞ID，手机号码或者用户有赞ID二选一必传",
      "example": "7j3Gi1UH732330877366837248"
    },
    "pay_request_no": {
      "type": "java.lang.String",
      "description": "支付请求号，请确保唯一，支付冥等校验（商家自定义，支持符号+字符+数字组合，长度不超过24个字符）",
      "example": "test-delivery-0010"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "卡号",
      "example": "310210561054511"
    },
    "delivery_num": {
      "type": "java.lang.Long",
      "description": "提货数量",
      "example": "2"
    },
    "item_id": {
      "type": "java.lang.String",
      "description": "提货商品ID，可以通过查用户提货卡列表接口（youzan.cardvoucher.delivery.card.list.info）获取卡对应的提货商品信息",
      "example": "393933357"
    },
    "sku_id": {
      "type": "java.lang.String",
      "description": "提货商品规格ID（同一商品Id下，规格id唯一），可以通过查用户提货卡列表接口（youzan.cardvoucher.delivery.card.list.info）获取卡对应的提货商品信息",
      "example": "11163396"
    },
    "goods_name": {
      "type": "java.lang.String",
      "description": "提货商品名称",
      "example": "称重商品"
    },
    "remark": {
      "type": "java.lang.String",
      "description": "描述",
      "example": "提货卡核销"
    },
    "operator": {
      "type": "java.lang.String",
      "description": "操作人信息",
      "example": "13734262381"
    }
  },
  "required": [
    "pay_request_no",
    "card_no",
    "delivery_num",
    "item_id",
    "sku_id",
    "goods_name",
    "remark",
    "operator"
  ]
}
```

**响应参数**（9 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenPayResultDTO",
      "description": "接口返回数据",
      "example": ""
    },
    "pay_request_no": {
      "type": "java.lang.String",
      "description": "支付请求号",
      "example": "test-delivery-0010"
    },
    "pay_order_no": {
      "type": "java.lang.String",
      "description": "支付订单号",
      "example": "CDP211111131739000002"
    },
    "status": {
      "type": "java.lang.String",
      "description": "支付状态(SUCCESS：成功；FAIL：失败；ING：支付中)",
      "example": "SUCCESS"
    },
    "code": {
      "type": "int",
      "description": "接口请求返回码",
      "example": "200"
    },
    "msg": {
      "type": "java.lang.String",
      "description": "状态描述",
      "example": "支付成功"
    },
    "success": {
      "type": "boolean",
      "description": "接口请求是否成功",
      "example": "true"
    },
    "message": {
      "type": "java.lang.String",
      "description": "接口请求返回信息",
      "example": "successful"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "pay_request_no": "test-delivery-0010",
  "pay_order_no": "CDP211111131739000002",
  "status": "SUCCESS",
  "code": "200",
  "msg": "支付成功",
  "success": "true"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.apply/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.apply/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3379)*