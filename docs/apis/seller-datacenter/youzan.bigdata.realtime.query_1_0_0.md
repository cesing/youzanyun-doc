---
apiName: "youzan.bigdata.realtime.query.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "店铺信息"
method: "getRealTimeOverView"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4839"
---

# youzan.bigdata.realtime.query.1.0.0

> **所属分组**: 店铺信息  **所属应用**: seller-datacenter

---

## 1. 场景说明

实时分析的实时概况数据，主要包括浏览访问、成交转化、客户会员

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.realtime.query/1.0.0`

**请求参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "basic_param": {
      "type": "com.youzan.bigdata.datacenter.base.api.param.realtime.RealTimeParamV2",
      "description": "请求体",
      "example": ""
    },
    "current_day": {
      "type": "java.lang.Integer",
      "description": "不填则为今日实时format:yyyyMMdd",
      "example": "20250611"
    },
    "canal_type": {
      "type": "java.lang.Integer",
      "description": "线上线下：0线上；1线下；10全部",
      "example": "0"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "分页参数",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "每页数据量大小",
      "example": "10"
    },
    "team_level": {
      "type": "java.lang.Integer",
      "description": "店铺等级：0-总店或者管理单元;1-子店;",
      "example": "1"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺id",
      "example": "88888"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用",
      "example": "123456"
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "UUID",
      "example": "sadsadafdafdsfsd"
    },
    "operator": {
      "type": "java.lang.String",
      "description": "操作人名字",
      "example": "zhangsan"
    }
  },
  "required": [
    "current_day",
    "yz_open_id"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.base.api.model.realtime.RealTimeOverviewResult",
      "description": "数据",
      "example": ""
    },
    "current_day": {
      "type": "java.lang.Integer",
      "description": "日期，如：20250611",
      "example": "20250611"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "uv": {
      "type": "java.lang.Long",
      "description": "访客数",
      "example": "11"
    },
    "pv": {
      "type": "java.lang.Long",
      "description": "浏览量",
      "example": "11"
    },
    "new_member_uv": {
      "type": "java.lang.Long",
      "description": "新增会员数",
      "example": "11"
    },
    "hour": {
      "type": "java.lang.Integer",
      "description": "小时，如：10",
      "example": "12"
    },
    "yester_day": {
      "type": "com.youzan.bigdata.datacenter.base.api.model.realtime.RealTimeOverviewModel",
      "description": "昨天",
      "example": ""
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "current_day": "20250611",
  "kdt_id": "88888",
  "uv": "11",
  "pv": "11",
  "new_member_uv": "11",
  "hour": "12"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.realtime.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.realtime.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4839)*