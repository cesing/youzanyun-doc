---
apiName: "youzan.appstore.open.page.update.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "open_market"
method: "updateMicroPage"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2019-05-20"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/358"
---
# youzan.appstore.open.page.update.1.0.0
> **所属分组**: open_market　**所属应用**: appstore
---
## 1. 场景说明
更新模板
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.page.update/1.0.0`
**请求参数 Schema**（10 个参数）:
```json
{
  "type": "object",
  "properties": {
    "micropage_update_request": {
      "type": "string",
      "description": ""
    },
    "page_id": {
      "type": "integer",
      "description": "页面id"
    },
    "user_id": {
      "type": "integer",
      "description": "用户id"
    },
    "inner_item_id": {
      "type": "integer",
      "description": "内购项id（备用字段，不填）"
    },
    "out_item_id": {
      "type": "string",
      "description": "（内购项）外部商品编码"
    },
    "page_name": {
      "type": "string",
      "description": "页面名称"
    },
    "page_desc": {
      "type": "string",
      "description": "页面描述"
    },
    "view_url": {
      "type": "string",
      "description": "预览地址"
    },
    "re_edit_url": {
      "type": "string",
      "description": "重编辑地址"
    },
    "category_id": {
      "type": "integer",
      "description": "页面分类(非必填)"
    }
  },
  "required": [
    "micropage_update_request",
    "page_id",
    "user_id",
    "out_item_id"
  ]
}
```
**请求参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `micropage_update_request` | `string` | ✅ | `` |  |
| `page_id` | `integer` | ✅ | `` | 页面id |
| `user_id` | `integer` | ✅ | `` | 用户id |
| `inner_item_id` | `integer` | ❌ | `` | 内购项id（备用字段，不填） |
| `out_item_id` | `string` | ✅ | `` | （内购项）外部商品编码 |
| `page_name` | `string` | ❌ | `` | 页面名称 |
| `page_desc` | `string` | ❌ | `` | 页面描述 |
| `view_url` | `string` | ❌ | `` | 预览地址 |
| `re_edit_url` | `string` | ❌ | `` | 重编辑地址 |
| `category_id` | `integer` | ❌ | `` | 页面分类(非必填) |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": ""
    },
    "id": {
      "type": "integer",
      "description": ""
    },
    "page_id": {
      "type": "integer",
      "description": "页面id"
    },
    "inner_item_id": {
      "type": "integer",
      "description": "内购项id(模板id)"
    },
    "page_name": {
      "type": "string",
      "description": "页面名称"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺id"
    },
    "user_id": {
      "type": "integer",
      "description": "用户id"
    },
    "view_url": {
      "type": "string",
      "description": "预览地址"
    },
    "re_edit_url": {
      "type": "string",
      "description": "编辑地址"
    },
    "category_id": {
      "type": "integer",
      "description": "分类id"
    },
    "page_desc": {
      "type": "string",
      "description": "页面描述"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "id": 0,
  "page_id": 0,
  "inner_item_id": 0,
  "page_name": "",
  "kdt_id": 0,
  "user_id": 0,
  "view_url": ""
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` |  |
| `id` | `integer` | ❌ | `` |  |
| `page_id` | `integer` | ❌ | `` | 页面id |
| `inner_item_id` | `integer` | ❌ | `` | 内购项id(模板id) |
| `page_name` | `string` | ❌ | `` | 页面名称 |
| `kdt_id` | `integer` | ❌ | `` | 店铺id |
| `user_id` | `integer` | ❌ | `` | 用户id |
| `view_url` | `string` | ❌ | `` | 预览地址 |
| `re_edit_url` | `string` | ❌ | `` | 编辑地址 |
| `category_id` | `integer` | ❌ | `` | 分类id |
| `page_desc` | `string` | ❌ | `` | 页面描述 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.open.page.update/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "micropage_update_request": "示例值",\n  "page_id": 0,\n  "user_id": 0,\n  "out_item_id": "示例值"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.page.update/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "micropage_update_request": "示例值",
    "page_id": 0,
    "user_id": 0,
    "out_item_id": "示例值"
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