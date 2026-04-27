---
apiName: "youzan.appstore.sevicedemand.upload.status.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "customized_api"
method: "updateDemandStatus"
timeout: "5000"
authType: "无需认证"
type: "HTTP"
deprecated: false
since: "2021-05-07"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2802"
---
# youzan.appstore.sevicedemand.upload.status.1.0.0
> **所属分组**: customized_api　**所属应用**: appstore
---
## 1. 场景说明
修改服务市场需求状态
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.sevicedemand.upload.status/1.0.0`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "service_demand_status_update_request": {
      "type": "string",
      "description": "请求集"
    },
    "demand_no": {
      "type": "string",
      "description": "需求编号",
      "example": "864642465397448704"
    },
    "status": {
      "type": "integer",
      "description": "需求状态@seeServiceDemandStatusEnum",
      "example": "10"
    },
    "remark": {
      "type": "string",
      "description": "需求备注",
      "example": "需求状态变更备注"
    }
  },
  "required": [
    "demand_no",
    "status",
    "remark"
  ]
}
```
**请求参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `service_demand_status_update_request` | `string` | ❌ | `` | 请求集 |
| `demand_no` | `string` | ✅ | `864642465397448704` | 需求编号 |
| `status` | `integer` | ✅ | `10` | 需求状态@seeServiceDemandStatusEnum |
| `remark` | `string` | ✅ | `需求状态变更备注` | 需求备注 |
---
## 3. 响应
**响应参数 Schema**（5 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "boolean",
      "description": "data",
      "example": "true"
    },
    "success": {
      "type": "boolean",
      "description": "是否成功",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "结果code",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "结果message",
      "example": "成功"
    },
    "request_id": {
      "type": "string",
      "description": "请求id",
      "example": "111111"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "true",
  "success": "true",
  "code": "200",
  "message": "成功",
  "request_id": "111111"
}
```
**响应参数明细**（5 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `boolean` | ❌ | `true` | data |
| `success` | `boolean` | ❌ | `true` | 是否成功 |
| `code` | `integer` | ❌ | `200` | 结果code |
| `message` | `string` | ❌ | `成功` | 结果message |
| `request_id` | `string` | ❌ | `111111` | 请求id |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.sevicedemand.upload.status/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "demand_no": "864642465397448704",\n  "status": "10",\n  "remark": "需求状态变更备注"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.sevicedemand.upload.status/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "demand_no": "864642465397448704",
    "status": "10",
    "remark": "需求状态变更备注"
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