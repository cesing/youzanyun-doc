---
apiName: "youzan.bigdata.team.flowoverview.query.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "数据分析"
method: "getTeamFlowOverview"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1466"
---

# youzan.bigdata.team.flowoverview.query.1.0.0

> **所属分组**: 数据分析  **所属应用**: seller-datacenter

---

## 1. 场景说明

流量概览渠道维度数据接口(不支持合伙人)
1.订单相关指标（如下单人数）以下单时间统计，支付相关指标（如支付人数）以支付成功时间统计（拼团订单成团算支付、货到付款订单发货算支付）。订单查询页面根据下单时间查询对应订单。若顾客当日下单、次日支付，则下单与支付数据会有一天时间差，请注意区分。 2.由于是离线数据，建议每天早晨9：00后再请求。
3.当响应参数返回值有特殊数值的-999999d时，开发者可以理解数据值等于空。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.team.flowoverview.query/1.0.0`

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "channel_type": {
      "type": "java.lang.String",
      "description": "渠道类型，appsdk-app开店，weapp-小程序，h5-h5，all-全，choice-精选，",
      "example": "weapp"
    },
    "node_kdt_id": {
      "type": "java.lang.Long",
      "description": "有赞连锁网店店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个网店。单店、连锁总部查询汇总数据不传该字段",
      "example": "8888"
    },
    "date_type": {
      "type": "java.lang.Integer",
      "description": "日期类型，枚举：1-天，2-周，3-月，4-近7天，5-近30天",
      "example": "1"
    },
    "current_day": {
      "type": "java.lang.Integer",
      "description": "统计时间。时间格式：yyyyMMdd。date_type是周则传递自然周的周一，月则传递自然月的一号，近七天、近三十天传递该时间范围的第一天。",
      "example": "20201022"
    }
  },
  "required": [
    "date_type",
    "current_day"
  ]
}
```

**响应参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.base.api.model.flow.overview.TeamOverviewModel",
      "description": "返回数据体",
      "example": ""
    },
    "uv": {
      "type": "long",
      "description": "访客数",
      "example": "1000"
    },
    "new_team_total_uv": {
      "type": "java.lang.Long",
      "description": "新访客数",
      "example": "10"
    },
    "pv": {
      "type": "long",
      "description": "浏览量",
      "example": "100"
    },
    "stay_time_avg": {
      "type": "java.lang.Double",
      "description": "平均停留时长，单位秒",
      "example": "19.28"
    },
    "per_capita_browsing": {
      "type": "java.lang.Double",
      "description": "人均浏览量",
      "example": "20.8"
    },
    "click_miss_rate": {
      "type": "java.lang.Double",
      "description": "跳失率",
      "example": "54.88"
    },
    "paid_order_uv": {
      "type": "long",
      "description": "支付人数",
      "example": "20"
    },
    "total_pay_rate": {
      "type": "java.lang.Double",
      "description": "访问支付转化率",
      "example": "39.89"
    },
    "share_total_pv": {
      "type": "long",
      "description": "分享访问次数",
      "example": "19"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "uv": "1000",
  "new_team_total_uv": "10",
  "pv": "100",
  "stay_time_avg": "19.28",
  "per_capita_browsing": "20.8",
  "click_miss_rate": "54.88",
  "paid_order_uv": "20"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.team.flowoverview.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.team.flowoverview.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1466)*