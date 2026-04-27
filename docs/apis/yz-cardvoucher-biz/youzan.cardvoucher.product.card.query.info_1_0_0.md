---
apiName: "youzan.cardvoucher.product.card.query.info.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "pageQueryProductCardList"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2830"
---

# youzan.cardvoucher.product.card.query.info.1.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

分页查询主卡下的子卡信息，默认查询处于正常状态下的子卡信息

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.product.card.query.info/1.0.0`

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "group_no": {
      "type": "java.lang.String",
      "description": "主卡号",
      "example": "310200462159949"
    },
    "status": {
      "type": "java.lang.Integer",
      "description": "子卡状态：0-初始化；1-正常；2-已回收（失效）；3-已核销；4-被冻结（改状态暂没有使用）；5-激活失败；6-无效卡（作废），默认取值1",
      "example": "1"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "页号，默认取1，取值区间是[1,200]",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "分页大小，默认取10，取值区间是[1,50]",
      "example": "10"
    }
  },
  "required": [
    "group_no"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.api.common.vo.ListWithLongPaginatorVO<T>",
      "description": "返回结果",
      "example": ""
    },
    "paginator": {
      "type": "com.youzan.api.common.response.LongPaginator",
      "description": "分页信息",
      "example": ""
    },
    "page_no": {
      "type": "long",
      "description": "页号",
      "example": "1"
    },
    "page_size": {
      "type": "long",
      "description": "分页大小",
      "example": "10"
    },
    "total_count": {
      "type": "long",
      "description": "数据总数",
      "example": "1"
    },
    "items": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenProductCardDTO>",
      "description": "数据",
      "example": ""
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "子卡号",
      "example": "210200462162308"
    },
    "create_time": {
      "type": "java.util.Date",
      "description": "创建时间",
      "example": "1620791833000"
    },
    "balance": {
      "type": "java.lang.Double",
      "description": "余额（元）",
      "example": "10.0"
    },
    "success": {
      "type": "boolean",
      "description": "接口调用是否成功",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "接口调用结果码",
      "example": "200"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "paginator": "",
  "page_no": "1",
  "page_size": "10",
  "total_count": "1",
  "items": "",
  "card_no": "210200462162308",
  "create_time": "1620791833000"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.product.card.query.info/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.product.card.query.info/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2830)*