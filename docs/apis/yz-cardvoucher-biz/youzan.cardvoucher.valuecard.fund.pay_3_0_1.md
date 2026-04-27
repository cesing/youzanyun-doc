---
apiName: "youzan.cardvoucher.valuecard.fund.pay.3.0.1"
version: "3.0.1"
status: "已上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundOpenService"
method: "pay"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner]
deprecated: false
since: "2019-03-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=537"
---
# youzan.cardvoucher.valuecard.fund.pay.3.0.1
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线
---
## 1. 场景说明
该接口支持微商城单店、微商城连锁、零售调用，适用于根据商品名称、用户手机号码等使用储值卡支付。连锁门店网店模式的总部，没有经营权限的，不能使用该接口。
出于系统稳定性考虑，需要注意如下：(1)按卡号核销(默认)，允许支付的储值卡最多不能超过20张;(2)按用户核销，允许支付的储值卡最多不能超过100张。
商家想按用户核销，需要进行如下操作：
（1）入参字段payMode=2
（2）加入白名单（需联系有赞云同事添加）
如果用户的储值卡有限品类、限店铺等相关限制，禁用按用户核销功能。
如发生下述任一情况而导致服务中断及开发者损失的，有赞不承担责任：
（1）发生不可抗力情形的；
（2）黑客攻击、计算机病毒侵入或发作的；
（3）计算机系统遭到破坏、瘫痪或无法正常使用的；
（4）电信部门技术调整的；
（5）因政府管制而造成暂时性关闭的；
（6）其它非因有赞的过错而引起的。
版本新增：yz_open_id（有赞开放ID）参数
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.pay/3.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（10 个参数）:
```json
{
  "type": "object",
  "properties": {
    "mobile": {
      "type": "string",
      "description": "用户手机号码（mobile或者yz_open_id二选一）",
      "example": "18972515558"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】（mobile或者yz_open_id二选一）",
      "example": "MVJ5w0uy585097513770430464"
    },
    "card_nos": {
      "type": "string",
      "description": "用于支付的卡号列表，目前支持最多20张卡，可通过以下接口获取用户可用储值卡列表以及卡内余额 youzan.cardvoucher.valuecard.info.bysup.query。 如果选择payMode=2，也需要传入一张卡号作为记录留存。",
      "example": "[\"310201117303395\"]"
    },
    "pay_request_no": {
      "type": "string",
      "description": "支付请求号，请确保唯一（商家自定义传入，支持符号+字母+数字组合，长度不超过24个字符）",
      "example": "pay-weixiao-20190801005"
    },
    "goods_name": {
      "type": "string",
      "description": "商品名称（长度不超过24个字符）",
      "example": "商品名称Test"
    },
    "amount": {
      "type": "string",
      "description": "支付金额，单位：分",
      "example": "200"
    },
    "remark": {
      "type": "string",
      "description": "支付描述（长度不超过100个字符）",
      "example": "描述Test"
    },
    "operator": {
      "type": "string",
      "description": "操作人姓名。如果是商家发起支付，请填写商家操作人姓名。如果是用户发起，请填写用户姓名（长度不超过24个字符）",
      "example": "姓名"
    },
    "pay_mode": {
      "type": "integer",
      "description": "支付模式：1-按卡号核销（默认）；2-按用户核销",
      "example": "1"
    },
    "data_source": {
      "type": "integer",
      "description": "数据来源，默认从有赞标准流程数据库中获取，1 表示从有赞标准来源数据库中获取 2 表示从扩展点获取，搭配储值卡支付扩展点使用",
      "example": "1"
    }
  },
  "required": [
    "card_nos",
    "pay_request_no",
    "goods_name",
    "amount",
    "operator"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `mobile` | `string` | ❌ 否 | `18972515558` | 用户手机号码（mobile或者yz_open_id二选一） |
| `yz_open_id` | `integer` | ❌ 否 | `MVJ5w0uy585097513770430464` | 有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】（mobile |
| `card_nos` | `string` | ✅ 是 | `["310201117303395"]` | 用于支付的卡号列表，目前支持最多20张卡，可通过以下接口获取用户可用储值卡列表以及卡内余额 youzan.cardvou |
| `pay_request_no` | `string` | ✅ 是 | `pay-weixiao-20190801005` | 支付请求号，请确保唯一（商家自定义传入，支持符号+字母+数字组合，长度不超过24个字符） |
| `goods_name` | `string` | ✅ 是 | `商品名称Test` | 商品名称（长度不超过24个字符） |
| `amount` | `string` | ✅ 是 | `200` | 支付金额，单位：分 |
| `remark` | `string` | ❌ 否 | `描述Test` | 支付描述（长度不超过100个字符） |
| `operator` | `string` | ✅ 是 | `姓名` | 操作人姓名。如果是商家发起支付，请填写商家操作人姓名。如果是用户发起，请填写用户姓名（长度不超过24个字符） |
| `pay_mode` | `integer` | ❌ 否 | `1` | 支付模式：1-按卡号核销（默认）；2-按用户核销 |
| `data_source` | `integer` | ❌ 否 | `1` | 数据来源，默认从有赞标准流程数据库中获取，1 表示从有赞标准来源数据库中获取 2 表示从扩展点获取，搭配储值卡支付扩展点 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "受理结果"
    },
    "pay_request_no": {
      "type": "string",
      "description": "支付请求号",
      "example": "pay-weixiao-20190801005"
    },
    "pay_order_no": {
      "type": "string",
      "description": "支付订单号",
      "example": "CDP190801163242262240"
    },
    "status": {
      "type": "string",
      "description": "支付状态；SUCCESS：支付成功，FAIL：支付失败，ING：支付中",
      "example": "SUCCESS"
    },
    "code": {
      "type": "string",
      "description": "网关返回码，表示本次请求是否成功。200:成功",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "支付成功"
    },
    "success": {
      "type": "string",
      "description": "表示本次请求是否成功。true:成功,false:失败",
      "example": "true"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "请求成功"
    },
    "request_id": {
      "type": "string",
      "description": "请求ID",
      "example": "aaddqwfqwfqf"
    },
    "error_data": {
      "type": "string",
      "description": "失败原因",
      "example": "error"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "pay_request_no": "pay-weixiao-20190801005",
  "pay_order_no": "CDP190801163242262240",
  "status": "SUCCESS",
  "code": "200",
  "msg": "支付成功",
  "success": "true"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 受理结果 |
| `pay_request_no` | `string` | ❌ 否 | `pay-weixiao-20190801005` | 支付请求号 |
| `pay_order_no` | `string` | ❌ 否 | `CDP190801163242262240` | 支付订单号 |
| `status` | `string` | ❌ 否 | `SUCCESS` | 支付状态；SUCCESS：支付成功，FAIL：支付失败，ING：支付中 |
| `code` | `string` | ❌ 否 | `200` | 结果码；200：支付成功，1001：支付失败，1002：支付失败,未订阅储值插件，1003：支付失败,卡号不存在，100 |
| `msg` | `string` | ❌ 否 | `支付成功` | 状态描述 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。true:成功,false:失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200:成功 |
| `message` | `string` | ❌ 否 | `请求成功` | 网关返回码描述 |
| `request_id` | `string` | ❌ 否 | `aaddqwfqwfqf` | 请求ID |
| `error_data` | `string` | ❌ 否 | `error` | 失败原因 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=537

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "card_nos": "[\"310201117303395\"]",
  "pay_request_no": "pay-weixiao-20190801005",
  "goods_name": "商品名称Test",
  "amount": "200",
  "operator": "姓名"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.pay/3.0.1"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "card_nos": "[\"310201117303395\"]",
  "pay_request_no": "pay-weixiao-20190801005",
  "goods_name": "商品名称Test",
  "amount": "200",
  "operator": "姓名"
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
| 方法名称 | `pay` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=537)_