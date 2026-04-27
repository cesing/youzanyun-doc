---
apiName: "youzan.agent.gatewaytest.upload.preworkflow.1.0.0"
version: "1.0.0"
appName: "gateway-test"
apiGroup: "网关测试分组"
method: "POST"
timeout: "100000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2025-05-27"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4828"
---
# youzan.agent.gatewaytest.upload.preworkflow.1.0.0
> **所属分组**: 网关测试分组　**所属应用**: gateway-test
---
## 1. 场景说明
智能体测试专用：文件上传测试
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.agent.gatewaytest.upload.preworkflow/1.0.0`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "user": {
      "type": "string",
      "description": "user",
      "example": "user"
    },
    "file": {
      "type": "string",
      "description": "file",
      "example": "file"
    }
  },
  "required": [
    "user",
    "file"
  ]
}
```
**请求参数明细**（2 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `user` | `string` | ✅ | `user` | user |
| `file` | `string` | ✅ | `file` | file |
---
## 3. 响应
**响应参数 Schema**（5 个字段）:
```json
{
  "type": "object",
  "properties": {
    "code": {
      "type": "integer",
      "description": "code",
      "example": "code"
    },
    "message": {
      "type": "string",
      "description": "message",
      "example": "success"
    },
    "statusCode": {
      "type": "string",
      "description": "statusCode",
      "example": "01@@3664@010200"
    },
    "success": {
      "type": "boolean",
      "description": "success",
      "example": "true"
    },
    "data": {
      "type": "object",
      "description": "data",
      "example": "data"
    }
  }
}
```
**成功响应示例**:
```json
{
  "code": "code",
  "message": "success",
  "statusCode": "01@@3664@010200",
  "success": "true",
  "data": "data"
}
```
**响应参数明细**（5 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `code` | `integer` | ❌ | `code` | code |
| `message` | `string` | ❌ | `success` | message |
| `statusCode` | `string` | ❌ | `01@@3664@010200` | statusCode |
| `success` | `boolean` | ❌ | `true` | success |
| `data` | `object` | ❌ | `data` | data |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.agent.gatewaytest.upload.preworkflow/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "user": "user",\n  "file": "file"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.agent.gatewaytest.upload.preworkflow/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "user": "user",
    "file": "file"
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