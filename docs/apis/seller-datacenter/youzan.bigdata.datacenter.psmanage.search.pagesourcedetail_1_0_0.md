---
apiName: "youzan.bigdata.datacenter.psmanage.search.pagesourcedetail.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
method: "fetchPsPageSourceList"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-12-14"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3483"
---
# youzan.bigdata.datacenter.psmanage.search.pagesourcedetail.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter
---
## 1. 场景说明
获取推广监控列表基本数据,不包含效果数据。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagesourcedetail/1.0.0`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "ps_name": {
      "type": "string",
      "description": "推广监控名称",
      "example": "推广1"
    },
    "dcps_list": {
      "type": "array",
      "description": "dcps列表",
      "example": "[\"2118722746287589378.200001\"]"
    },
    "ps_status": {
      "type": "integer",
      "description": "推广监控状态1:推广中;2:推广结束",
      "example": "1"
    },
    "start_day": {
      "type": "string",
      "description": "查询开始时间",
      "example": "2021-12-01"
    },
    "end_day": {
      "type": "string",
      "description": "查询结束时间",
      "example": "2021-12-01"
    },
    "page_no": {
      "type": "integer",
      "description": "分页信息",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "分页信息",
      "example": "100"
    }
  },
  "required": [
    "page_no",
    "page_size"
  ]
}
```
**请求参数明细**（7 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `ps_name` | `string` | ❌ | `推广1` | 推广监控名称 |
| `dcps_list` | `array` | ❌ | `["2118722746287589378.200001"]` | dcps列表 |
| `ps_status` | `integer` | ❌ | `1` | 推广监控状态1:推广中;2:推广结束 |
| `start_day` | `string` | ❌ | `2021-12-01` | 查询开始时间 |
| `end_day` | `string` | ❌ | `2021-12-01` | 查询结束时间 |
| `page_no` | `integer` | ✅ | `1` | 分页信息 |
| `page_size` | `integer` | ✅ | `100` | 分页信息 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "结果"
    },
    "paginator": {
      "type": "string",
      "description": "分页信息"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页条数。最大不能超过200",
      "example": "100"
    },
    "total_count": {
      "type": "integer",
      "description": "总数",
      "example": "1000"
    },
    "items": {
      "type": "array",
      "description": "推广监控列表"
    },
    "id": {
      "type": "integer",
      "description": "自增id",
      "example": "1"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "dcps": {
      "type": "string",
      "description": "dcps",
      "example": "2118722746287589378.200001"
    },
    "ps_name": {
      "type": "string",
      "description": "推广名称",
      "example": "推广1"
    },
    "source_id": {
      "type": "integer",
      "description": "推广渠道id,ps_sourceid",
      "example": "1"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "paginator": "",
  "page_no": "1",
  "page_size": "100",
  "total_count": "1000",
  "items": [],
  "id": "1",
  "kdt_id": "88888"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 结果 |
| `paginator` | `string` | ❌ | `` | 分页信息 |
| `page_no` | `integer` | ❌ | `1` | 页码 |
| `page_size` | `integer` | ❌ | `100` | 每页条数。最大不能超过200 |
| `total_count` | `integer` | ❌ | `1000` | 总数 |
| `items` | `array` | ❌ | `` | 推广监控列表 |
| `id` | `integer` | ❌ | `1` | 自增id |
| `kdt_id` | `integer` | ❌ | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `dcps` | `string` | ❌ | `2118722746287589378.200001` | dcps |
| `ps_name` | `string` | ❌ | `推广1` | 推广名称 |
| `source_id` | `integer` | ❌ | `1` | 推广渠道id,ps_sourceid |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagesourcedetail/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "ps_name": "推广1",\n  "dcps_list": "[\"2118722746287589378.200001\"]",\n  "ps_status": "1",\n  "start_day": "2021-12-01",\n  "end_day": "2021-12-01",\n  "page_no": "1",\n  "page_size": "100"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagesourcedetail/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "ps_name": "推广1",
    "dcps_list": "[\"2118722746287589378.200001\"]",
    "ps_status": "1",
    "start_day": "2021-12-01",
    "end_day": "2021-12-01",
    "page_no": "1",
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