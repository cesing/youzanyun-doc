---
apiName: "youzan.cardvoucher.giftcard.query.buydetail.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4065"
---

# youzan.cardvoucher.giftcard.query.buydetail.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

礼品卡模板详情查询：可分页查询礼品卡模板详细信息。与个人中心->余额->礼品卡->购买礼品卡->礼品卡模板详细页面中的查询效果一致。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buydetail/1.0.0`

**认证方式**: 凭证式

**请求参数**（1 个）:

```json
{
  "type": "object",
  "properties": {
    "template_no": {
      "type": "java.lang.String",
      "description": "模版号",
      "example": "110204008016011"
    }
  },
  "required": [
    "template_no"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.open.response.DealQueryBuyDetailOpenResponse>",
      "description": "数据",
      "example": ""
    },
    "template_name": {
      "type": "java.lang.String",
      "description": "模板名称",
      "example": "礼品卡"
    },
    "template_img": {
      "type": "java.lang.String",
      "description": "模板背景图片",
      "example": "https://img01.yzcdn.cn/upload_files/2023/02/06/FmHkosO7YgMI7h1KdDM7QcnEr7gE.png"
    },
    "instructions": {
      "type": "java.lang.String",
      "description": "使用须知",
      "example": "购卡成功后，你可选择自己使用或赠送给朋友"
    },
    "product_infos": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.card.dto.product.ProductInfoDTO>",
      "description": "卡面对应商品详细信息",
      "example": ""
    },
    "original_price": {
      "type": "java.lang.Long",
      "description": "原始单价，单位：分",
      "example": "10000"
    },
    "sale_price": {
      "type": "java.lang.Long",
      "description": "实际销售单价，单位：分",
      "example": "8000"
    },
    "stock": {
      "type": "java.lang.Long",
      "description": "库存 ，单位：张",
      "example": "79"
    },
    "gift_packs": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.card.dto.market.GiftPackInfoDTO>",
      "description": "礼包信息",
      "example": ""
    },
    "rule_rights": {
      "type": "com.youzan.pay.cardvoucher.biz.common.model.rule.RuleRightsDTO",
      "description": "规则权益",
      "example": ""
    },
    "coupon_rights": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.common.model.rule.CouponRightsDTO>",
      "description": "优惠券权益列表",
      "example": ""
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "template_name": "礼品卡",
  "template_img": "https://img01.yzcdn.cn/upload_files/2023/02/06/FmHkosO7YgMI7h1KdDM7QcnEr7gE.png",
  "instructions": "购卡成功后，你可选择自己使用或赠送给朋友",
  "product_infos": "",
  "original_price": "10000",
  "sale_price": "8000",
  "stock": "79"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buydetail/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buydetail/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4065)*