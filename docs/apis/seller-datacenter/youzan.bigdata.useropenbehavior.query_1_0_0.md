---
apiName: "youzan.bigdata.useropenbehavior.query.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "data_center"
method: "scan"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-07-09"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3021"
---
# youzan.bigdata.useropenbehavior.query.1.0.0
> **所属分组**: data_center　**所属应用**: seller-datacenter
---
## 1. 场景说明
店铺用户行为数据接口（大客户专属），每天早上9点更新前一天的用户行为数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.0`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "current_day": {
      "type": "string",
      "description": "日期，日期的格式为：yyyy-MM-dd",
      "example": "2021-07-08"
    },
    "page_num": {
      "type": "integer",
      "description": "页数",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页查看的条数",
      "example": "100"
    }
  },
  "required": []
}
```
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `current_day` | `string` | ❌ | `2021-07-08` | 日期，日期的格式为：yyyy-MM-dd |
| `page_num` | `integer` | ❌ | `1` | 页数 |
| `page_size` | `integer` | ❌ | `100` | 每页查看的条数 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "业务数据"
    },
    "yz_uid": {
      "type": "string",
      "description": "有赞用户id",
      "example": "1"
    },
    "user_log_time": {
      "type": "integer",
      "description": "行为发生时间。13位时间戳",
      "example": "1234567891234"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "91619160"
    },
    "hq_kdt_id": {
      "type": "integer",
      "description": "连锁店铺,总店id,非连锁店铺等同于kdt_id",
      "example": "91619160"
    },
    "current_day": {
      "type": "string",
      "description": "日期，格式：yyyy-MM-dd",
      "example": "2021-07-08"
    },
    "page": {
      "type": "string",
      "description": "行为发生页面地址",
      "example": "https://shimo.im/docs/VMAPV72EwMSayEqg"
    },
    "page_title": {
      "type": "string",
      "description": "行为发生页面标题",
      "example": "埋点分析中间层"
    },
    "event_sign": {
      "type": "string",
      "description": "行为事件标识",
      "example": "enterpage"
    },
    "scene_level1": {
      "type": "string",
      "description": "流量来源第一级:小程序下为weapp",
      "example": "enterpage"
    },
    "scene_level2": {
      "type": "string",
      "description": "流量来源第二级:小程序下为wexin、alipay、baidu、qq等",
      "example": "enterpage"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "yz_uid": "1",
  "user_log_time": "1234567891234",
  "kdt_id": "91619160",
  "hq_kdt_id": "91619160",
  "current_day": "2021-07-08",
  "page": "https://shimo.im/docs/VMAPV72EwMSayEqg",
  "page_title": "埋点分析中间层"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 业务数据 |
| `yz_uid` | `string` | ❌ | `1` | 有赞用户id |
| `user_log_time` | `integer` | ❌ | `1234567891234` | 行为发生时间。13位时间戳 |
| `kdt_id` | `integer` | ❌ | `91619160` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `hq_kdt_id` | `integer` | ❌ | `91619160` | 连锁店铺,总店id,非连锁店铺等同于kdt_id |
| `current_day` | `string` | ❌ | `2021-07-08` | 日期，格式：yyyy-MM-dd |
| `page` | `string` | ❌ | `https://shimo.im/docs/VMAPV72EwMSayEqg` | 行为发生页面地址 |
| `page_title` | `string` | ❌ | `埋点分析中间层` | 行为发生页面标题 |
| `event_sign` | `string` | ❌ | `enterpage` | 行为事件标识 |
| `scene_level1` | `string` | ❌ | `enterpage` | 流量来源第一级:小程序下为weapp |
| `scene_level2` | `string` | ❌ | `enterpage` | 流量来源第二级:小程序下为wexin、alipay、baidu、qq等 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "current_day": "2021-07-08",\n  "page_num": "1",\n  "page_size": "100"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "current_day": "2021-07-08",
    "page_num": "1",
    "page_size": "100"
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