---
apiName: "youzan.bigdata.team.flowoverview.query.1.0.0"
version: "1.0.0"
status: "已上线"
appName: "seller-datacenter"
apiGroup: "data_center"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.flow.yun.YunTeamFlowService"
method: "getTeamFlowOverview"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2020-10-23"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1466"
---
# youzan.bigdata.team.flowoverview.query.1.0.0
> **所属分组**: data_center　**所属应用**: seller-datacenter　**状态**: 已上线
---
## 1. 场景说明
流量概览渠道维度数据接口(不支持合伙人)
1.订单相关指标（如下单人数）以下单时间统计，支付相关指标（如支付人数）以支付成功时间统计（拼团订单成团算支付、货到付款订单发货算支付）。订单查询页面根据下单时间查询对应订单。若顾客当日下单、次日支付，则下单与支付数据会有一天时间差，请注意区分。 2.由于是离线数据，建议每天早晨9：00后再请求。
3.当响应参数返回值有特殊数值的-999999d时，开发者可以理解数据值等于空。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.team.flowoverview.query/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `channel_type` | `string` | ❌ 否 | `weapp` | 渠道类型，appsdk-app开店，weapp-小程序，h5-h5，all-全，choice-精选， |
| `node_kdt_id` | `integer` | ❌ 否 | `8888` | 有赞连锁网店店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个网店。单店、连锁总部查 |
| `date_type` | `integer` | ✅ 是 | `1` | 日期类型，枚举：1-天，2-周，3-月，4-近7天，5-近30天 |
| `current_day` | `integer` | ✅ 是 | `20201022` | 统计时间。时间格式：yyyyMMdd。date_type是周则传递自然周的周一，月则传递自然月的一号，近七天、近三十天传 |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "返回数据体"
    },
    "uv": {
      "type": "string",
      "description": "访客数",
      "example": "1000"
    },
    "new_team_total_uv": {
      "type": "integer",
      "description": "新访客数",
      "example": "10"
    },
    "pv": {
      "type": "string",
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
      "type": "string",
      "description": "支付人数",
      "example": "20"
    },
    "total_pay_rate": {
      "type": "number",
      "description": "访问支付转化率",
      "example": "39.89"
    },
    "share_total_pv": {
      "type": "string",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 返回数据体 |
| `uv` | `string` | ❌ 否 | `1000` | 访客数 |
| `new_team_total_uv` | `integer` | ❌ 否 | `10` | 新访客数 |
| `pv` | `string` | ❌ 否 | `100` | 浏览量 |
| `stay_time_avg` | `number` | ❌ 否 | `19.28` | 平均停留时长，单位秒 |
| `per_capita_browsing` | `number` | ❌ 否 | `20.8` | 人均浏览量 |
| `click_miss_rate` | `number` | ❌ 否 | `54.88` | 跳失率 |
| `paid_order_uv` | `string` | ❌ 否 | `20` | 支付人数 |
| `total_pay_rate` | `number` | ❌ 否 | `39.89` | 访问支付转化率 |
| `share_total_pv` | `string` | ❌ 否 | `19` | 分享访问次数 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1466

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "date_type": "1",
  "current_day": "20201022"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.team.flowoverview.query/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "date_type": "1",
  "current_day": "20201022"
}

response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

> ⚠️ **注意**：以上为示例代码，`access_token` 需要通过 OAuth2.0 流程获取。
> 真实调用地址和参数请以管理后台详情页为准。

---
## 5. 错误码
## 错误码

| 错误码 | 说明 | 处理建议 |
|--------|------|----------|
| 1000 | 系统内部错误 | 稍后重试或联系技术支持 |
| 1001 | 鉴权失败 | 检查 access_token 是否有效 |
| 1002 | 参数校验失败 | 检查必填参数是否完整 |
| 1003 | 权限不足 | 确认应用已开通对应接口权限 |
| 1004 | 频率超限 | 降低请求频率或申请更高配额 |
| 1005 | 资源不存在 | 检查请求的业务 ID 是否正确 |
| 1006 | 请求超时 | 增加超时时间或稍后重试 |
| 1007 | 账户欠费 | 完成账户充值后重试 |

> 更多错误码请参考：[有赞云错误码文档](https://doc.youzanyun.com) |

---
## 6. 内部服务信息
| 字段 | 值 |
|------|---|
| 协议类型 | dubbo |
| 服务名称 | `com.youzan.bigdata.datacenter.base.api.service.flow.yun.YunTeamFlowService` |
| 方法名称 | `getTeamFlowOverview` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1466)_