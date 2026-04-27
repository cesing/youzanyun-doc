---
apiName: "youzan.cardvoucher.openCardService.verify.checkCustomerPayCards.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "checkCustomerPayCards"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4803"
---

# youzan.cardvoucher.openCardService.verify.checkCustomerPayCards.1.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

创建订单前，校验卡列表是否可用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.openCardService.verify.checkCustomerPayCards/1.0.0`

**请求参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "客户号",
      "example": "SoQvb61L732695759723438080"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。当前请求的店铺id,连锁店铺为分店店铺di",
      "example": "92732278"
    },
    "items": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.card.dto.card.ItemContext>",
      "description": "商品上下文",
      "example": ""
    },
    "item_id": {
      "type": "long",
      "description": "商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.items.inventory.get （查询仓库中商品）获取",
      "example": "399515043"
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
    "card_no_list": {
      "type": "java.util.List<java.lang.String>",
      "description": "卡号列表",
      "example": "[\"310200463069568\"]"
    },
    "card_type": {
      "type": "java.lang.Integer",
      "description": "卡类型",
      "example": "102"
    },
    "sales_channel_id": {
      "type": "java.lang.Integer",
      "description": "销售渠道Id",
      "example": "0"
    },
    "app_name": {
      "type": "java.lang.String",
      "description": "应用名称",
      "example": "app_name"
    }
  },
  "required": [
    "yz_open_id",
    "kdt_id"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.card.response.CardInfoDTOResponse>",
      "description": "返回数据",
      "example": ""
    },
    "card_name": {
      "type": "java.lang.String",
      "description": "卡名称",
      "example": "礼品卡"
    },
    "summary_card_no": {
      "type": "java.lang.String",
      "description": "汇总卡号",
      "example": "310200463069568"
    },
    "balance": {
      "type": "java.lang.Long",
      "description": "余额（分）",
      "example": "89720"
    },
    "yz_open_id": {
      "type": "java.lang.String",
      "description": "有赞用户id",
      "example": "SoQvb61L732695759723438080"
    },
    "card_status": {
      "type": "java.lang.String",
      "description": "卡状态。\"normal\"（正常状态）,\"freeze\"（C端冻结状态）,\"cmpfrz\"（完全冻结状态），\"close\"（注销），\"receding\"（退卡中），\"receded\"（已退卡）",
      "example": "normal"
    },
    "card_type": {
      "type": "int",
      "description": "卡类型102储值卡。目前都是102的卡了",
      "example": "102"
    },
    "freezing_sum_dnom": {
      "type": "long",
      "description": "被冻结的金额",
      "example": "0"
    },
    "is_exclusion": {
      "type": "java.lang.Boolean",
      "description": "是否互斥卡(无优惠卡)",
      "example": "false"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "网关返回码，表示本次请求是否成功。200 成功",
      "example": "200"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "card_name": "礼品卡",
  "summary_card_no": "310200463069568",
  "balance": "89720",
  "yz_open_id": "SoQvb61L732695759723438080",
  "card_status": "normal",
  "card_type": "102",
  "freezing_sum_dnom": "0"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.openCardService.verify.checkCustomerPayCards/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.openCardService.verify.checkCustomerPayCards/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4803)*