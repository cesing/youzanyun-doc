---
apiName: "youzan.cardvoucher.giftcard.query.buyercenter.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4058"
---

# youzan.cardvoucher.giftcard.query.buyercenter.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

礼品卡分页查询：可分页查询礼品卡列表。与个人中心->余额->礼品卡->购买礼品卡页面中的查询效果一致。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buyercenter/1.0.0`

**认证方式**: 凭证式

**请求参数**（2 个）:

```json
{
  "type": "object",
  "properties": {
    "page": {
      "type": "int",
      "description": "页码，从1开始",
      "example": "1"
    },
    "page_size": {
      "type": "int",
      "description": "页数。默认10条，最大不能超过50，建议使用默认分页",
      "example": "10"
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
      "description": "数据",
      "example": ""
    },
    "paginator": {
      "type": "com.youzan.api.common.response.LongPaginator",
      "description": "分页信息",
      "example": ""
    },
    "page": {
      "type": "long",
      "description": "页码，从1开始正整数",
      "example": "1"
    },
    "page_size": {
      "type": "long",
      "description": "页数。默认10条",
      "example": "10"
    },
    "total_count": {
      "type": "long",
      "description": "查询获得数据总条数",
      "example": "2"
    },
    "items": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.open.response.DealQueryBuyCenterOpenResponse>",
      "description": "卡信息",
      "example": ""
    },
    "template_name": {
      "type": "java.lang.String",
      "description": "卡名称",
      "example": "礼品卡"
    },
    "template_img": {
      "type": "java.lang.String",
      "description": "封面图片",
      "example": "https://img01.yzcdn.cn/upload_files/2023/02/16/Fkv8lU-C6PDnceu_RbmnPMGsLs5n.png"
    },
    "max_original_price": {
      "type": "java.lang.Long",
      "description": "卡最高面额(单位:分)",
      "example": "100000"
    },
    "min_original_price": {
      "type": "java.lang.Long",
      "description": "卡最低面额(单位:分)",
      "example": "100000"
    },
    "template_no": {
      "type": "java.lang.String",
      "description": "卡模板Id",
      "example": "110200549443060"
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
  "page_size": "10",
  "total_count": "2",
  "items": "",
  "template_name": "礼品卡",
  "template_img": "https://img01.yzcdn.cn/upload_files/2023/02/16/Fkv8lU-C6PDnceu_RbmnPMGsLs5n.png"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buyercenter/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buyercenter/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4058)*