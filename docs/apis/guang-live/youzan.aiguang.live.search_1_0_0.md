---
apiName: "youzan.aiguang.live.search.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "guang-live"
apiGroup: "open_education_broadcast"
serviceName: "com.guang.live.api.service.LiveStreamingSearchService"
method: "searchForYouzanShop"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2021-12-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3477"
---
# youzan.aiguang.live.search.1.0.0
> **所属分组**: open_education_broadcast　**所属应用**: guang-live　**状态**: 已上线/变更中
---
## 1. 场景说明
查询有赞店铺直播列表数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.aiguang.live.search/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `page_no` | `integer` | ✅ 是 | `1` | 分页参数 |
| `page_size` | `integer` | ✅ 是 | `10` | 分页参数（最小1， 最大暂未限制，无默认值） |
| `state_list` | `integer` | ✅ 是 | `[10, 15]` | 直播状态；10：预告；15：直播中；45：结束(也就是回放) |
| `is_replay_search` | `boolean` | ✅ 是 | `true` | 是否回放搜索，是的话stateList参数将失效 |
| `sequence_field` | `string` | ✅ 是 | `started_at` | 目前仅支持started_at字段 |
| `sequence_type` | `string` | ✅ 是 | `desc` | 排序类型：desc（默认降序），asc（升序） |
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` | 返回值 |
| `list` | `array` | ❌ 否 | `` | 列表 |
| `live_stream_id` | `integer` | ❌ 否 | `123456` | 直播id |
| `guang_business_id` | `integer` | ❌ 否 | `123456` | 爱逛号业务id |
| `title` | `string` | ❌ 否 | `直播` | 直播标题 |
| `started_at` | `string` | ❌ 否 | `2021-10-10 00:00:00` | 开播时间 |
| `state` | `integer` | ❌ 否 | `10` | 直播状态（10:预告，15:直播中，45:结束） |
| `cover_uri` | `string` | ❌ 否 | `https://img.yzcdn.cn/upload_fi` | 直播封面 |
| `play_uri` | `string` | ❌ 否 | `http://glive-play.yzcdn.cn/liv` | 播放地址 |
| `replay_uri` | `string` | ❌ 否 | `http://glive-play.yzcdn.cn/liv` | 回放地址 |
| `guang_business` | `string` | ❌ 否 | `` | 爱逛号信息 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3477

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "page_no": "1",
  "page_size": "10",
  "state_list": "[10, 15]",
  "is_replay_search": "true",
  "sequence_field": "started_at"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.aiguang.live.search/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "page_no": "1",
  "page_size": "10",
  "state_list": "[10, 15]",
  "is_replay_search": "true",
  "sequence_field": "started_at"
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
| 服务名称 | `com.guang.live.api.service.LiveStreamingSearchService` |
| 方法名称 | `searchForYouzanShop` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3477)_