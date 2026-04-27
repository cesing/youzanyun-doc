---
apiName: "youzan.cardvoucher.opencardservice.query.querycustomerpaycards.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "queryCustomerPayCards"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4796"
---

# youzan.cardvoucher.opencardservice.query.querycustomerpaycards.1.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

下单页查询用户可用储值卡列表，返回相关的余额卡、礼品卡信息。
针对开放接口，只提供简单的查询可用卡列表逻辑。
支持的功能
1：如果当前购买的商品不在卡模板配置的【适用商品】范围内，那么该卡不可用
2：如果当前所在店铺不在卡模板配置的【适用店铺】范围内，那么该卡不可用

不支持：
1.不支持判断  卡模板设置的【优惠设置】
2.不支持判断 卡模板设置的【仅限此卡支付时享受相应折扣优惠】
3.不支持判断【储值会员】模式下，卡模板设置的【余额全额支付时可享受会员优惠】

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.opencardservice.query.querycustomerpaycards/1.0.0`

**请求参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "客户号",
      "example": "MVJ5w0uy585097513770430464"
    },
    "items": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.card.dto.card.ItemContext>",
      "description": "商品上下文",
      "example": ""
    },
    "item_id": {
      "type": "long",
      "description": "商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.items.inventory.get （查询仓库中商品）获取",
      "example": "365112687"
    },
    "outside": {
      "type": "java.lang.Boolean",
      "description": "是否为外部商品，非有赞IC商品设置为true,默认为IC商品",
      "example": "false"
    },
    "is_present": {
      "type": "java.lang.Boolean",
      "description": "是否是赠品",
      "example": "false"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。表示当前请求的店铺id。连锁店铺为分店店铺id",
      "example": "92732278"
    },
    "pay_amount": {
      "type": "java.lang.Long",
      "description": "订单金额（单位：分）",
      "example": "50"
    },
    "origin_amount": {
      "type": "java.lang.Long",
      "description": "订单原价金额（单位：分）",
      "example": "100"
    },
    "distribution": {
      "type": "java.lang.Boolean",
      "description": "当前交易请求是否包含分销商品",
      "example": "false"
    },
    "checked_list": {
      "type": "java.util.List<java.lang.String>",
      "description": "已选卡号列表。首次返回可用卡列表后，用户可以重新手动勾选自己想要支付的卡列表。",
      "example": "[\"310200561086860\"]"
    }
  },
  "required": [
    "yz_open_id",
    "items",
    "item_id",
    "kdt_id",
    "pay_amount",
    "origin_amount"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.open.response.OpenCustomerPayCardResponse",
      "description": "返回的数据",
      "example": ""
    },
    "usable_list": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.card.dto.card.CustomerPayCardDTO>",
      "description": "可用列表",
      "example": ""
    },
    "publish_mch_id": {
      "type": "java.lang.String",
      "description": "发卡机构商户号",
      "example": "170307112147366149"
    },
    "publish_kdt_id": {
      "type": "java.lang.Long",
      "description": "发卡机构店铺id",
      "example": ""
    },
    "card_name": {
      "type": "java.lang.String",
      "description": "卡名称",
      "example": "干柴华的测试店铺"
    },
    "summary_card_no": {
      "type": "java.lang.String",
      "description": "汇总卡号",
      "example": "310200561086860"
    },
    "balance": {
      "type": "java.lang.Long",
      "description": "余额（分）",
      "example": "200800"
    },
    "use_specification": {
      "type": "java.lang.String",
      "description": "使用说明",
      "example": ""
    },
    "cancel_use_specification": {
      "type": "java.lang.String",
      "description": "取消勾选使用说明",
      "example": ""
    },
    "use_special_channel": {
      "type": "java.lang.Boolean",
      "description": "使用特殊渠道(多人拼团积分商城秒杀赠品下单砍价0元购以外的)",
      "example": "false"
    },
    "usable": {
      "type": "java.lang.Boolean",
      "description": "是否可用",
      "example": "true"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "usable_list": "",
  "publish_mch_id": "170307112147366149",
  "publish_kdt_id": "",
  "card_name": "干柴华的测试店铺",
  "summary_card_no": "310200561086860",
  "balance": "200800",
  "use_specification": ""
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.opencardservice.query.querycustomerpaycards/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.opencardservice.query.querycustomerpaycards/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4796)*