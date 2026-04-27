---
apiName: "youzan.cardvoucher.valuecard.fund.pay.3.0.1"
version: "3.0.1"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/537"
---

# youzan.cardvoucher.valuecard.fund.pay.3.0.1

> **所属分组**: 储值卡

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

**认证方式**: 凭证式

**请求参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "mobile": {
      "type": "java.lang.String",
      "description": "用户手机号码（mobile或者yz_open_id二选一）",
      "example": "18972515558"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】（mobile或者yz_open_id二选一）",
      "example": "MVJ5w0uy585097513770430464"
    },
    "card_nos": {
      "type": "java.util.List<java.lang.String>",
      "description": "用于支付的卡号列表，目前支持最多20张卡，可通过以下接口获取用户可用储值卡列表以及卡内余额 youzan.cardvoucher.valuecard.info.bysup.query。 如果选择payMode=2，也需要传入一张卡号作为记录留存。",
      "example": "[\"310201117303395\"]"
    },
    "pay_request_no": {
      "type": "java.lang.String",
      "description": "支付请求号，请确保唯一（商家自定义传入，支持符号+字母+数字组合，长度不超过24个字符）",
      "example": "pay-weixiao-20190801005"
    },
    "goods_name": {
      "type": "java.lang.String",
      "description": "商品名称（长度不超过24个字符）",
      "example": "商品名称Test"
    },
    "amount": {
      "type": "long",
      "description": "支付金额，单位：分",
      "example": "200"
    },
    "remark": {
      "type": "java.lang.String",
      "description": "支付描述（长度不超过100个字符）",
      "example": "描述Test"
    },
    "operator": {
      "type": "java.lang.String",
      "description": "操作人姓名。如果是商家发起支付，请填写商家操作人姓名。如果是用户发起，请填写用户姓名（长度不超过24个字符）",
      "example": "姓名"
    },
    "pay_mode": {
      "type": "java.lang.Integer",
      "description": "支付模式：1-按卡号核销（默认）；2-按用户核销",
      "example": "1"
    },
    "data_source": {
      "type": "java.lang.Integer",
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

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenPayResultDTO",
      "description": "受理结果",
      "example": ""
    },
    "pay_request_no": {
      "type": "java.lang.String",
      "description": "支付请求号",
      "example": "pay-weixiao-20190801005"
    },
    "pay_order_no": {
      "type": "java.lang.String",
      "description": "支付订单号",
      "example": "CDP190801163242262240"
    },
    "status": {
      "type": "java.lang.String",
      "description": "支付状态；SUCCESS：支付成功，FAIL：支付失败，ING：支付中",
      "example": "SUCCESS"
    },
    "code": {
      "type": "int",
      "description": "网关返回码，表示本次请求是否成功。200:成功",
      "example": "200"
    },
    "msg": {
      "type": "java.lang.String",
      "description": "状态描述",
      "example": "支付成功"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。true:成功,false:失败",
      "example": "true"
    },
    "message": {
      "type": "java.lang.String",
      "description": "网关返回码描述",
      "example": "请求成功"
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "请求ID",
      "example": "aaddqwfqwfqf"
    },
    "error_data": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
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

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.pay/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.pay/3.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/537)*