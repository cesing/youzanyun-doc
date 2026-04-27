---
apiName: "youzan.cardvoucher.delivery.card.pay.apply.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "retail_valuecard"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundOpenService"
method: "deliveryPay"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [retail]
deprecated: false
since: "2021-11-12"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3379"
---
# youzan.cardvoucher.delivery.card.pay.apply.1.0.0
> **所属分组**: retail_valuecard　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
提供提货卡核销的功能，使用前需先调youzan.cardvoucher.delivery.card.list.info（查询用户可提货卡列表接口）来查询用户的提货卡及其提货商品信息。
注意：该接口不会扣在有赞后台配置的商品库存，也不会生成订单，如果有需要对接，请直接调库存接口，更新线上库存

---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.apply/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `mobile` | `string` | ❌ 否 | `18534262387` | 手机号码，手机号码或者用户有赞ID二选一必传 |
| `yz_open_id` | `integer` | ❌ 否 | `7j3Gi1UH732330877366837248` | 用户有赞ID，手机号码或者用户有赞ID二选一必传 |
| `pay_request_no` | `string` | ✅ 是 | `test-delivery-0010` | 支付请求号，请确保唯一，支付冥等校验（商家自定义，支持符号+字符+数字组合，长度不超过24个字符） |
| `card_no` | `string` | ✅ 是 | `310210561054511` | 卡号 |
| `delivery_num` | `integer` | ✅ 是 | `2` | 提货数量 |
| `item_id` | `string` | ✅ 是 | `393933357` | 提货商品ID，可以通过查用户提货卡列表接口（youzan.cardvoucher.delivery.card.list. |
| `sku_id` | `string` | ✅ 是 | `11163396` | 提货商品规格ID（同一商品Id下，规格id唯一），可以通过查用户提货卡列表接口（youzan.cardvoucher.d |
| `goods_name` | `string` | ✅ 是 | `称重商品` | 提货商品名称 |
| `remark` | `string` | ✅ 是 | `提货卡核销` | 描述 |
| `operator` | `string` | ✅ 是 | `13734262381` | 操作人信息 |
---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
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
      "type": "string",
      "description": "接口请求返回码",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "支付成功"
    },
    "success": {
      "type": "string",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 接口返回数据 |
| `pay_request_no` | `string` | ❌ 否 | `test-delivery-0010` | 支付请求号 |
| `pay_order_no` | `string` | ❌ 否 | `CDP211111131739000002` | 支付订单号 |
| `status` | `string` | ❌ 否 | `SUCCESS` | 支付状态(SUCCESS：成功；FAIL：失败；ING：支付中) |
| `code` | `string` | ❌ 否 | `200` | 结果码 |
| `msg` | `string` | ❌ 否 | `支付成功` | 状态描述 |
| `success` | `string` | ❌ 否 | `true` | 接口请求是否成功 |
| `code` | `string` | ❌ 否 | `200` | 接口请求返回码 |
| `message` | `string` | ❌ 否 | `successful` | 接口请求返回信息 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3379

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "pay_request_no": "test-delivery-0010",
  "card_no": "310210561054511",
  "delivery_num": "2",
  "item_id": "393933357",
  "sku_id": "11163396"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.apply/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "pay_request_no": "test-delivery-0010",
  "card_no": "310210561054511",
  "delivery_num": "2",
  "item_id": "393933357",
  "sku_id": "11163396"
}

response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

> ⚠️ **注意**：以上为示例代码，`access_token` 需要通过 OAuth2.0 流程获取。
> 真实调用地址和参数请以管理后台详情页为准。

---
## 5. 错误码
## 错误码

| 错误码 | 说明 | 处理建议 |
|--------|------|----------|
| 1000 | 系统内部错误 | 稍后重试或联系技术支持 |
| 1001 | 鉴权失败 | 检查 access_token 是否有效 |
| 1002 | 参数校验失败 | 检查必填参数是否完整 |
| 1003 | 权限不足 | 确认应用已开通对应接口权限 |
| 1004 | 频率超限 | 降低请求频率或申请更高配额 |
| 1005 | 资源不存在 | 检查请求的业务 ID 是否正确 |
| 1006 | 请求超时 | 增加超时时间或稍后重试 |
| 1007 | 账户欠费 | 完成账户充值后重试 |

> 更多错误码请参考：[有赞云错误码文档](https://doc.youzanyun.com) |

---
## 6. 内部服务信息
| 字段 | 值 |
|------|---|
| 协议类型 | dubbo |
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundOpenService` |
| 方法名称 | `deliveryPay` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3379)_