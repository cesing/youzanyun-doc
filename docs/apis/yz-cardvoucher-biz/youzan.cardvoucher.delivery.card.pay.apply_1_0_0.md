---
apiName: "youzan.cardvoucher.delivery.card.pay.apply.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "retail_valuecard"
method: "deliveryPay"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-11-12"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3379"
---
# youzan.cardvoucher.delivery.card.pay.apply.1.0.0
> **所属分组**: retail_valuecard　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
提供提货卡核销的功能，使用前需先调youzan.cardvoucher.delivery.card.list.info（查询用户可提货卡列表接口）来查询用户的提货卡及其提货商品信息。
注意：该接口不会扣在有赞后台配置的商品库存，也不会生成订单，如果有需要对接，请直接调库存接口，更新线上库存

---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.apply/1.0.0`
**请求参数 Schema**（10 个参数）:
```json
{
  "type": "object",
  "properties": {
    "mobile": {
      "type": "string",
      "description": "手机号码，手机号码或者用户有赞ID二选一必传",
      "example": "18534262387"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "用户有赞ID，手机号码或者用户有赞ID二选一必传",
      "example": "7j3Gi1UH732330877366837248"
    },
    "pay_request_no": {
      "type": "string",
      "description": "支付请求号，请确保唯一，支付冥等校验（商家自定义，支持符号+字符+数字组合，长度不超过24个字符）",
      "example": "test-delivery-0010"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "310210561054511"
    },
    "delivery_num": {
      "type": "integer",
      "description": "提货数量",
      "example": "2"
    },
    "item_id": {
      "type": "string",
      "description": "提货商品ID，可以通过查用户提货卡列表接口（youzan.cardvoucher.delivery.card.list.info）获取卡对应的提货商品信息",
      "example": "393933357"
    },
    "sku_id": {
      "type": "string",
      "description": "提货商品规格ID（同一商品Id下，规格id唯一），可以通过查用户提货卡列表接口（youzan.cardvoucher.delivery.card.list.info）获取卡对应的提货商品信息",
      "example": "11163396"
    },
    "goods_name": {
      "type": "string",
      "description": "提货商品名称",
      "example": "称重商品"
    },
    "remark": {
      "type": "string",
      "description": "描述",
      "example": "提货卡核销"
    },
    "operator": {
      "type": "string",
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
**请求参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `mobile` | `string` | ❌ | `18534262387` | 手机号码，手机号码或者用户有赞ID二选一必传 |
| `yz_open_id` | `integer` | ❌ | `7j3Gi1UH732330877366837248` | 用户有赞ID，手机号码或者用户有赞ID二选一必传 |
| `pay_request_no` | `string` | ✅ | `test-delivery-0010` | 支付请求号，请确保唯一，支付冥等校验（商家自定义，支持符号+字符+数字组合，长度不超过24个字符） |
| `card_no` | `string` | ✅ | `310210561054511` | 卡号 |
| `delivery_num` | `integer` | ✅ | `2` | 提货数量 |
| `item_id` | `string` | ✅ | `393933357` | 提货商品ID，可以通过查用户提货卡列表接口（youzan.cardvoucher.delivery.card.list.info）获取卡对应的提货商品信息 |
| `sku_id` | `string` | ✅ | `11163396` | 提货商品规格ID（同一商品Id下，规格id唯一），可以通过查用户提货卡列表接口（youzan.cardvoucher.delivery.card.list.in |
| `goods_name` | `string` | ✅ | `称重商品` | 提货商品名称 |
| `remark` | `string` | ✅ | `提货卡核销` | 描述 |
| `operator` | `string` | ✅ | `13734262381` | 操作人信息 |
---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "接口返回数据"
    },
    "pay_request_no": {
      "type": "string",
      "description": "支付请求号",
      "example": "test-delivery-0010"
    },
    "pay_order_no": {
      "type": "string",
      "description": "支付订单号",
      "example": "CDP211111131739000002"
    },
    "status": {
      "type": "string",
      "description": "支付状态(SUCCESS：成功；FAIL：失败；ING：支付中)",
      "example": "SUCCESS"
    },
    "code": {
      "type": "integer",
      "description": "接口请求返回码",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "支付成功"
    },
    "success": {
      "type": "boolean",
      "description": "接口请求是否成功",
      "example": "true"
    },
    "message": {
      "type": "string",
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
**响应参数明细**（9 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 接口返回数据 |
| `pay_request_no` | `string` | ❌ | `test-delivery-0010` | 支付请求号 |
| `pay_order_no` | `string` | ❌ | `CDP211111131739000002` | 支付订单号 |
| `status` | `string` | ❌ | `SUCCESS` | 支付状态(SUCCESS：成功；FAIL：失败；ING：支付中) |
| `code` | `string` | ❌ | `200` | 结果码 |
| `msg` | `string` | ❌ | `支付成功` | 状态描述 |
| `success` | `boolean` | ❌ | `true` | 接口请求是否成功 |
| `code` | `integer` | ❌ | `200` | 接口请求返回码 |
| `message` | `string` | ❌ | `successful` | 接口请求返回信息 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.apply/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "mobile": "18534262387",\n  "yz_open_id": "7j3Gi1UH732330877366837248",\n  "pay_request_no": "test-delivery-0010",\n  "card_no": "310210561054511",\n  "delivery_num": "2",\n  "item_id": "393933357",\n  "sku_id": "11163396",\n  "goods_name": "称重商品",\n  "remark": "提货卡核销",\n  "operator": "13734262381"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.apply/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "mobile": "18534262387",
    "yz_open_id": "7j3Gi1UH732330877366837248",
    "pay_request_no": "test-delivery-0010",
    "card_no": "310210561054511",
    "delivery_num": "2",
    "item_id": "393933357",
    "sku_id": "11163396",
    "goods_name": "称重商品",
    "remark": "提货卡核销",
    "operator": "13734262381"
}

resp = requests.post(url, json=payload, headers=headers)
print(resp.json())
```
---
## 5. 错误码
| 错误码 | 类型 | 说明 |
|--------|------|------|
| 10001 | `SYSTEM_ERROR` | 系统内部错误 |
| 10002 | `INVALID_PARAMETER` | 参数错误 |
| 10003 | `UNAUTHORIZED` | 未授权或授权已过期 |
| 10004 | `PERMISSION_DENIED` | 无权限调用此接口 |
| 10005 | `RESOURCE_NOT_FOUND` | 请求的资源不存在 |
| 20001 | `RATE_LIMIT_EXCEEDED` | 调用频率超限 |
| 20002 | `QUOTA_EXCEEDED` | 接口配额已用完 |
---
## 6. 权限与计费

**接口计费状态：未知（请以官网实际披露为准）。**

**拥有此API的能力包：** 暂无数据（请以官网实际披露为准）。

---
## 7. 权限说明

**应用类目 → 权限类型：**

| 应用类目 | 权限类型 |
|----------|----------|
| 有赞微商城、有赞零售、有赞教育、有赞美业 | 普通自研商家（基础权益） |
| 大客户定制接口、美业大客户定制、零售大客户定制、收款二维码-大客专用 | 大客定制接口（需购买大客套餐） |
| 客户关系CRM、门店POS | iPaaS 套餐权益（需购买 iPaaS 套餐） |

> 权限数据来源：[有赞云能力包说明](https://doc.youzanyun.com/detail/content/API/0/120)