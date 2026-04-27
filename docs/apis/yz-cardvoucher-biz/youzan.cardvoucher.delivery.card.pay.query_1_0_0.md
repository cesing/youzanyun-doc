---
apiName: "youzan.cardvoucher.delivery.card.pay.query.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "retail_valuecard"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "deliveryPayQuery"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [retail]
deprecated: false
since: "2021-11-12"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3381"
---
# youzan.cardvoucher.delivery.card.pay.query.1.0.0
> **所属分组**: retail_valuecard　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
提货卡核销结果查询
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.query/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "pay_request_no": {
      "type": "string",
      "description": "支付请求号（二选一必填）",
      "example": "test-delivery-0008"
    },
    "pay_order_no": {
      "type": "string",
      "description": "支付订单号（二选一必填）",
      "example": "CDP211111115411000000"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `pay_request_no` | `string` | ❌ 否 | `test-delivery-0008` | 支付请求号（二选一必填） |
| `pay_order_no` | `string` | ❌ 否 | `CDP211111115411000000` | 支付订单号（二选一必填） |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "接口返回结果"
    },
    "pay_request_no": {
      "type": "string",
      "description": "支付请求号",
      "example": "test-delivery-0008"
    },
    "pay_order_no": {
      "type": "string",
      "description": "支付订单号",
      "example": "CDP211111115411000000"
    },
    "status": {
      "type": "string",
      "description": "支付状态（SUCCES：支付成功；FAIL：支付失败；ING：支付中）",
      "example": "SUCCESS"
    },
    "code": {
      "type": "string",
      "description": "结果码",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "支付成功"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户ID",
      "example": "7j3Gi1UH732330877366837248"
    },
    "mobile": {
      "type": "string",
      "description": "用户手机号",
      "example": "18577820653"
    },
    "card_no": {
      "type": "string",
      "description": "储值卡号",
      "example": "310210461184512"
    },
    "delivery_num": {
      "type": "integer",
      "description": "提货数量",
      "example": "2"
    },
    "item_id": {
      "type": "string",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 接口返回结果 |
| `pay_request_no` | `string` | ❌ 否 | `test-delivery-0008` | 支付请求号 |
| `pay_order_no` | `string` | ❌ 否 | `CDP211111115411000000` | 支付订单号 |
| `status` | `string` | ❌ 否 | `SUCCESS` | 支付状态（SUCCES：支付成功；FAIL：支付失败；ING：支付中） |
| `code` | `string` | ❌ 否 | `200` | 结果码 |
| `msg` | `string` | ❌ 否 | `支付成功` | 状态描述 |
| `yz_open_id` | `integer` | ❌ 否 | `7j3Gi1UH732330877366837248` | 有赞用户ID |
| `mobile` | `string` | ❌ 否 | `18577820653` | 用户手机号 |
| `card_no` | `string` | ❌ 否 | `310210461184512` | 储值卡号 |
| `delivery_num` | `integer` | ❌ 否 | `2` | 提货数量 |
| `item_id` | `string` | ❌ 否 | `393933357` | 提货商品ID |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3381

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.pay.query/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {}

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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService` |
| 方法名称 | `deliveryPayQuery` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3381)_