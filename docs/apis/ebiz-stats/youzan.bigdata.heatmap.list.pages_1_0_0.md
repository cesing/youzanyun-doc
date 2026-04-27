---
apiName: "youzan.bigdata.heatmap.list.pages.1.0.0"
version: "1.0.0"
appName: "ebiz-stats"
apiGroup: "data_center"
method: "getPages"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-05-18"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4075"
---
# youzan.bigdata.heatmap.list.pages.1.0.0
> **所属分组**: data_center　**所属应用**: ebiz-stats
---
## 1. 场景说明
获取热力图页面列表,分页方式获取页面列表。支持页面模糊搜索和页面类型的筛选。返回的id为热力图id，后续查询页面统计信息时传递上述id进行查询。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.heatmap.list.pages/1.0.0`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "page_type": {
      "type": "string",
      "description": "热力图页面类型。微页面：f，商详页g，不传查全部",
      "example": "f"
    },
    "page_name": {
      "type": "string",
      "description": "热力图页面名称模糊搜索",
      "example": "主页"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页大小",
      "example": "10"
    }
  },
  "required": []
}
```
**请求参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `page_type` | `string` | ❌ | `f` | 热力图页面类型。微页面：f，商详页g，不传查全部 |
| `page_name` | `string` | ❌ | `主页` | 热力图页面名称模糊搜索 |
| `page_no` | `integer` | ❌ | `1` | 页码 |
| `page_size` | `integer` | ❌ | `10` | 每页大小 |
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
      "description": "分页结果"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页大小",
      "example": "10"
    },
    "total_count": {
      "type": "integer",
      "description": "总数",
      "example": "15"
    },
    "items": {
      "type": "array",
      "description": "热力图页面信息列表"
    },
    "id": {
      "type": "integer",
      "description": "热力图id，查询热力图统计数据时使用",
      "example": "1"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "page_id": {
      "type": "integer",
      "description": "商品或者微页面id",
      "example": "123"
    },
    "page_alias": {
      "type": "string",
      "description": "商品或者微页面别名",
      "example": "ffff"
    },
    "page_name": {
      "type": "string",
      "description": "商品或者微页面名称",
      "example": "主页面"
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
  "page_size": "10",
  "total_count": "15",
  "items": [],
  "id": "1",
  "kdt_id": "88888"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 结果 |
| `paginator` | `string` | ❌ | `` | 分页结果 |
| `page_no` | `integer` | ❌ | `1` | 页码 |
| `page_size` | `integer` | ❌ | `10` | 每页大小 |
| `total_count` | `integer` | ❌ | `15` | 总数 |
| `items` | `array` | ❌ | `` | 热力图页面信息列表 |
| `id` | `integer` | ❌ | `1` | 热力图id，查询热力图统计数据时使用 |
| `kdt_id` | `integer` | ❌ | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `page_id` | `integer` | ❌ | `123` | 商品或者微页面id |
| `page_alias` | `string` | ❌ | `ffff` | 商品或者微页面别名 |
| `page_name` | `string` | ❌ | `主页面` | 商品或者微页面名称 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.heatmap.list.pages/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "page_type": "f",\n  "page_name": "主页",\n  "page_no": "1",\n  "page_size": "10"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.heatmap.list.pages/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "page_type": "f",
    "page_name": "主页",
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