---
apiName: "youzan.bigdata.heatmap.query.heatMapDetail.1.0.0"
version: "1.0.0"
appName: "ebiz-stats"
apiGroup: "data_center"
method: "getHeatMapNew"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-05-18"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4076"
---
# youzan.bigdata.heatmap.query.heatMapDetail.1.0.0
> **所属分组**: data_center　**所属应用**: ebiz-stats
---
## 1. 场景说明
根据热力图id获取各个渠道下的页面的每个点位点击情况。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.heatMapDetail/1.0.0`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "description": "热力图id，而非页面id",
      "example": "1"
    },
    "start_time": {
      "type": "integer",
      "description": "开始时间，格式YYYYMMdd",
      "example": "20230511"
    },
    "end_time": {
      "type": "integer",
      "description": "结束时间，格式YYYYMMdd",
      "example": "20230511"
    },
    "sdk_type": {
      "type": "string",
      "description": "渠道筛选条件。枚举值小程序：weapp、 其他：js",
      "example": "weapp"
    }
  },
  "required": [
    "start_time",
    "end_time",
    "sdk_type"
  ]
}
```
**请求参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `id` | `integer` | ❌ | `1` | 热力图id，而非页面id |
| `start_time` | `integer` | ✅ | `20230511` | 开始时间，格式YYYYMMdd |
| `end_time` | `integer` | ✅ | `20230511` | 结束时间，格式YYYYMMdd |
| `sdk_type` | `string` | ✅ | `weapp` | 渠道筛选条件。枚举值小程序：weapp、 其他：js |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "业务数据内容"
    },
    "hot_zone": {
      "type": "array",
      "description": "热点图坐标信息"
    },
    "loc_x": {
      "type": "integer",
      "description": "x轴",
      "example": "1"
    },
    "loc_y": {
      "type": "integer",
      "description": "y轴",
      "example": "1"
    },
    "click_pv": {
      "type": "integer",
      "description": "点击次数",
      "example": "1"
    },
    "click_uv": {
      "type": "integer",
      "description": "点击人数",
      "example": "1"
    },
    "is_fix": {
      "type": "boolean",
      "description": "是否是浮层，true为浮层",
      "example": "true"
    },
    "page_info": {
      "type": "string",
      "description": "热点图页面信息"
    },
    "page_type": {
      "type": "string",
      "description": "页面类型",
      "example": "f"
    },
    "page_id": {
      "type": "integer",
      "description": "页面id",
      "example": "1"
    },
    "page_name": {
      "type": "string",
      "description": "页面名称",
      "example": "主页"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "hot_zone": [],
  "loc_x": "1",
  "loc_y": "1",
  "click_pv": "1",
  "click_uv": "1",
  "is_fix": "true",
  "page_info": ""
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 业务数据内容 |
| `hot_zone` | `array` | ❌ | `` | 热点图坐标信息 |
| `loc_x` | `integer` | ❌ | `1` | x轴 |
| `loc_y` | `integer` | ❌ | `1` | y轴 |
| `click_pv` | `integer` | ❌ | `1` | 点击次数 |
| `click_uv` | `integer` | ❌ | `1` | 点击人数 |
| `is_fix` | `boolean` | ❌ | `true` | 是否是浮层，true为浮层 |
| `page_info` | `string` | ❌ | `` | 热点图页面信息 |
| `page_type` | `string` | ❌ | `f` | 页面类型 |
| `page_id` | `integer` | ❌ | `1` | 页面id |
| `page_name` | `string` | ❌ | `主页` | 页面名称 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.heatMapDetail/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "id": "1",\n  "start_time": "20230511",\n  "end_time": "20230511",\n  "sdk_type": "weapp"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.heatMapDetail/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "id": "1",
    "start_time": "20230511",
    "end_time": "20230511",
    "sdk_type": "weapp"
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