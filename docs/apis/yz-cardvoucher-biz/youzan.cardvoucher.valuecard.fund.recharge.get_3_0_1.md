---
apiName: "youzan.cardvoucher.valuecard.fund.recharge.get.3.0.1"
version: "3.0.1"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "rechargeQuery"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [retail, wsc, wsc_head, wsc_online, retail_d_partner]
deprecated: false
since: "2019-11-05"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=701"
---
# youzan.cardvoucher.valuecard.fund.recharge.get.3.0.1
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
该接口支持微商城单店、微商城连锁、零售调用，适用于根据充值订单号或充值请求号查询充值结果，充值受理成功后（youzan.cardvoucher.valuecard.fund.recharge），通过此接口获取最后充值结果。也可以通过监听充值结果消息来确认充值结果，两种方式结果完全一致
版本新增：操作人、充值时间、店铺与客户信息、卡号等返回。注意：仅支持查询通过有赞云API接口充值的订单。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.recharge.get/3.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "recharge_request_no": {
      "type": "string",
      "description": "充值请求号（二选一）",
      "example": "20220225012440533"
    },
    "recharge_order_no": {
      "type": "string",
      "description": "充值订单号（二选一）",
      "example": "CDRG190723152420000049"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `recharge_request_no` | `string` | ❌ 否 | `20220225012440533` | 充值请求号（二选一） |
| `recharge_order_no` | `string` | ❌ 否 | `CDRG190723152420000049` | 充值订单号（二选一） |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "接口返回数据"
    },
    "recharge_request_no": {
      "type": "string",
      "description": "充值请求号",
      "example": "20220225012440533"
    },
    "recharge_order_no": {
      "type": "string",
      "description": "充值订单号",
      "example": "CDRG190826175842000017"
    },
    "status": {
      "type": "string",
      "description": "充值状态SUCCESS:充值成功FAIL:充值失败ING:充值中",
      "example": "SUCCESS"
    },
    "code": {
      "type": "string",
      "description": "结果码，200：充值成功、充值中 1001：充值失败 1002：充值失败，店铺未签约或签约已过期 1003：充值失败，储值卡状态异常",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "充值成功"
    },
    "amount": {
      "type": "string",
      "description": "储值充值金额，单位：分",
      "example": "100"
    },
    "bonus_amount": {
      "type": "integer",
      "description": "储值充值赠送金,单位：分",
      "example": "100"
    },
    "kdt_id": {
      "type": "integer",
      "description": "受理店铺Id",
      "example": "491391"
    },
    "buyer_id": {
      "type": "integer",
      "description": "客户Id",
      "example": "8100531847"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "310200301240918"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "recharge_request_no": "20220225012440533",
  "recharge_order_no": "CDRG190826175842000017",
  "status": "SUCCESS",
  "code": "200",
  "msg": "充值成功",
  "amount": "100",
  "bonus_amount": "100"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 接口返回数据 |
| `recharge_request_no` | `string` | ❌ 否 | `20220225012440533` | 充值请求号 |
| `recharge_order_no` | `string` | ❌ 否 | `CDRG190826175842000017` | 充值订单号 |
| `status` | `string` | ❌ 否 | `SUCCESS` | 充值状态SUCCESS:充值成功FAIL:充值失败ING:充值中 |
| `code` | `string` | ❌ 否 | `200` | 结果码，200：充值成功、充值中 1001：充值失败 1002：充值失败，店铺未签约或签约已过期 1003：充值失败，储 |
| `msg` | `string` | ❌ 否 | `充值成功` | 状态描述 |
| `amount` | `string` | ❌ 否 | `100` | 储值充值金额，单位：分 |
| `bonus_amount` | `integer` | ❌ 否 | `100` | 储值充值赠送金,单位：分 |
| `kdt_id` | `integer` | ❌ 否 | `491391` | 受理店铺Id |
| `buyer_id` | `integer` | ❌ 否 | `8100531847` | 客户Id |
| `card_no` | `string` | ❌ 否 | `310200301240918` | 卡号 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=701

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.recharge.get/3.0.1"
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
| 方法名称 | `rechargeQuery` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=701)_