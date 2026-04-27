---
apiName: "youzan.bigdata.realtime.query.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "shop"
method: "getRealTimeOverView"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2025-06-11"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4839"
---
# youzan.bigdata.realtime.query.1.0.0
> **所属分组**: shop　**所属应用**: seller-datacenter
---
## 1. 场景说明
实时分析的实时概况数据，主要包括浏览访问、成交转化、客户会员
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.realtime.query/1.0.0`
**请求参数 Schema**（10 个参数）:
```json
{
  "type": "object",
  "properties": {
    "basic_param": {
      "type": "string",
      "description": "请求体"
    },
    "current_day": {
      "type": "integer",
      "description": "不填则为今日实时format:yyyyMMdd",
      "example": "20250611"
    },
    "canal_type": {
      "type": "integer",
      "description": "线上线下：0线上；1线下；10全部",
      "example": "0"
    },
    "page_no": {
      "type": "integer",
      "description": "分页参数",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页数据量大小",
      "example": "10"
    },
    "team_level": {
      "type": "integer",
      "description": "店铺等级：0-总店或者管理单元;1-子店;",
      "example": "1"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺id",
      "example": "88888"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用",
      "example": "123456"
    },
    "request_id": {
      "type": "string",
      "description": "UUID",
      "example": "sadsadafdafdsfsd"
    },
    "operator": {
      "type": "string",
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
**请求参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `basic_param` | `string` | ❌ | `` | 请求体 |
| `current_day` | `integer` | ✅ | `20250611` | 不填则为今日实时format:yyyyMMdd |
| `canal_type` | `integer` | ❌ | `0` | 线上线下：0线上；1线下；10全部 |
| `page_no` | `integer` | ❌ | `1` | 分页参数 |
| `page_size` | `integer` | ❌ | `10` | 每页数据量大小 |
| `team_level` | `integer` | ❌ | `1` | 店铺等级：0-总店或者管理单元;1-子店; |
| `kdt_id` | `integer` | ❌ | `88888` | 店铺id |
| `yz_open_id` | `integer` | ✅ | `123456` | 有赞用户id，用户在有赞的唯一id。推荐使用 |
| `request_id` | `string` | ❌ | `sadsadafdafdsfsd` | UUID |
| `operator` | `string` | ❌ | `zhangsan` | 操作人名字 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "数据"
    },
    "current_day": {
      "type": "integer",
      "description": "日期，如：20250611",
      "example": "20250611"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "uv": {
      "type": "integer",
      "description": "访客数",
      "example": "11"
    },
    "pv": {
      "type": "integer",
      "description": "浏览量",
      "example": "11"
    },
    "new_member_uv": {
      "type": "integer",
      "description": "新增会员数",
      "example": "11"
    },
    "hour": {
      "type": "integer",
      "description": "小时，如：10",
      "example": "12"
    },
    "yester_day": {
      "type": "string",
      "description": "昨天"
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
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 数据 |
| `current_day` | `string` | ❌ | `` | 当前时间，如：20250611 |
| `kdt_id` | `integer` | ❌ | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `uv` | `integer` | ❌ | `11` | 访客数 |
| `pv` | `integer` | ❌ | `11` | 浏览量 |
| `new_member_uv` | `integer` | ❌ | `11` | 新增会员数 |
| `current_day` | `integer` | ❌ | `20250611` | 日期，如：20250611 |
| `hour` | `integer` | ❌ | `12` | 小时，如：10 |
| `yester_day` | `string` | ❌ | `` | 昨天 |
| `kdt_id` | `integer` | ❌ | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `uv` | `integer` | ❌ | `11` | 访客数 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.realtime.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "current_day": "20250611",\n  "canal_type": "0",\n  "page_no": "1",\n  "page_size": "10",\n  "team_level": "1",\n  "kdt_id": "88888",\n  "yz_open_id": "123456",\n  "request_id": "sadsadafdafdsfsd",\n  "operator": "zhangsan"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.realtime.query/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "current_day": "20250611",
    "canal_type": "0",
    "page_no": "1",
    "page_size": "10",
    "team_level": "1",
    "kdt_id": "88888",
    "yz_open_id": "123456",
    "request_id": "sadsadafdafdsfsd",
    "operator": "zhangsan"
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