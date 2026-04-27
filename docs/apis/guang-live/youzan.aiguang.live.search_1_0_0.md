---
apiName: "youzan.aiguang.live.search.1.0.0"
version: "1.0.0"
appName: "guang-live"
apiGroup: "open_education_broadcast"
method: "searchForYouzanShop"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-12-14"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3477"
---
# youzan.aiguang.live.search.1.0.0
> **所属分组**: open_education_broadcast　**所属应用**: guang-live
---
## 1. 场景说明
查询有赞店铺直播列表数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.aiguang.live.search/1.0.0`
**请求参数 Schema**（6 个参数）:
```json
{
  "type": "object",
  "properties": {
    "page_no": {
      "type": "integer",
      "description": "分页参数",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "分页参数（最小1， 最大暂未限制，无默认值）",
      "example": "10"
    },
    "state_list": {
      "type": "integer",
      "description": "直播状态；10：预告；15：直播中；45：结束(也就是回放)",
      "example": "[10, 15]"
    },
    "is_replay_search": {
      "type": "boolean",
      "description": "是否回放搜索，是的话stateList参数将失效",
      "example": "true"
    },
    "sequence_field": {
      "type": "string",
      "description": "目前仅支持started_at字段",
      "example": "started_at"
    },
    "sequence_type": {
      "type": "string",
      "description": "排序类型：desc（默认降序），asc（升序）",
      "example": "desc"
    }
  },
  "required": [
    "page_no",
    "page_size",
    "state_list",
    "is_replay_search",
    "sequence_field",
    "sequence_type"
  ]
}
```
**请求参数明细**（6 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `page_no` | `integer` | ✅ | `1` | 分页参数 |
| `page_size` | `integer` | ✅ | `10` | 分页参数（最小1， 最大暂未限制，无默认值） |
| `state_list` | `integer` | ✅ | `[10, 15]` | 直播状态；10：预告；15：直播中；45：结束(也就是回放) |
| `is_replay_search` | `boolean` | ✅ | `true` | 是否回放搜索，是的话stateList参数将失效 |
| `sequence_field` | `string` | ✅ | `started_at` | 目前仅支持started_at字段 |
| `sequence_type` | `string` | ✅ | `desc` | 排序类型：desc（默认降序），asc（升序） |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "返回值"
    },
    "list": {
      "type": "array",
      "description": "列表"
    },
    "live_stream_id": {
      "type": "integer",
      "description": "直播id",
      "example": "123456"
    },
    "guang_business_id": {
      "type": "integer",
      "description": "爱逛号业务id",
      "example": "123456"
    },
    "title": {
      "type": "string",
      "description": "直播标题",
      "example": "直播"
    },
    "started_at": {
      "type": "string",
      "description": "开播时间",
      "example": "2021-10-10 00:00:00"
    },
    "state": {
      "type": "integer",
      "description": "直播状态（10:预告，15:直播中，45:结束）",
      "example": "10"
    },
    "cover_uri": {
      "type": "string",
      "description": "直播封面",
      "example": "https://img.yzcdn.cn/upload_files/2020/08/10/Fih7pMf5l5r5b3OZ0nK8Nr7XMsSX.png"
    },
    "play_uri": {
      "type": "string",
      "description": "播放地址",
      "example": "http://glive-play.yzcdn.cn/live/3973a330ae3afec6ed4cc4226603b283.flv"
    },
    "replay_uri": {
      "type": "string",
      "description": "回放地址",
      "example": "http://glive-play.yzcdn.cn/live/3c6957f06721c991a4eb87d184d34d66.flv"
    },
    "guang_business": {
      "type": "string",
      "description": "爱逛号信息"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "list": [],
  "live_stream_id": "123456",
  "guang_business_id": "123456",
  "title": "直播",
  "started_at": "2021-10-10 00:00:00",
  "state": "10",
  "cover_uri": "https://img.yzcdn.cn/upload_files/2020/08/10/Fih7pMf5l5r5b3OZ0nK8Nr7XMsSX.png"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 返回值 |
| `list` | `array` | ❌ | `` | 列表 |
| `live_stream_id` | `integer` | ❌ | `123456` | 直播id |
| `guang_business_id` | `integer` | ❌ | `123456` | 爱逛号业务id |
| `title` | `string` | ❌ | `直播` | 直播标题 |
| `started_at` | `string` | ❌ | `2021-10-10 00:00:00` | 开播时间 |
| `state` | `integer` | ❌ | `10` | 直播状态（10:预告，15:直播中，45:结束） |
| `cover_uri` | `string` | ❌ | `https://img.yzcdn.cn/upload_files/2020/0` | 直播封面 |
| `play_uri` | `string` | ❌ | `http://glive-play.yzcdn.cn/live/3973a330` | 播放地址 |
| `replay_uri` | `string` | ❌ | `http://glive-play.yzcdn.cn/live/3c6957f0` | 回放地址 |
| `guang_business` | `string` | ❌ | `` | 爱逛号信息 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.aiguang.live.search/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "page_no": "1",\n  "page_size": "10",\n  "state_list": "[10, 15]",\n  "is_replay_search": "true",\n  "sequence_field": "started_at",\n  "sequence_type": "desc"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.aiguang.live.search/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "page_no": "1",
    "page_size": "10",
    "state_list": "[10, 15]",
    "is_replay_search": "true",
    "sequence_field": "started_at",
    "sequence_type": "desc"
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