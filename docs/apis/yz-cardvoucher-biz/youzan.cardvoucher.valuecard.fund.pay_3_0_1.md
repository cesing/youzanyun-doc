---
apiName: "youzan.cardvoucher.valuecard.fund.pay.3.0.1"
version: "3.0.1"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "pay"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2019-03-14"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/537"
---
# youzan.cardvoucher.valuecard.fund.pay.3.0.1
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
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
      "type": "array",
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
      "type": "integer",
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
**请求参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `mobile` | `string` | ❌ | `18972515558` | 用户手机号码（mobile或者yz_open_id二选一） |
| `yz_open_id` | `integer` | ❌ | `MVJ5w0uy585097513770430464` | 有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】（mobile或者yz_open_id二选一） |
| `card_nos` | `array` | ✅ | `["310201117303395"]` | 用于支付的卡号列表，目前支持最多20张卡，可通过以下接口获取用户可用储值卡列表以及卡内余额 youzan.cardvoucher.valuecard.info. |
| `pay_request_no` | `string` | ✅ | `pay-weixiao-20190801005` | 支付请求号，请确保唯一（商家自定义传入，支持符号+字母+数字组合，长度不超过24个字符） |
| `goods_name` | `string` | ✅ | `商品名称Test` | 商品名称（长度不超过24个字符） |
| `amount` | `integer` | ✅ | `200` | 支付金额，单位：分 |
| `remark` | `string` | ❌ | `描述Test` | 支付描述（长度不超过100个字符） |
| `operator` | `string` | ✅ | `姓名` | 操作人姓名。如果是商家发起支付，请填写商家操作人姓名。如果是用户发起，请填写用户姓名（长度不超过24个字符） |
| `pay_mode` | `integer` | ❌ | `1` | 支付模式：1-按卡号核销（默认）；2-按用户核销 |
| `data_source` | `integer` | ❌ | `1` | 数据来源，默认从有赞标准流程数据库中获取，1 表示从有赞标准来源数据库中获取 2 表示从扩展点获取，搭配储值卡支付扩展点使用 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
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
      "type": "integer",
      "description": "网关返回码，表示本次请求是否成功。200:成功",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "支付成功"
    },
    "success": {
      "type": "boolean",
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
      "type": "object",
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
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 受理结果 |
| `pay_request_no` | `string` | ❌ | `pay-weixiao-20190801005` | 支付请求号 |
| `pay_order_no` | `string` | ❌ | `CDP190801163242262240` | 支付订单号 |
| `status` | `string` | ❌ | `SUCCESS` | 支付状态；SUCCESS：支付成功，FAIL：支付失败，ING：支付中 |
| `code` | `string` | ❌ | `200` | 结果码；200：支付成功，1001：支付失败，1002：支付失败,未订阅储值插件，1003：支付失败,卡号不存在，1004：支付失败,余额不足，1005：支付失 |
| `msg` | `string` | ❌ | `支付成功` | 状态描述 |
| `success` | `boolean` | ❌ | `true` | 表示本次请求是否成功。true:成功,false:失败 |
| `code` | `integer` | ❌ | `200` | 网关返回码，表示本次请求是否成功。200:成功 |
| `message` | `string` | ❌ | `请求成功` | 网关返回码描述 |
| `request_id` | `string` | ❌ | `aaddqwfqwfqf` | 请求ID |
| `error_data` | `object` | ❌ | `error` | 失败原因 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.pay/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "mobile": "18972515558",\n  "yz_open_id": "MVJ5w0uy585097513770430464",\n  "card_nos": "[\"310201117303395\"]",\n  "pay_request_no": "pay-weixiao-20190801005",\n  "goods_name": "商品名称Test",\n  "amount": "200",\n  "remark": "描述Test",\n  "operator": "姓名",\n  "pay_mode": "1",\n  "data_source": "1"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.pay/3.0.1"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "mobile": "18972515558",
    "yz_open_id": "MVJ5w0uy585097513770430464",
    "card_nos": "[\"310201117303395\"]",
    "pay_request_no": "pay-weixiao-20190801005",
    "goods_name": "商品名称Test",
    "amount": "200",
    "remark": "描述Test",
    "operator": "姓名",
    "pay_mode": "1",
    "data_source": "1"
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