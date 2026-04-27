---
apiName: "youzan.ad.order.detail.query.1.0.0"
version: "1.0.0"
appName: "ad-cps"
apiGroup: "营销优惠"
method: "getOrderDetail"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/714"
---

# youzan.ad.order.detail.query.1.0.0

> **所属分组**: 营销优惠  **所属应用**: ad-cps

---

## 1. 场景说明

查询分佣订单信息（仅支持合作渠道方使用，开发者及商家请勿调用）

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ad.order.detail.query/1.0.0`

**请求参数**（2 个）:

```json
{
  "type": "object",
  "properties": {
    "order_no": {
      "type": "java.lang.String",
      "description": "推广订单号即有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E20190318135014056100001"
    },
    "operator": {
      "type": "java.lang.String",
      "description": "操作者",
      "example": "有赞"
    }
  },
  "required": []
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.ad.cps.api.req.yun.YunOrderDetailResponse",
      "description": "查询订单分佣信息的响应数据",
      "example": ""
    },
    "order_no": {
      "type": "java.lang.String",
      "description": "推广订单号即有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E20190318135014056100001"
    },
    "postage": {
      "type": "java.lang.Long",
      "description": "运费，单位分",
      "example": "0"
    },
    "is_cross_border": {
      "type": "java.lang.Integer",
      "description": "是否是海淘订单，1-是，0-否",
      "example": "1"
    },
    "tariff": {
      "type": "java.lang.Long",
      "description": "订单关税，单位：分",
      "example": "200"
    },
    "has_freight_insurance": {
      "type": "java.lang.Boolean",
      "description": "退货是否包运费，true：是，false：否",
      "example": "false"
    },
    "buy_way_desc": {
      "type": "java.lang.String",
      "description": "支付方式，0:默认值,未支付; 1:微信自有支付; 2:支付宝wap; 3:支付宝wap; 5:财付通; 7:代付; 8:联动优势; 9:货到付款; 10:大账号代销; 11:受理模式; 12:百付宝; 13:sdk支付; 14:合并付货款; 15:赠品; 16:优惠兑换; 17:自动付货款; 18:爱学贷; 19:微信wap; 20:微信红包支付; 21:返利; 22:ump红包; 24:易宝支付; 25:储值卡; 27:qq支付; 28:有赞E卡支付; 29:微信条码; 30:支付宝条码; 33:礼品卡支付; 35:储值卡（会员余额）; 37:银行卡支付;72:微信扫码二维码支付; 100:代收账户; 300:储值账户; 400:保证金账户; 101:收款码; 102:微信; 103:支付宝; 104:刷卡; 105:二维码台卡; 106:储值卡（线下场景使用）; 107:有赞E卡; 110:标记收款-自有微信支付; 111:标记收款-自有支付宝; 112:标记收款-自有POS刷卡; 113:通联刷卡支付; 115:有赞零钱; 200:记账账户; 201:现金;202:组合支付",
      "example": "微信支付"
    },
    "is_commission_order": {
      "type": "java.lang.Boolean",
      "description": "是否是分佣订单",
      "example": "true"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺ID",
      "example": "1234575"
    },
    "settle_amount": {
      "type": "java.lang.Long",
      "description": "订单分佣成功时的结算金额 单位分",
      "example": "1000"
    },
    "pay_status": {
      "type": "java.lang.Integer",
      "description": "10:待付款30:已付款40:已发货50:已签收70:维权中80:已退款90:订单关闭",
      "example": "10"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "order_no": "E20190318135014056100001",
  "postage": "0",
  "is_cross_border": "1",
  "tariff": "200",
  "has_freight_insurance": "false",
  "buy_way_desc": "微信支付",
  "is_commission_order": "true"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.ad.order.detail.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ad.order.detail.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/714)*