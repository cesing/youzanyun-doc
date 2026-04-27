---
apiName: "youzan.bigdata.team.org.data.list.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "交易订单"
method: "getSpecialFacadeShopReportData"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3785"
---

# youzan.bigdata.team.org.data.list.1.0.0

> **所属分组**: 交易订单  **所属应用**: seller-datacenter

---

## 1. 场景说明

云上专柜定制交易数据报表

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.team.org.data.list/1.0.0`

**请求参数**（5 个）:

```json
{
  "type": "object",
  "properties": {
    "team_org_ids": {
      "type": "java.util.List<java.lang.Long>",
      "description": "专柜id列表",
      "example": "[111,222]"
    },
    "start_date": {
      "type": "java.lang.String",
      "description": "开始时间",
      "example": "2022-05-01"
    },
    "end_date": {
      "type": "java.lang.String",
      "description": "结束时间",
      "example": "2022-07-01"
    },
    "page": {
      "type": "java.lang.Integer",
      "description": "查询页",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "每页条目数",
      "example": "20"
    }
  },
  "required": [
    "team_org_ids",
    "start_date",
    "end_date",
    "page",
    "page_size"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.base.api.model.async.AsyncResult<T>",
      "description": "调用返回的异步结果数据,",
      "example": ""
    },
    "response_id": {
      "type": "java.lang.String",
      "description": "请求返回标识，用于当status=0时，轮询查询",
      "example": "1111111"
    },
    "result": {
      "type": "com.youzan.bigdata.datacenter.proxy.api.model.retailreport.SpecialFacadeReportDataModel",
      "description": "请求结果，当status=1时，有结果，",
      "example": ""
    },
    "special_facade_report_detail_models": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.proxy.api.model.retailreport.SpecialFacadeReportDetailModel>",
      "description": "数据对象",
      "example": ""
    },
    "parent_org_id": {
      "type": "java.lang.String",
      "description": "父专柜id，通过\"_\"拼接",
      "example": "父专柜id"
    },
    "parent_team_org_name": {
      "type": "java.lang.String",
      "description": "父专柜id名称，多级拼接",
      "example": "父机构名称（区域名称）"
    },
    "team_org_id": {
      "type": "java.lang.String",
      "description": "专柜id",
      "example": "专柜id"
    },
    "team_org_name": {
      "type": "java.lang.String",
      "description": "专柜名称",
      "example": "专柜名称"
    },
    "per_customer_price": {
      "type": "java.lang.Long",
      "description": "客单价",
      "example": "客单价"
    },
    "book_customer_num": {
      "type": "java.lang.Long",
      "description": "下单人数",
      "example": "下单人数"
    },
    "book_order_num": {
      "type": "java.lang.Long",
      "description": "下单笔数",
      "example": "下单笔数"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "response_id": "1111111",
  "result": "",
  "special_facade_report_detail_models": "",
  "parent_org_id": "父专柜id",
  "parent_team_org_name": "父机构名称（区域名称）",
  "team_org_id": "专柜id",
  "team_org_name": "专柜名称"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.team.org.data.list/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.team.org.data.list/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3785)*