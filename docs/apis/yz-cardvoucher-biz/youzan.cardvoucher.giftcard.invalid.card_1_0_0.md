---
apiName: "youzan.cardvoucher.giftcard.invalid.card.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "invalidCard"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-04-07"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4030"
---
# youzan.cardvoucher.giftcard.invalid.card.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
失效礼品卡的电子卡，仅激活之前的卡可进行失效
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.invalid.card/1.0.0`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "operator_open_id": {
      "type": "integer",
      "description": "操作人",
      "example": "xvJrRKC0702883114891939840"
    },
    "card_no": {
      "type": "string",
      "description": "电子卡号",
      "example": "310200549496389"
    }
  },
  "required": [
    "operator_open_id",
    "card_no"
  ]
}
```
**请求参数明细**（2 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `operator_open_id` | `integer` | ✅ | `xvJrRKC0702883114891939840` | 操作人 |
| `card_no` | `string` | ✅ | `310200549496389` | 电子卡号 |
---
## 3. 响应
**响应参数 Schema**（7 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": ""
    },
    "invalid_result": {
      "type": "boolean",
      "description": "失效结果，true 成功，false失败",
      "example": "true"
    },
    "success": {
      "type": "boolean",
      "description": "是否请求成功",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "",
      "example": "200"
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
  "invalid_result": "true",
  "success": "true",
  "code": "200",
  "message": "",
  "request_id": "",
  "error_data": {}
}
```
**响应参数明细**（7 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` |  |
| `invalid_result` | `boolean` | ❌ | `true` | 失效结果，true 成功，false失败 |
| `success` | `boolean` | ❌ | `true` | 是否请求成功 |
| `code` | `integer` | ❌ | `200` |  |
| `message` | `string` | ❌ | `` |  |
| `request_id` | `string` | ❌ | `` |  |
| `error_data` | `object` | ❌ | `` |  |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.invalid.card/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "operator_open_id": "xvJrRKC0702883114891939840",\n  "card_no": "310200549496389"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.invalid.card/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "operator_open_id": "xvJrRKC0702883114891939840",
    "card_no": "310200549496389"
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