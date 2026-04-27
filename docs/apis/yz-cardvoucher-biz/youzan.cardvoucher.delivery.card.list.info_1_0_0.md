---
apiName: "youzan.cardvoucher.delivery.card.list.info.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "pageQueryUserDeliveryCards"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3380"
---

# youzan.cardvoucher.delivery.card.list.info.1.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

分页查询店铺下用户的提货卡列表，返回结果中包含了可用和不可用的提货卡数据，如果提货卡不可用，结果中会告知不可用的原因，方便商家进行识别筛选。在使用提货卡核销功能时，需先通过该接口查询用户的提货卡信息。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.list.info/1.0.0`

**请求参数**（7 个）:

```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "用户Id，用户手机号与用户Id二选一必填",
      "example": "7j3Gi1UH732330877366837248"
    },
    "mobile": {
      "type": "java.lang.String",
      "description": "用户手机号，用户手机号与用户Id二选一必填",
      "example": "18573028713"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "储值卡号",
      "example": "310200461055007"
    },
    "max_left_delivery_num": {
      "type": "java.lang.Long",
      "description": "最大剩余可提货数量",
      "example": "3"
    },
    "min_left_delivery_num": {
      "type": "java.lang.Long",
      "description": "最小剩余可提货数量",
      "example": "1"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "页号，不传默认为1，最大可传200",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "页码，不传默认为10，最大可传50",
      "example": "20"
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
      "type": "com.youzan.api.common.vo.ListWithLongPaginatorVO<T>",
      "description": "返回数据",
      "example": ""
    },
    "paginator": {
      "type": "com.youzan.api.common.response.LongPaginator",
      "description": "分页信息",
      "example": ""
    },
    "page": {
      "type": "long",
      "description": "页号，默认为1，最大为200",
      "example": "1"
    },
    "page_size": {
      "type": "long",
      "description": "页码，默认为10，最大为50",
      "example": "20"
    },
    "total_count": {
      "type": "long",
      "description": "数据总数",
      "example": "2"
    },
    "items": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenDeliveryCardQueryResultDTO>",
      "description": "提货卡列表信息",
      "example": ""
    },
    "mobile": {
      "type": "java.lang.String",
      "description": "手机号码",
      "example": "18573028713"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "卡号",
      "example": "310200461055007"
    },
    "original_price": {
      "type": "java.lang.Long",
      "description": "卡面额（单位为分）",
      "example": "10000"
    },
    "card_name": {
      "type": "java.lang.String",
      "description": "卡模板名称",
      "example": "提货卡"
    },
    "status": {
      "type": "java.lang.String",
      "description": "卡状态（normal：正常；freeze：停用；cmpfrz：冻结；close：销卡；receding：退卡中；receded：已退卡）",
      "example": "normal"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "paginator": "",
  "page": "1",
  "page_size": "20",
  "total_count": "2",
  "items": "",
  "mobile": "18573028713",
  "card_no": "310200461055007"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.list.info/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.list.info/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3380)*