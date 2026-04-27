---
apiName: "youzan.bigdata.datacenter.psmanage.update.pagesource.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
method: "updatePageSource"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-12-14"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3482"
---
# youzan.bigdata.datacenter.psmanage.update.pagesource.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter
---
## 1. 场景说明
更新推广监控名称
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.update.pagesource/1.0.0`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "description": "id更新时不能为空",
      "example": "id，推广监控id，可通过<获取推广监控列表>接口获取。"
    },
    "ps_name": {
      "type": "string",
      "description": "推广名称创建时不能为空",
      "example": "推广名称"
    }
  },
  "required": [
    "id",
    "ps_name"
  ]
}
```
**请求参数明细**（2 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `id` | `integer` | ✅ | `id，推广监控id，可通过<获取推广监控列表>接口获取。` | id更新时不能为空 |
| `ps_name` | `string` | ✅ | `推广名称` | 推广名称创建时不能为空 |
---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "数据"
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
    "ps_code": {
      "type": "string",
      "description": "dcps",
      "example": "111111"
    },
    "ps_name": {
      "type": "string",
      "description": "推广名称",
      "example": "推广名称"
    },
    "source_id": {
      "type": "integer",
      "description": "推广渠道，ps_sourceid",
      "example": "1"
    },
    "source_name": {
      "type": "string",
      "description": "渠道名称",
      "example": "渠道"
    },
    "source_default_tag": {
      "type": "integer",
      "description": "是否默认渠道,0:默认渠道;1:自定义渠道",
      "example": "1"
    },
    "page_info_id": {
      "type": "integer",
      "description": "推广页面，ps_page_info主键id",
      "example": "1"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "id": "1",
  "kdt_id": "88888",
  "ps_code": "111111",
  "ps_name": "推广名称",
  "source_id": "1",
  "source_name": "渠道",
  "source_default_tag": "1"
}
```
**响应参数明细**（9 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 数据 |
| `id` | `integer` | ❌ | `1` | 自增id |
| `kdt_id` | `integer` | ❌ | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `ps_code` | `string` | ❌ | `111111` | dcps |
| `ps_name` | `string` | ❌ | `推广名称` | 推广名称 |
| `source_id` | `integer` | ❌ | `1` | 推广渠道，ps_sourceid |
| `source_name` | `string` | ❌ | `渠道` | 渠道名称 |
| `source_default_tag` | `integer` | ❌ | `1` | 是否默认渠道,0:默认渠道;1:自定义渠道 |
| `page_info_id` | `integer` | ❌ | `1` | 推广页面，ps_page_info主键id |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.update.pagesource/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "id": "id，推广监控id，可通过<获取推广监控列表>接口获取。",\n  "ps_name": "推广名称"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.update.pagesource/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "id": "id，推广监控id，可通过<获取推广监控列表>接口获取。",
    "ps_name": "推广名称"
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