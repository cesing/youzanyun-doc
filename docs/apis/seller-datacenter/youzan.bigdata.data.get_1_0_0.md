---
apiName: "youzan.bigdata.data.get.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "item"
method: "query"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2020-11-12"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1544"
---
# youzan.bigdata.data.get.1.0.0
> **所属分组**: item　**所属应用**: seller-datacenter
---
## 1. 场景说明
该接口仅支持在快手直播产生的推广数据，查询时间间隔T+1，建议数据在第二天的10：00之后查询前一天的数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.data.get/1.0.0`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "ad_cps_team_spu_param": {
      "type": "string",
      "description": "入参"
    },
    "current_day": {
      "type": "string",
      "description": "查询日期",
      "example": "2020-11-10"
    },
    "item_id": {
      "type": "integer",
      "description": "直播商品id",
      "example": "23333"
    },
    "type": {
      "type": "string",
      "description": "渠道类型,默认快手",
      "example": "快手"
    }
  },
  "required": [
    "current_day",
    "item_id"
  ]
}
```
**请求参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `ad_cps_team_spu_param` | `string` | ❌ | `` | 入参 |
| `current_day` | `string` | ✅ | `2020-11-10` | 查询日期 |
| `item_id` | `integer` | ✅ | `23333` | 直播商品id |
| `type` | `string` | ❌ | `快手` | 渠道类型,默认快手 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "直播数据"
    },
    "trade_num": {
      "type": "integer",
      "description": "支付人数",
      "example": "12"
    },
    "trade_count": {
      "type": "integer",
      "description": "支付笔数",
      "example": "121"
    },
    "trade_amount": {
      "type": "integer",
      "description": "支付金额（分）",
      "example": "2"
    },
    "pay_num": {
      "type": "integer",
      "description": "下单人数",
      "example": "12"
    },
    "pay_count": {
      "type": "integer",
      "description": "下单笔数",
      "example": "12"
    },
    "pay_amount": {
      "type": "integer",
      "description": "下单金额（分）",
      "example": "12"
    },
    "pv": {
      "type": "integer",
      "description": "浏览量",
      "example": "12"
    },
    "uv": {
      "type": "integer",
      "description": "访客数",
      "example": "12"
    },
    "success": {
      "type": "boolean",
      "description": "成功与否",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "返回码",
      "example": "200"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "trade_num": "12",
  "trade_count": "121",
  "trade_amount": "2",
  "pay_num": "12",
  "pay_count": "12",
  "pay_amount": "12",
  "pv": "12"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 直播数据 |
| `trade_num` | `integer` | ❌ | `12` | 支付人数 |
| `trade_count` | `integer` | ❌ | `121` | 支付笔数 |
| `trade_amount` | `integer` | ❌ | `2` | 支付金额（分） |
| `pay_num` | `integer` | ❌ | `12` | 下单人数 |
| `pay_count` | `integer` | ❌ | `12` | 下单笔数 |
| `pay_amount` | `integer` | ❌ | `12` | 下单金额（分） |
| `pv` | `integer` | ❌ | `12` | 浏览量 |
| `uv` | `integer` | ❌ | `12` | 访客数 |
| `success` | `boolean` | ❌ | `true` | 成功与否 |
| `code` | `integer` | ❌ | `200` | 返回码 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.data.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "current_day": "2020-11-10",\n  "item_id": "23333",\n  "type": "快手"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.data.get/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "current_day": "2020-11-10",
    "item_id": "23333",
    "type": "快手"
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