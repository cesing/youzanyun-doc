---
apiName: "youzan.cardvoucher.recharge.rule.query.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2400"
---

# youzan.cardvoucher.recharge.rule.query.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

该接口用于查看商家某张储值卡模板的储值规则。目前仅支持查询充值设置中的礼包信息和卡面额信息。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.recharge.rule.query/1.0.0`

**认证方式**: 凭证式

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】",
      "example": "MVJ5w0uy585097513770430464"
    },
    "template_no": {
      "type": "java.lang.String",
      "description": "储值卡模版号，为空时默认查询店铺储值余额模板",
      "example": "110101052740001"
    },
    "channel_type": {
      "type": "java.lang.String",
      "description": "渠道类型限制 ALL:全部，ONLINE:线上充值，OFFLINE:线下充值，为空时默认值为ALL",
      "example": "ALL"
    }
  },
  "required": [
    "yz_open_id"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenQueryRechargeRuleDTO",
      "description": "返回参数",
      "example": ""
    },
    "product_infos": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.card.dto.product.ProductMchInfoDTO>",
      "description": "可选充值面额列表",
      "example": ""
    },
    "amount": {
      "type": "java.lang.Long",
      "description": "充值金额（单位：分）",
      "example": "1000"
    },
    "gift_packs": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.card.dto.market.GiftPackInfoDTO>",
      "description": "礼包信息列表",
      "example": ""
    },
    "gift_pack_id": {
      "type": "java.lang.String",
      "description": "礼包ID",
      "example": "10000255"
    },
    "gift_pack_name": {
      "type": "java.lang.String",
      "description": "礼包名称",
      "example": "充值10元送1元"
    },
    "fact_amount": {
      "type": "java.lang.Long",
      "description": "实际支付金额（单位：分）",
      "example": "1000"
    },
    "rule_rights": {
      "type": "com.youzan.pay.cardvoucher.biz.common.model.rule.RuleRightsDTO",
      "description": "礼包具体权益",
      "example": ""
    },
    "coupon_rights": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.common.model.rule.CouponRightsDTO>",
      "description": "优惠券权益",
      "example": ""
    },
    "coupon_id": {
      "type": "java.lang.String",
      "description": "优惠券ID，即优惠券/码活动时的活动id，activity_id、coupon_id都是优惠活动id",
      "example": "1990"
    },
    "coupon_name": {
      "type": "java.lang.String",
      "description": "优惠券名称",
      "example": "10元饮品券"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "product_infos": "",
  "amount": "1000",
  "gift_packs": "",
  "gift_pack_id": "10000255",
  "gift_pack_name": "充值10元送1元",
  "fact_amount": "1000",
  "rule_rights": ""
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.recharge.rule.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.recharge.rule.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2400)*