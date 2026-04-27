---
apiName: "youzan.appstore.sevicedemand.query.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "customized_api"
method: "getDemandListByTime"
timeout: "5000"
authType: "无需认证"
type: "HTTP"
deprecated: false
since: "2021-05-12"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2829"
---
# youzan.appstore.sevicedemand.query.1.0.0
> **所属分组**: customized_api　**所属应用**: appstore
---
## 1. 场景说明
根据时间获取需求列表(连接器调用)
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.sevicedemand.query/1.0.0`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "start_time": {
      "type": "string",
      "description": "开始时间筛选条件，默认1970-01-01 08:00:00",
      "example": "2021-05-07 00:00:00"
    },
    "end_time": {
      "type": "string",
      "description": "结束时间筛选条件，默认当前时间",
      "example": "2021-05-07 00:00:00"
    },
    "page_no": {
      "type": "integer",
      "description": "查询时当前的页数（分页查询接口必填）",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页展示的行数（分页查询接口必填）",
      "example": "10"
    }
  },
  "required": [
    "start_time"
  ]
}
```
**请求参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `start_time` | `string` | ✅ | `2021-05-07 00:00:00` | 开始时间筛选条件，默认1970-01-01 08:00:00 |
| `end_time` | `string` | ❌ | `2021-05-07 00:00:00` | 结束时间筛选条件，默认当前时间 |
| `page_no` | `integer` | ❌ | `1` | 查询时当前的页数（分页查询接口必填） |
| `page_size` | `integer` | ❌ | `10` | 每页展示的行数（分页查询接口必填） |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "data"
    },
    "paginator": {
      "type": "string",
      "description": "分页"
    },
    "page": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "页数",
      "example": "10"
    },
    "total_count": {
      "type": "integer",
      "description": "总数",
      "example": "10"
    },
    "items": {
      "type": "array",
      "description": "需求列表"
    },
    "id": {
      "type": "integer",
      "description": "主键id",
      "example": "1"
    },
    "demand_no": {
      "type": "string",
      "description": "需求编号",
      "example": "864642465397448704"
    },
    "demand_detail": {
      "type": "string",
      "description": "需求信息",
      "example": "我需要10人的客服团队"
    },
    "mobile": {
      "type": "string",
      "description": "联系人手机号码",
      "example": "13000000000"
    },
    "status": {
      "type": "integer",
      "description": "需求状态",
      "example": "10"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "paginator": "",
  "page": "1",
  "page_size": "10",
  "total_count": "10",
  "items": [],
  "id": "1",
  "demand_no": "864642465397448704"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | data |
| `paginator` | `string` | ❌ | `` | 分页 |
| `page` | `integer` | ❌ | `1` | 页码 |
| `page_size` | `integer` | ❌ | `10` | 页数 |
| `total_count` | `integer` | ❌ | `10` | 总数 |
| `items` | `array` | ❌ | `` | 需求列表 |
| `id` | `integer` | ❌ | `1` | 主键id |
| `demand_no` | `string` | ❌ | `864642465397448704` | 需求编号 |
| `demand_detail` | `string` | ❌ | `我需要10人的客服团队` | 需求信息 |
| `mobile` | `string` | ❌ | `13000000000` | 联系人手机号码 |
| `status` | `integer` | ❌ | `10` | 需求状态 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.sevicedemand.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "start_time": "2021-05-07 00:00:00",\n  "end_time": "2021-05-07 00:00:00",\n  "page_no": "1",\n  "page_size": "10"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.sevicedemand.query/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "start_time": "2021-05-07 00:00:00",
    "end_time": "2021-05-07 00:00:00",
    "page_no": "1",
    "page_size": "10"
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