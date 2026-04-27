---
apiName: "youzan.bigdata.datacenter.psmanage.search.pagepsdata.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3570"
---

# youzan.bigdata.datacenter.psmanage.search.pagepsdata.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

分页获取多个人推广监控效果数据

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagepsdata/1.0.0`

**认证方式**: 凭证式

**请求参数**（8 个）:

```json
{
  "type": "object",
  "properties": {
    "dcps_list": {
      "type": "java.util.List<java.lang.String>",
      "description": "dcps号",
      "example": "[\"2118722746287589378.200001\"]"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "每页条数。最大不能超过200",
      "example": "1"
    },
    "attribution_period": {
      "type": "java.lang.Integer",
      "description": "归因周期当天:1,七天:7,15天:15,30天:30",
      "example": "1"
    },
    "statistical_scope": {
      "type": "java.lang.Integer",
      "description": "统计范围全部转化数据：空，推广页直接转化数据：2，连带销售：3",
      "example": "2"
    },
    "attribution_type": {
      "type": "java.lang.Integer",
      "description": "归因方式首次1，末次2",
      "example": "1"
    },
    "start_day": {
      "type": "java.lang.String",
      "description": "开始时间yyyy-MM-dd",
      "example": "2021-12-01"
    },
    "end_day": {
      "type": "java.lang.String",
      "description": "结束时间yyyy-MM-dd",
      "example": "2021-12-02"
    }
  },
  "required": [
    "page_no",
    "page_size",
    "attribution_period",
    "attribution_type",
    "start_day",
    "end_day"
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
      "description": "结果数据",
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
      "description": "每页条数",
      "example": "10"
    },
    "total_count": {
      "type": "int",
      "description": "总条数",
      "example": "100"
    },
    "items": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.base.api.model.psmanage.chain.PsMonitorEffectDTO>",
      "description": "结果列表",
      "example": ""
    },
    "dcps": {
      "type": "java.lang.String",
      "description": "推广监控唯一标识",
      "example": "2118722746287589378.200001"
    },
    "ps_name": {
      "type": "java.lang.String",
      "description": "推广监控名称",
      "example": "微信推广"
    },
    "channel_name": {
      "type": "java.lang.String",
      "description": "所属渠道名称",
      "example": "微信"
    },
    "tag_name": {
      "type": "java.lang.String",
      "description": "所属标签名称",
      "example": "推广标签"
    },
    "ps_cost": {
      "type": "java.lang.Long",
      "description": "推广花费",
      "example": "10"
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
  "total_count": "100",
  "items": "",
  "dcps": "2118722746287589378.200001",
  "ps_name": "微信推广"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagepsdata/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagepsdata/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3570)*