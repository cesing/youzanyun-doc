---
apiName: "youzan.bigdata.team.flowoverview.query.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "data_center"
method: "getTeamFlowOverview"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2020-10-23"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1466"
---
# youzan.bigdata.team.flowoverview.query.1.0.0
> **所属分组**: data_center　**所属应用**: seller-datacenter
---
## 1. 场景说明
流量概览渠道维度数据接口(不支持合伙人)
1.订单相关指标（如下单人数）以下单时间统计，支付相关指标（如支付人数）以支付成功时间统计（拼团订单成团算支付、货到付款订单发货算支付）。订单查询页面根据下单时间查询对应订单。若顾客当日下单、次日支付，则下单与支付数据会有一天时间差，请注意区分。 2.由于是离线数据，建议每天早晨9：00后再请求。
3.当响应参数返回值有特殊数值的-999999d时，开发者可以理解数据值等于空。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.team.flowoverview.query/1.0.0`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "channel_type": {
      "type": "string",
      "description": "渠道类型，appsdk-app开店，weapp-小程序，h5-h5，all-全，choice-精选，",
      "example": "weapp"
    },
    "node_kdt_id": {
      "type": "integer",
      "description": "有赞连锁网店店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个网店。单店、连锁总部查询汇总数据不传该字段",
      "example": "8888"
    },
    "date_type": {
      "type": "integer",
      "description": "日期类型，枚举：1-天，2-周，3-月，4-近7天，5-近30天",
      "example": "1"
    },
    "current_day": {
      "type": "integer",
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
**请求参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `channel_type` | `string` | ❌ | `weapp` | 渠道类型，appsdk-app开店，weapp-小程序，h5-h5，all-全，choice-精选， |
| `node_kdt_id` | `integer` | ❌ | `8888` | 有赞连锁网店店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个网店。单店、连锁总部查询汇总数据不传该字段 |
| `date_type` | `integer` | ✅ | `1` | 日期类型，枚举：1-天，2-周，3-月，4-近7天，5-近30天 |
| `current_day` | `integer` | ✅ | `20201022` | 统计时间。时间格式：yyyyMMdd。date_type是周则传递自然周的周一，月则传递自然月的一号，近七天、近三十天传递该时间范围的第一天。 |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "返回数据体"
    },
    "uv": {
      "type": "integer",
      "description": "访客数",
      "example": "1000"
    },
    "new_team_total_uv": {
      "type": "integer",
      "description": "新访客数",
      "example": "10"
    },
    "pv": {
      "type": "integer",
      "description": "浏览量",
      "example": "100"
    },
    "stay_time_avg": {
      "type": "number",
      "description": "平均停留时长，单位秒",
      "example": "19.28"
    },
    "per_capita_browsing": {
      "type": "number",
      "description": "人均浏览量",
      "example": "20.8"
    },
    "click_miss_rate": {
      "type": "number",
      "description": "跳失率",
      "example": "54.88"
    },
    "paid_order_uv": {
      "type": "integer",
      "description": "支付人数",
      "example": "20"
    },
    "total_pay_rate": {
      "type": "number",
      "description": "访问支付转化率",
      "example": "39.89"
    },
    "share_total_pv": {
      "type": "integer",
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
**响应参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 返回数据体 |
| `uv` | `integer` | ❌ | `1000` | 访客数 |
| `new_team_total_uv` | `integer` | ❌ | `10` | 新访客数 |
| `pv` | `integer` | ❌ | `100` | 浏览量 |
| `stay_time_avg` | `number` | ❌ | `19.28` | 平均停留时长，单位秒 |
| `per_capita_browsing` | `number` | ❌ | `20.8` | 人均浏览量 |
| `click_miss_rate` | `number` | ❌ | `54.88` | 跳失率 |
| `paid_order_uv` | `integer` | ❌ | `20` | 支付人数 |
| `total_pay_rate` | `number` | ❌ | `39.89` | 访问支付转化率 |
| `share_total_pv` | `integer` | ❌ | `19` | 分享访问次数 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.team.flowoverview.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "channel_type": "weapp",\n  "node_kdt_id": "8888",\n  "date_type": "1",\n  "current_day": "20201022"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.team.flowoverview.query/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "channel_type": "weapp",
    "node_kdt_id": "8888",
    "date_type": "1",
    "current_day": "20201022"
}

resp = requests.post(url, json=payload, headers=headers)
print(resp.json())
```
---
## 5. 错误码
| 错误码 | 类型 | 说明 |
|--------|------|------|
| 10001 | `SYSTEM_ERROR` | 系统内部错误 |
| 10002 | `INVALID_PARAMETER` | 参数错误 |
| 10003 | `UNAUTHORIZED` | 未授权或授权已过期 |
| 10004 | `PERMISSION_DENIED` | 无权限调用此接口 |
| 10005 | `RESOURCE_NOT_FOUND` | 请求的资源不存在 |
| 20001 | `RATE_LIMIT_EXCEEDED` | 调用频率超限 |
| 20002 | `QUOTA_EXCEEDED` | 接口配额已用完 |
---
## 6. 权限与计费

**接口计费状态：未知（请以官网实际披露为准）。**

**拥有此API的能力包：** 暂无数据（请以官网实际披露为准）。

---
## 7. 权限说明

**应用类目 → 权限类型：**

| 应用类目 | 权限类型 |
|----------|----------|
| 有赞微商城、有赞零售、有赞教育、有赞美业 | 普通自研商家（基础权益） |
| 大客户定制接口、美业大客户定制、零售大客户定制、收款二维码-大客专用 | 大客定制接口（需购买大客套餐） |
| 客户关系CRM、门店POS | iPaaS 套餐权益（需购买 iPaaS 套餐） |

> 权限数据来源：[有赞云能力包说明](https://doc.youzanyun.com/detail/content/API/0/120)