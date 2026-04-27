---
apiName: "youzan.appstore.sevicedemand.query.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "大客CRM"
method: "getDemandListByTime"
timeout: 5000
authType: "无认证"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2829"
---

# youzan.appstore.sevicedemand.query.1.0.0

> **所属分组**: 大客CRM  **所属应用**: appstore

---

## 1. 场景说明

根据时间获取需求列表(连接器调用)

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.sevicedemand.query/1.0.0`

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "start_time": {
      "type": "java.util.Date",
      "description": "开始时间筛选条件，默认1970-01-01 08:00:00",
      "example": "2021-05-07 00:00:00"
    },
    "end_time": {
      "type": "java.util.Date",
      "description": "结束时间筛选条件，默认当前时间",
      "example": "2021-05-07 00:00:00"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "查询时当前的页数（分页查询接口必填）",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "每页展示的行数（分页查询接口必填）",
      "example": "10"
    }
  },
  "required": [
    "start_time"
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
      "description": "data",
      "example": ""
    },
    "paginator": {
      "type": "com.youzan.api.common.response.Paginator",
      "description": "分页",
      "example": ""
    },
    "page": {
      "type": "int",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "int",
      "description": "页数",
      "example": "10"
    },
    "total_count": {
      "type": "int",
      "description": "总数",
      "example": "10"
    },
    "items": {
      "type": "java.util.List<com.youzan.cloud.appstore.api.dto.response.demand.ServiceDemandDTO>",
      "description": "需求列表",
      "example": ""
    },
    "id": {
      "type": "java.lang.Long",
      "description": "主键id",
      "example": "1"
    },
    "demand_no": {
      "type": "java.lang.String",
      "description": "需求编号",
      "example": "864642465397448704"
    },
    "demand_detail": {
      "type": "java.lang.String",
      "description": "需求信息",
      "example": "我需要10人的客服团队"
    },
    "mobile": {
      "type": "java.lang.String",
      "description": "联系人手机号码",
      "example": "13000000000"
    },
    "status": {
      "type": "java.lang.Integer",
      "description": "需求状态",
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
  "page": "1",
  "page_size": "10",
  "total_count": "10",
  "items": "",
  "id": "1",
  "demand_no": "864642465397448704"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.sevicedemand.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.appstore.sevicedemand.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2829)*