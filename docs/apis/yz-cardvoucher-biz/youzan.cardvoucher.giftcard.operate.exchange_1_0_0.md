---
apiName: "youzan.cardvoucher.giftcard.operate.exchange.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4029"
---

# youzan.cardvoucher.giftcard.operate.exchange.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

礼品卡兑换：支持卡密兑换和扫码兑换，仅进行兑换，不会自动触发激活。可通过商家后台批量制卡后生成的兑换信息进行调用，支持电子卡和实体卡兑换。
备注：如扩展点兑换流程中衔接本接口，返回的电子卡号不可直接作为用户的卡号返回，否则选择此卡号支付时会走到标品，可通过自定义卡号映射或加固定前/后缀解决，非扩展点流程对接无需关注本备注。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.operate.exchange/1.0.0`

**认证方式**: 凭证式

**请求参数**（5 个）:

```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】",
      "example": "MVJ5w0uy585097513770430464"
    },
    "card_no_or_serial_num": {
      "type": "java.lang.String",
      "description": "卡密兑换时必填：可填批量制卡后的电子卡的序列号或实体卡的卡号进行兑换序列号",
      "example": "aaaaaaa"
    },
    "check_code": {
      "type": "java.lang.String",
      "description": "卡密兑换时必填：兑换码",
      "example": "1111111"
    },
    "card_random": {
      "type": "java.lang.String",
      "description": "扫码兑换时必填：卡号随机数",
      "example": ""
    },
    "exchange_type": {
      "type": "java.lang.Integer",
      "description": "兑换类型：0(卡密兑换) 1(扫码兑换)",
      "example": "0"
    }
  },
  "required": [
    "yz_open_id",
    "card_no_or_serial_num",
    "exchange_type"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.ExchangeCardResultDTO",
      "description": "",
      "example": ""
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "电子卡卡号",
      "example": "1234567890"
    },
    "exchange_status": {
      "type": "java.lang.Integer",
      "description": "兑换状态：2(兑换成功，且是首次被兑换成功) 3(卡已经被兑换过，且是当前用户兑换的) 4(卡已经被兑换过，且是被他人兑换的) 5(卡已被失效，无法兑换)",
      "example": "2"
    },
    "exchange_date": {
      "type": "java.util.Date",
      "description": "兑换时间-毫秒级时间戳",
      "example": "1680863031000"
    },
    "template_no": {
      "type": "java.lang.String",
      "description": "卡模板号",
      "example": "1234567899"
    },
    "template_name": {
      "type": "java.lang.String",
      "description": "卡模板名称",
      "example": "测试卡模板"
    },
    "denomination": {
      "type": "java.lang.Long",
      "description": "卡面额-分",
      "example": "100"
    },
    "principal": {
      "type": "java.lang.Long",
      "description": "卡内本金-分",
      "example": "60"
    },
    "bonus": {
      "type": "java.lang.Long",
      "description": "卡内赠送金-分",
      "example": "40"
    },
    "expired_date": {
      "type": "java.util.Date",
      "description": "批量制卡时卡的有效期截止日期-毫秒时间戳",
      "example": "1680863031"
    },
    "support_give": {
      "type": "java.lang.Boolean",
      "description": "卡模板配置的礼品卡是否支持赠送：true支持，false不支持",
      "example": "true"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "card_no": "1234567890",
  "exchange_status": "2",
  "exchange_date": "1680863031000",
  "template_no": "1234567899",
  "template_name": "测试卡模板",
  "denomination": "100",
  "principal": "60"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.operate.exchange/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.operate.exchange/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4029)*