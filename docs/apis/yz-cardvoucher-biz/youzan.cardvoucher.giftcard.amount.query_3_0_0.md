---
apiName: "youzan.cardvoucher.giftcard.amount.query.3.0.0"
version: "3.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "gift_card"
method: "queryGiftCardAmout"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2019-06-27"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/418"
---
# youzan.cardvoucher.giftcard.amount.query.3.0.0
> **所属分组**: gift_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
根据店铺id查询该店铺下礼品卡的激活总数、激活金额总数、激活未使用的金额总数
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.amount.query/3.0.0`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "string",
      "description": ""
    },
    "search_kdt_id": {
      "type": "integer",
      "description": "查询店铺id，非必传，为了以后兼容",
      "example": "491491"
    },
    "card_type": {
      "type": "integer",
      "description": "卡类型（101：礼品卡）",
      "example": "101"
    }
  },
  "required": [
    "request",
    "card_type"
  ]
}
```
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `request` | `string` | ✅ | `` |  |
| `search_kdt_id` | `integer` | ❌ | `491491` | 查询店铺id，非必传，为了以后兼容 |
| `card_type` | `integer` | ✅ | `101` | 卡类型（101：礼品卡） |
---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": ""
    },
    "card_active_total": {
      "type": "integer",
      "description": "卡激活的数量",
      "example": "10"
    },
    "card_active_amout": {
      "type": "integer",
      "description": "卡激活的金额",
      "example": "10"
    },
    "card_remainingmount": {
      "type": "integer",
      "description": "卡剩余的金额",
      "example": "10"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "successful"
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
  "card_active_total": "10",
  "card_active_amout": "10",
  "card_remainingmount": "10",
  "success": "true",
  "code": "200",
  "message": "successful",
  "request_id": ""
}
```
**响应参数明细**（9 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` |  |
| `card_active_total` | `integer` | ❌ | `10` | 卡激活的数量 |
| `card_active_amout` | `integer` | ❌ | `10` | 卡激活的金额 |
| `card_remainingmount` | `integer` | ❌ | `10` | 卡剩余的金额 |
| `success` | `boolean` | ❌ | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `integer` | ❌ | `200` | 网关返回码，表示本次请求是否成功。200 :成功。 |
| `message` | `string` | ❌ | `successful` | 网关返回码描述 |
| `request_id` | `string` | ❌ | `` |  |
| `error_data` | `object` | ❌ | `` |  |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.amount.query/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "request": "示例值",\n  "search_kdt_id": "491491",\n  "card_type": "101"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.amount.query/3.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "request": "示例值",
    "search_kdt_id": "491491",
    "card_type": "101"
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