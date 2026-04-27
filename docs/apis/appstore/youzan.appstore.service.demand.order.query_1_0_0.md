---
apiName: "youzan.appstore.service.demand.order.query.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "customized_api"
method: "getDemandOrderDetail"
timeout: "5000"
authType: "无需认证"
type: "HTTP"
deprecated: false
since: "2021-07-29"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3092"
---
# youzan.appstore.service.demand.order.query.1.0.0
> **所属分组**: customized_api　**所属应用**: appstore
---
## 1. 场景说明
服务需求订单查询订单金额（纷享销客，连接器使用）当data返回为空时，代表kdt_id和订单号无对应关系。当data有值时表示请求成功
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.service.demand.order.query/1.0.0`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "tid": {
      "type": "string",
      "description": "有赞应用市场订单号",
      "example": "23202107272015210109053"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "demand_no": {
      "type": "string",
      "description": "需求号 （youzan.appstore.sevicedemand.query接口获取，demand_no字段）",
      "example": "12345"
    }
  },
  "required": [
    "tid",
    "kdt_id"
  ]
}
```
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `tid` | `string` | ✅ | `23202107272015210109053` | 有赞应用市场订单号 |
| `kdt_id` | `integer` | ✅ | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `demand_no` | `string` | ❌ | `12345` | 需求号 （youzan.appstore.sevicedemand.query接口获取，demand_no字段） |
---
## 3. 响应
**响应参数 Schema**（6 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "data"
    },
    "tid": {
      "type": "string",
      "description": "有赞应用市场订单号",
      "example": "23202107272015210109053"
    },
    "price": {
      "type": "integer",
      "description": "订单金额（分）",
      "example": "123"
    },
    "success": {
      "type": "boolean",
      "description": "true",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "200",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "successful",
      "example": "successful"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "tid": "23202107272015210109053",
  "price": "123",
  "success": "true",
  "code": "200",
  "message": "successful"
}
```
**响应参数明细**（6 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | data |
| `tid` | `string` | ❌ | `23202107272015210109053` | 有赞应用市场订单号 |
| `price` | `integer` | ❌ | `123` | 订单金额（分） |
| `success` | `boolean` | ❌ | `true` | true |
| `code` | `integer` | ❌ | `200` | 200 |
| `message` | `string` | ❌ | `successful` | successful |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.service.demand.order.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "tid": "23202107272015210109053",\n  "kdt_id": "88888",\n  "demand_no": "12345"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.service.demand.order.query/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "tid": "23202107272015210109053",
    "kdt_id": "88888",
    "demand_no": "12345"
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