---
apiName: "youzan.bigdata.datacenter.psmanage.search.pagesourcedetail.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3483"
---

# youzan.bigdata.datacenter.psmanage.search.pagesourcedetail.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

获取推广监控列表基本数据,不包含效果数据。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagesourcedetail/1.0.0`

**认证方式**: 凭证式

**请求参数**（7 个）:

```json
{
  "type": "object",
  "properties": {
    "ps_name": {
      "type": "java.lang.String",
      "description": "推广监控名称",
      "example": "推广1"
    },
    "dcps_list": {
      "type": "java.util.List<java.lang.String>",
      "description": "dcps列表",
      "example": "[\"2118722746287589378.200001\"]"
    },
    "ps_status": {
      "type": "java.lang.Integer",
      "description": "推广监控状态1:推广中;2:推广结束",
      "example": "1"
    },
    "start_day": {
      "type": "java.lang.String",
      "description": "查询开始时间",
      "example": "2021-12-01"
    },
    "end_day": {
      "type": "java.lang.String",
      "description": "查询结束时间",
      "example": "2021-12-01"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "分页信息",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "分页信息",
      "example": "100"
    }
  },
  "required": [
    "page_no",
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
      "type": "com.youzan.api.common.vo.ListWithPaginatorVO<T>",
      "description": "结果",
      "example": ""
    },
    "paginator": {
      "type": "com.youzan.api.common.response.Paginator",
      "description": "分页信息",
      "example": ""
    },
    "page_no": {
      "type": "int",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "int",
      "description": "每页条数。最大不能超过200",
      "example": "100"
    },
    "total_count": {
      "type": "int",
      "description": "总数",
      "example": "1000"
    },
    "items": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.base.api.model.psmanage.yun.YunPsPageSourceModel>",
      "description": "推广监控列表",
      "example": ""
    },
    "id": {
      "type": "java.lang.Long",
      "description": "自增id",
      "example": "1"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "dcps": {
      "type": "java.lang.String",
      "description": "dcps",
      "example": "2118722746287589378.200001"
    },
    "ps_name": {
      "type": "java.lang.String",
      "description": "推广名称",
      "example": "推广1"
    },
    "source_id": {
      "type": "java.lang.Long",
      "description": "推广渠道id,ps_sourceid",
      "example": "1"
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
  "page_size": "100",
  "total_count": "1000",
  "items": "",
  "id": "1",
  "kdt_id": "88888"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagesourcedetail/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagesourcedetail/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3483)*