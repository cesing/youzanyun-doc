---
apiName: "youzan.cardvoucher.valuecard.fund.recharge.3.0.0"
version: "3.0.0"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundOpenService"
method: "recharge"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail]
deprecated: false
since: "2019-03-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=107"
---
# youzan.cardvoucher.valuecard.fund.recharge.3.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
储值充值受理接口，目前仅支持类似支付10元储值入账10元的功能，暂不支持储值规则。当前接口仅做充值受理，是否最后充值入账成功可以查询youzan.cardvoucher.valuecard.fund.recharge.get接口，或者接收储值充值结果消息
如发生下述任一情况而导致服务中断及开发者损失的，有赞不承担责任：
（1）发生不可抗力情形的；
（2）黑客攻击、计算机病毒侵入或发作的；
（3）计算机系统遭到破坏、瘫痪或无法正常使用的；
（4）电信部门技术调整的；
（5）因政府管制而造成暂时性关闭的；
（6）其它非因有赞的过错而引起的。
此为老版，推荐使用3.0.1新版本
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.recharge/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（8 个参数）:
```json
{
  "type": "object",
  "properties": {
    "mobile": {
      "type": "string",
      "description": "客户手机号，仅支持国内手机号（mobile或者buyer_id二选一）",
      "example": "18972515558"
    },
    "buyer_id": {
      "type": "integer",
      "description": "客户Id（有赞用户ID，在有赞平台账号平台下唯一。user_id，yz_uid，account_id都是账号id,后续会废弃推荐使用yz_open_id（mobile或者buyer_id二选一）",
      "example": "1441668074"
    },
    "card_no": {
      "type": "string",
      "description": "卡号，填写则按照输入卡号进行充值；不填则老储值店铺对储值卡充值，新储值店铺如果存在储值余额则对储值余额进行充值，否则对储值卡进行充值",
      "example": "310201117305531"
    },
    "recharge_request_no": {
      "type": "string",
      "description": "充值请求号，调用方自定义，请确保唯一且长度不超过24个字符",
      "example": "weixiao20190723001"
    },
    "amount": {
      "type": "string",
      "description": "充值金额，单位：分",
      "example": "120"
    },
    "remark": {
      "type": "string",
      "description": "描述（长度不超过100个字符）",
      "example": "描述说明Test"
    },
    "operator_name": {
      "type": "string",
      "description": "操作人姓名。如果是商家发起充值，请填写商家操作人姓名。如果是用户发起，请填写用户姓名（长度不超过24个字符）",
      "example": "卫潇"
    },
    "operator_mobile": {
      "type": "string",
      "description": "操作人手机号码",
      "example": "13211112222"
    }
  },
  "required": [
    "recharge_request_no",
    "amount",
    "operator_name",
    "operator_mobile"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `mobile` | `string` | ❌ 否 | `18972515558` | 客户手机号，仅支持国内手机号（mobile或者buyer_id二选一） |
| `buyer_id` | `integer` | ❌ 否 | `1441668074` | 客户Id（有赞用户ID，在有赞平台账号平台下唯一。user_id，yz_uid，account_id都是账号id,后续会 |
| `card_no` | `string` | ❌ 否 | `310201117305531` | 卡号，填写则按照输入卡号进行充值；不填则老储值店铺对储值卡充值，新储值店铺如果存在储值余额则对储值余额进行充值，否则对储 |
| `recharge_request_no` | `string` | ✅ 是 | `weixiao20190723001` | 充值请求号，调用方自定义，请确保唯一且长度不超过24个字符 |
| `amount` | `string` | ✅ 是 | `120` | 充值金额，单位：分 |
| `remark` | `string` | ❌ 否 | `描述说明Test` | 描述（长度不超过100个字符） |
| `operator_name` | `string` | ✅ 是 | `卫潇` | 操作人姓名。如果是商家发起充值，请填写商家操作人姓名。如果是用户发起，请填写用户姓名（长度不超过24个字符） |
| `operator_mobile` | `string` | ✅ 是 | `13211112222` | 操作人手机号码 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": ""
    },
    "recharge_request_no": {
      "type": "string",
      "description": "充值请求号",
      "example": "weixiao20190827001"
    },
    "recharge_order_no": {
      "type": "string",
      "description": "充值订单号",
      "example": "CDRG190827154329000021"
    },
    "status": {
      "type": "string",
      "description": "充值受理状态，SUCCESS：受理成功 FAIL：受理失败 UNKNOWN：未知状态",
      "example": "SUCCESS"
    },
    "code": {
      "type": "string",
      "description": "网关返回码，表示本次请求是否成功。200 成功",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "受理成功"
    },
    "amount": {
      "type": "string",
      "description": "储值充值金额，单位：分",
      "example": "300"
    },
    "success": {
      "type": "string",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "successful"
    },
    "request_id": {
      "type": "string",
      "description": ""
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "recharge_request_no": "weixiao20190827001",
  "recharge_order_no": "CDRG190827154329000021",
  "status": "SUCCESS",
  "code": "200",
  "msg": "受理成功",
  "amount": "300",
  "success": "true"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `recharge_request_no` | `string` | ❌ 否 | `weixiao20190827001` | 充值请求号 |
| `recharge_order_no` | `string` | ❌ 否 | `CDRG190827154329000021` | 充值订单号 |
| `status` | `string` | ❌ 否 | `SUCCESS` | 充值受理状态，SUCCESS：受理成功 FAIL：受理失败 UNKNOWN：未知状态 |
| `code` | `string` | ❌ 否 | `200` | 结果码，200：充值受理成功 1001：充值受理失败 1002：充值受理失败，店铺未签约或签约已过期 1003：充值受理 |
| `msg` | `string` | ❌ 否 | `受理成功` | 状态描述 |
| `amount` | `string` | ❌ 否 | `300` | 储值充值金额，单位：分 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200 成功 |
| `message` | `string` | ❌ 否 | `successful` | 网关返回码描述 |
| `request_id` | `string` | ❌ 否 | `` |  |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=107

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "recharge_request_no": "weixiao20190723001",
  "amount": "120",
  "operator_name": "卫潇",
  "operator_mobile": "13211112222"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.recharge/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "recharge_request_no": "weixiao20190723001",
  "amount": "120",
  "operator_name": "卫潇",
  "operator_mobile": "13211112222"
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
| 方法名称 | `recharge` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=107)_