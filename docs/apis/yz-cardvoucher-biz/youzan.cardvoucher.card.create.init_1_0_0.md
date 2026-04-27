---
apiName: "youzan.cardvoucher.card.create.init.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "createCard"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3926"
---

# youzan.cardvoucher.card.create.init.1.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

储值礼品卡制卡接口，会创建未激活的礼品卡且没有归属人，该礼品卡可以在商家后台 储值查询-卡查询中根据返回的卡号查询信息
一般配合youzan.cardvoucher.giftcard.marketing.issue接口进行后续的发卡使用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.create.init/1.0.0`

**请求参数**（7 个）:

```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.request.CreateGiftCardOpenRequest",
      "description": "请求参数",
      "example": ""
    },
    "request_no": {
      "type": "java.lang.String",
      "description": "请求单号，是幂等单号要求唯一",
      "example": "Unique123456"
    },
    "template_no": {
      "type": "java.lang.String",
      "description": "卡模板号",
      "example": "11111111"
    },
    "img_url_no": {
      "type": "java.lang.Integer",
      "description": "制卡卡模板选择第几个封面，从1开始计数，可不填，不填默认取第一个封面图片",
      "example": "1"
    },
    "price": {
      "type": "java.lang.Long",
      "description": "制卡卡模板选择的面额，单位分，不传默认取最小的面额",
      "example": "100"
    },
    "operator_name": {
      "type": "java.lang.String",
      "description": "操作员姓名",
      "example": "aaa"
    },
    "operator_mobile": {
      "type": "java.lang.String",
      "description": "操作员手机号",
      "example": "12345678901"
    }
  },
  "required": [
    "request_no",
    "template_no",
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
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenCreateCardResultDTO",
      "description": "接口返回数据",
      "example": ""
    },
    "request_no": {
      "type": "java.lang.String",
      "description": "请求单号",
      "example": "Unique123456"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "制成的卡号",
      "example": "987654321"
    },
    "status": {
      "type": "java.lang.String",
      "description": "制卡状态SUCCESS:成功FAIL:失败ING:制卡中",
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
      "example": "制卡成功"
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
      "description": "",
      "example": ""
    },
    "error_data": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "",
      "example": ""
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "request_no": "Unique123456",
  "card_no": "987654321",
  "status": "SUCCESS",
  "code": "200",
  "msg": "制卡成功",
  "success": "true"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.card.create.init/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.create.init/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3926)*