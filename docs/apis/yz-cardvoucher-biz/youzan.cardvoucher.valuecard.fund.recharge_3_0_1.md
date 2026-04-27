---
apiName: "youzan.cardvoucher.valuecard.fund.recharge.3.0.1"
version: "3.0.1"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "recharge"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/536"
---

# youzan.cardvoucher.valuecard.fund.recharge.3.0.1

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

该接口支持微商城单店、微商城连锁、零售调用，适用于根据account_id等给用户充值，目前仅支持类似支付10元储值入账10元的功能，暂不支持储值规则。当前接口仅做充值受理，是否最后充值入账成功可以查询youzan.cardvoucher.valuecard.fund.recharge.get接口，或者接收储值充值结果消息。
如发生下述任一情况而导致服务中断及开发者损失的，有赞不承担责任：
（1）发生不可抗力情形的；
（2）黑客攻击、计算机病毒侵入或发作的；
（3）计算机系统遭到破坏、瘫痪或无法正常使用的；
（4）电信部门技术调整的；
（5）因政府管制而造成暂时性关闭的；
（6）其它非因有赞的

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.recharge/3.0.1`

**请求参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "mobile": {
      "type": "java.lang.String",
      "description": "客户手机号，仅支持国内手机号（mobile或者yz_open_id二选一）",
      "example": "18972511111"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】（mobile或者yz_open_id二选一）",
      "example": "MVJ5w0uy585097513770430464"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "卡号（填写则按照输入卡号进行充值；不填如果存在储值余额规则则对储值余额卡进行充值，客户没有储值余额卡则创建储值余额卡然后充值，不存在储值余额规则接口返回报错）",
      "example": "310201117305531"
    },
    "recharge_request_no": {
      "type": "java.lang.String",
      "description": "充值请求号，调用方自定义，请确保唯一且长度不超过24个字符",
      "example": "weixiao20190723001"
    },
    "amount": {
      "type": "long",
      "description": "充值金额，从1开始正整数，单位：分",
      "example": "120"
    },
    "bonus_amount": {
      "type": "java.lang.Long",
      "description": "充值赠送金,从 1 开始正整数，单位:分",
      "example": "100"
    },
    "remark": {
      "type": "java.lang.String",
      "description": "描述（长度不超过100个字符）",
      "example": "描述说明Test"
    },
    "operator_name": {
      "type": "java.lang.String",
      "description": "操作人姓名。如果是商家发起充值，请填写商家操作人姓名。如果是用户发起，请填写用户姓名（长度不超过24个字符）",
      "example": "卫潇"
    },
    "operator_mobile": {
      "type": "java.lang.String",
      "description": "操作人手机号码",
      "example": "13211112222"
    },
    "sub_pay_method_name": {
      "type": "java.lang.String",
      "description": "子支付方式名称，用户充值使用的支付方式，会保存到充值记录，用于后续查询使用。内容不做强校验，由开发者决定。长度最多32.",
      "example": "wx"
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

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenRechargeResultDTO",
      "description": "返回值",
      "example": ""
    },
    "recharge_request_no": {
      "type": "java.lang.String",
      "description": "充值请求号",
      "example": "weixiao20190827001"
    },
    "recharge_order_no": {
      "type": "java.lang.String",
      "description": "充值订单号",
      "example": "CDRG190827154329000021"
    },
    "status": {
      "type": "java.lang.String",
      "description": "充值受理状态，SUCCESS：受理成功 FAIL：受理失败 UNKNOWN：未知状态",
      "example": "SUCCESS"
    },
    "code": {
      "type": "int",
      "description": "网关返回码，表示本次请求是否成功。200 成功",
      "example": "200"
    },
    "msg": {
      "type": "java.lang.String",
      "description": "状态描述",
      "example": "受理成功"
    },
    "amount": {
      "type": "long",
      "description": "储值充值金额，单位：分",
      "example": "300"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "message": {
      "type": "java.lang.String",
      "description": "网关返回码描述",
      "example": "successful"
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "traceId",
      "example": "weixiao20190723001"
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

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.recharge/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.recharge/3.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/536)*