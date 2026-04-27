---
apiName: "youzan.aiguang.live.search.1.0.0"
version: "1.0.0"
appName: "guang-live"
apiGroup: "教育"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3477"
---

# youzan.aiguang.live.search.1.0.0

> **所属分组**: 教育

---

## 1. 场景说明

查询有赞店铺直播列表数据

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.aiguang.live.search/1.0.0`

**认证方式**: 凭证式

**请求参数**（6 个）:

```json
{
  "type": "object",
  "properties": {
    "page_no": {
      "type": "java.lang.Integer",
      "description": "分页参数",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "分页参数（最小1， 最大暂未限制，无默认值）",
      "example": "10"
    },
    "state_list": {
      "type": "java.util.List<java.lang.Integer>",
      "description": "直播状态；10：预告；15：直播中；45：结束(也就是回放)",
      "example": "[10, 15]"
    },
    "is_replay_search": {
      "type": "java.lang.Boolean",
      "description": "是否回放搜索，是的话stateList参数将失效",
      "example": "true"
    },
    "sequence_field": {
      "type": "java.lang.String",
      "description": "目前仅支持started_at字段",
      "example": "started_at"
    },
    "sequence_type": {
      "type": "java.lang.String",
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

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.guang.live.api.entity.PagedList<com.guang.live.api.entity.LiveStreamForYouzanShop>",
      "description": "返回值",
      "example": ""
    },
    "list": {
      "type": "java.util.List<com.guang.live.api.entity.LiveStreamForYouzanShop>",
      "description": "列表",
      "example": ""
    },
    "live_stream_id": {
      "type": "java.lang.Long",
      "description": "直播id",
      "example": "123456"
    },
    "guang_business_id": {
      "type": "java.lang.Long",
      "description": "爱逛号业务id",
      "example": "123456"
    },
    "title": {
      "type": "java.lang.String",
      "description": "直播标题",
      "example": "直播"
    },
    "started_at": {
      "type": "java.util.Date",
      "description": "开播时间",
      "example": "2021-10-10 00:00:00"
    },
    "state": {
      "type": "java.lang.Integer",
      "description": "直播状态（10:预告，15:直播中，45:结束）",
      "example": "10"
    },
    "cover_uri": {
      "type": "java.lang.String",
      "description": "直播封面",
      "example": "https://img.yzcdn.cn/upload_files/2020/08/10/Fih7pMf5l5r5b3OZ0nK8Nr7XMsSX.png"
    },
    "play_uri": {
      "type": "java.lang.String",
      "description": "播放地址",
      "example": "http://glive-play.yzcdn.cn/live/3973a330ae3afec6ed4cc4226603b283.flv"
    },
    "replay_uri": {
      "type": "java.lang.String",
      "description": "回放地址",
      "example": "http://glive-play.yzcdn.cn/live/3c6957f06721c991a4eb87d184d34d66.flv"
    },
    "guang_business": {
      "type": "com.guang.live.api.entity.GuangBusiness",
      "description": "爱逛号信息",
      "example": ""
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "list": "",
  "live_stream_id": "123456",
  "guang_business_id": "123456",
  "title": "直播",
  "started_at": "2021-10-10 00:00:00",
  "state": "10",
  "cover_uri": "https://img.yzcdn.cn/upload_files/2020/08/10/Fih7pMf5l5r5b3OZ0nK8Nr7XMsSX.png"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.aiguang.live.search/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.aiguang.live.search/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3477)*