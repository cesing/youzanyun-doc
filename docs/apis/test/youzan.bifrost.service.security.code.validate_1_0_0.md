---
apiName: "youzan.bifrost.service.security.code.validate.1.0.0"
version: "1.0.0"
appName: "test"
apiGroup: "customized_api"
method: "validate"
timeout: "5000"
authType: "无需认证"
type: "HTTP"
deprecated: false
since: "2020-07-08"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1071"
---
# youzan.bifrost.service.security.code.validate.1.0.0
> **所属分组**: customized_api　**所属应用**: test
---
## 1. 场景说明
校验app开店安全码
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bifrost.service.security.code.validate/1.0.0`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "client_id": {
      "type": "string",
      "description": "应用的client_id",
      "example": "2"
    },
    "type": {
      "type": "integer",
      "description": "-1:未知,1:安卓,2:IOS",
      "example": "2"
    },
    "unique_key": {
      "type": "string",
      "description": "唯一标示",
      "example": "2"
    },
    "security_code": {
      "type": "string",
      "description": "安全码,安卓为SHA1,IOS为BundleID",
      "example": "2"
    },
    "extra_code": {
      "type": "string",
      "description": "扩展编码,安卓为包名,IOS暂无",
      "example": "2"
    }
  },
  "required": [
    "client_id",
    "type",
    "unique_key",
    "security_code"
  ]
}
```
**请求参数明细**（5 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `client_id` | `string` | ✅ | `2` | 应用的client_id |
| `type` | `integer` | ✅ | `2` | -1:未知,1:安卓,2:IOS |
| `unique_key` | `string` | ✅ | `2` | 唯一标示 |
| `security_code` | `string` | ✅ | `2` | 安全码,安卓为SHA1,IOS为BundleID |
| `extra_code` | `string` | ❌ | `2` | 扩展编码,安卓为包名,IOS暂无 |
---
## 3. 响应
**响应参数 Schema**（7 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "",
      "example": "2"
    },
    "success": {
      "type": "boolean",
      "description": "",
      "example": "2"
    },
    "code": {
      "type": "integer",
      "description": "",
      "example": "2"
    },
    "message": {
      "type": "string",
      "description": "",
      "example": "2"
    },
    "request_id": {
      "type": "string",
      "description": "",
      "example": "3"
    },
    "error_data": {
      "type": "object",
      "description": "",
      "example": "2"
    },
    "test": {
      "type": "integer",
      "description": "",
      "example": "2"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "2",
  "success": "2",
  "code": "2",
  "message": "2",
  "request_id": "3",
  "error_data": "2",
  "test": "2"
}
```
**响应参数明细**（7 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `2` |  |
| `success` | `boolean` | ❌ | `2` |  |
| `code` | `integer` | ❌ | `2` |  |
| `message` | `string` | ❌ | `2` |  |
| `request_id` | `string` | ❌ | `3` |  |
| `error_data` | `object` | ❌ | `2` |  |
| `test` | `integer` | ❌ | `2` |  |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bifrost.service.security.code.validate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "client_id": "2",\n  "type": "2",\n  "unique_key": "2",\n  "security_code": "2",\n  "extra_code": "2"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bifrost.service.security.code.validate/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "client_id": "2",
    "type": "2",
    "unique_key": "2",
    "security_code": "2",
    "extra_code": "2"
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