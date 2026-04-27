---
apiName: "youzan.cardvoucher.delivery.card.list.info.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "retail_valuecard"
method: "pageQueryUserDeliveryCards"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-11-12"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3380"
---
# youzan.cardvoucher.delivery.card.list.info.1.0.0
> **所属分组**: retail_valuecard　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
分页查询店铺下用户的提货卡列表，返回结果中包含了可用和不可用的提货卡数据，如果提货卡不可用，结果中会告知不可用的原因，方便商家进行识别筛选。在使用提货卡核销功能时，需先通过该接口查询用户的提货卡信息。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.list.info/1.0.0`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "用户Id，用户手机号与用户Id二选一必填",
      "example": "7j3Gi1UH732330877366837248"
    },
    "mobile": {
      "type": "string",
      "description": "用户手机号，用户手机号与用户Id二选一必填",
      "example": "18573028713"
    },
    "card_no": {
      "type": "string",
      "description": "储值卡号",
      "example": "310200461055007"
    },
    "max_left_delivery_num": {
      "type": "integer",
      "description": "最大剩余可提货数量",
      "example": "3"
    },
    "min_left_delivery_num": {
      "type": "integer",
      "description": "最小剩余可提货数量",
      "example": "1"
    },
    "page_no": {
      "type": "integer",
      "description": "页号，不传默认为1，最大可传200",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "页码，不传默认为10，最大可传50",
      "example": "20"
    }
  },
  "required": []
}
```
**请求参数明细**（7 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `yz_open_id` | `integer` | ❌ | `7j3Gi1UH732330877366837248` | 用户Id，用户手机号与用户Id二选一必填 |
| `mobile` | `string` | ❌ | `18573028713` | 用户手机号，用户手机号与用户Id二选一必填 |
| `card_no` | `string` | ❌ | `310200461055007` | 储值卡号 |
| `max_left_delivery_num` | `integer` | ❌ | `3` | 最大剩余可提货数量 |
| `min_left_delivery_num` | `integer` | ❌ | `1` | 最小剩余可提货数量 |
| `page_no` | `integer` | ❌ | `1` | 页号，不传默认为1，最大可传200 |
| `page_size` | `integer` | ❌ | `20` | 页码，不传默认为10，最大可传50 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "integer",
      "description": "返回数据"
    },
    "paginator": {
      "type": "integer",
      "description": "分页信息"
    },
    "page": {
      "type": "integer",
      "description": "页号，默认为1，最大为200",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "页码，默认为10，最大为50",
      "example": "20"
    },
    "total_count": {
      "type": "integer",
      "description": "数据总数",
      "example": "2"
    },
    "items": {
      "type": "array",
      "description": "提货卡列表信息"
    },
    "mobile": {
      "type": "string",
      "description": "手机号码",
      "example": "18573028713"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "310200461055007"
    },
    "original_price": {
      "type": "integer",
      "description": "卡面额（单位为分）",
      "example": "10000"
    },
    "card_name": {
      "type": "string",
      "description": "卡模板名称",
      "example": "提货卡"
    },
    "status": {
      "type": "string",
      "description": "卡状态（normal：正常；freeze：停用；cmpfrz：冻结；close：销卡；receding：退卡中；receded：已退卡）",
      "example": "normal"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": 0,
  "paginator": 0,
  "page": "1",
  "page_size": "20",
  "total_count": "2",
  "items": [],
  "mobile": "18573028713",
  "card_no": "310200461055007"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `integer` | ❌ | `` | 返回数据 |
| `paginator` | `integer` | ❌ | `` | 分页信息 |
| `page` | `integer` | ❌ | `1` | 页号，默认为1，最大为200 |
| `page_size` | `integer` | ❌ | `20` | 页码，默认为10，最大为50 |
| `total_count` | `integer` | ❌ | `2` | 数据总数 |
| `items` | `array` | ❌ | `` | 提货卡列表信息 |
| `mobile` | `string` | ❌ | `18573028713` | 手机号码 |
| `card_no` | `string` | ❌ | `310200461055007` | 卡号 |
| `original_price` | `integer` | ❌ | `10000` | 卡面额（单位为分） |
| `card_name` | `string` | ❌ | `提货卡` | 卡模板名称 |
| `status` | `string` | ❌ | `normal` | 卡状态（normal：正常；freeze：停用；cmpfrz：冻结；close：销卡；receding：退卡中；receded：已退卡） |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.list.info/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "yz_open_id": "7j3Gi1UH732330877366837248",\n  "mobile": "18573028713",\n  "card_no": "310200461055007",\n  "max_left_delivery_num": "3",\n  "min_left_delivery_num": "1",\n  "page_no": "1",\n  "page_size": "20"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.list.info/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "yz_open_id": "7j3Gi1UH732330877366837248",
    "mobile": "18573028713",
    "card_no": "310200461055007",
    "max_left_delivery_num": "3",
    "min_left_delivery_num": "1",
    "page_no": "1",
    "page_size": "20"
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