---
apiName: "youzan.bigdata.heatmap.query.pageData.1.0.0"
version: "1.0.0"
appName: "ebiz-stats"
apiGroup: "数据分析"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4078"
---

# youzan.bigdata.heatmap.query.pageData.1.0.0

> **所属分组**: 数据分析

---

## 1. 场景说明

根据热力图id获取页面级别统计信息：点击人数、点击次数、浏览量、访客数等

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.pageData/1.0.0`

**认证方式**: 凭证式

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "java.lang.Long",
      "description": "定制页面id，而非页面id",
      "example": "1"
    },
    "start_time": {
      "type": "java.lang.Integer",
      "description": "开始时间，格式YYYYMMdd",
      "example": "20230511"
    },
    "end_time": {
      "type": "java.lang.Integer",
      "description": "结束时间，格式YYYYMMdd",
      "example": "20230511"
    },
    "sdk_type": {
      "type": "java.lang.String",
      "description": "渠道筛选条件。枚举值小程序：weapp、 其他：js",
      "example": "weapp"
    }
  },
  "required": [
    "sdk_type"
  ]
}
```

**响应参数**（6 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.ebiz.stats.domain.heatmap.StatsBO",
      "description": "业务数据内容",
      "example": ""
    },
    "total_stats": {
      "type": "com.youzan.ebiz.stats.domain.heatmap.StatsBO.MetricsBO",
      "description": "汇总值",
      "example": ""
    },
    "total_uv": {
      "type": "java.lang.Long",
      "description": "访客数",
      "example": "1"
    },
    "total_pv": {
      "type": "java.lang.Long",
      "description": "浏览量",
      "example": "1"
    },
    "click_pv": {
      "type": "java.lang.Long",
      "description": "点击次数",
      "example": "1"
    },
    "click_uv": {
      "type": "java.lang.Long",
      "description": "点击人数",
      "example": "1"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "total_stats": "",
  "total_uv": "1",
  "total_pv": "1",
  "click_pv": "1",
  "click_uv": "1"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.pageData/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.pageData/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4078)*