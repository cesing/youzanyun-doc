---
apiName: "com.youzan.sogo.token.generate.1.0.0"
version: "1.0.0"
appName: "bifrost-developer"
apiGroup: "test"
method: "generateSogoToken"
timeout: "5000"
authType: "无需认证"
type: "HTTP"
deprecated: false
since: "2019-12-09"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/759"
---
# com.youzan.sogo.token.generate.1.0.0
> **所属分组**: test　**所属应用**: bifrost-developer
---
## 1. 场景说明
搜狗输入法回调方法生成token
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/com.youzan.sogo.token.generate/1.0.0`
**请求参数 Schema**（1 个参数）:
```json
{
  "type": "object",
  "properties": {
    "code": {
      "type": "string",
      "description": ""
    }
  },
  "required": [
    "code"
  ]
}
```
**请求参数明细**（1 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `code` | `string` | ✅ | `` |  |
---
## 3. 响应
**响应参数 Schema**（6 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": ""
    },
    "success": {
      "type": "boolean",
      "description": ""
    },
    "code": {
      "type": "integer",
      "description": ""
    },
    "message": {
      "type": "string",
      "description": ""
    },
    "request_id": {
      "type": "string",
      "description": ""
    },
    "error_data": {
      "type": "object",
      "description": ""
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "success": true,
  "code": 0,
  "message": "",
  "request_id": "",
  "error_data": {}
}
```
**响应参数明细**（6 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` |  |
| `success` | `boolean` | ❌ | `` |  |
| `code` | `integer` | ❌ | `` |  |
| `message` | `string` | ❌ | `` |  |
| `request_id` | `string` | ❌ | `` |  |
| `error_data` | `object` | ❌ | `` |  |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/com.youzan.sogo.token.generate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "code": "示例值"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/com.youzan.sogo.token.generate/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "code": "示例值"
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