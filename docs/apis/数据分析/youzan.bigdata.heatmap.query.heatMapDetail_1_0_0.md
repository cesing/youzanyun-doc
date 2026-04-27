---
apiName: "youzan.bigdata.heatmap.query.heatMapDetail.1.0.0"
version: "1.0.0"
appName: "ebiz-stats"
apiGroup: "数据分析"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4076"
---

# youzan.bigdata.heatmap.query.heatMapDetail.1.0.0

> **所属分组**: 数据分析

---

## 1. 场景说明

根据热力图id获取各个渠道下的页面的每个点位点击情况。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.heatMapDetail/1.0.0`

**认证方式**: 凭证式

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "java.lang.Long",
      "description": "热力图id，而非页面id",
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
    "start_time",
    "end_time",
    "sdk_type"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.ebiz.stats.domain.heatmap.HeatMapBO",
      "description": "业务数据内容",
      "example": ""
    },
    "hot_zone": {
      "type": "java.util.List<com.youzan.ebiz.stats.domain.heatmap.HeatMapBO.HotZoneBO>",
      "description": "热点图坐标信息",
      "example": ""
    },
    "loc_x": {
      "type": "java.lang.Integer",
      "description": "x轴",
      "example": "1"
    },
    "loc_y": {
      "type": "java.lang.Integer",
      "description": "y轴",
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
    },
    "is_fix": {
      "type": "java.lang.Boolean",
      "description": "是否是浮层，true为浮层",
      "example": "true"
    },
    "page_info": {
      "type": "com.youzan.ebiz.stats.domain.heatmap.HeatMapBO.PageInfo",
      "description": "热点图页面信息",
      "example": ""
    },
    "page_type": {
      "type": "java.lang.String",
      "description": "页面类型",
      "example": "f"
    },
    "page_id": {
      "type": "java.lang.Long",
      "description": "页面id",
      "example": "1"
    },
    "page_name": {
      "type": "java.lang.String",
      "description": "页面名称",
      "example": "主页"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "hot_zone": "",
  "loc_x": "1",
  "loc_y": "1",
  "click_pv": "1",
  "click_uv": "1",
  "is_fix": "true",
  "page_info": ""
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.heatMapDetail/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.heatMapDetail/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4076)*