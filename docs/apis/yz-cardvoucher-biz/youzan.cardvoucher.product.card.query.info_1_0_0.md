---
apiName: "youzan.cardvoucher.product.card.query.info.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "pageQueryProductCardList"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-05-12"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2830"
---
# youzan.cardvoucher.product.card.query.info.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
分页查询主卡下的子卡信息，默认查询处于正常状态下的子卡信息
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.product.card.query.info/1.0.0`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "group_no": {
      "type": "string",
      "description": "主卡号",
      "example": "310200462159949"
    },
    "status": {
      "type": "integer",
      "description": "子卡状态：0-初始化；1-正常；2-已回收（失效）；3-已核销；4-被冻结（改状态暂没有使用）；5-激活失败；6-无效卡（作废），默认取值1",
      "example": "1"
    },
    "page_no": {
      "type": "integer",
      "description": "页号，默认取1，取值区间是[1,200]",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "分页大小，默认取10，取值区间是[1,50]",
      "example": "10"
    }
  },
  "required": [
    "group_no"
  ]
}
```
**请求参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `group_no` | `string` | ✅ | `310200462159949` | 主卡号 |
| `status` | `integer` | ❌ | `1` | 子卡状态：0-初始化；1-正常；2-已回收（失效）；3-已核销；4-被冻结（改状态暂没有使用）；5-激活失败；6-无效卡（作废），默认取值1 |
| `page_no` | `integer` | ❌ | `1` | 页号，默认取1，取值区间是[1,200] |
| `page_size` | `integer` | ❌ | `10` | 分页大小，默认取10，取值区间是[1,50] |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "integer",
      "description": "返回结果"
    },
    "paginator": {
      "type": "integer",
      "description": "分页信息"
    },
    "page_no": {
      "type": "integer",
      "description": "页号",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "分页大小",
      "example": "10"
    },
    "total_count": {
      "type": "integer",
      "description": "数据总数",
      "example": "1"
    },
    "items": {
      "type": "array",
      "description": "数据"
    },
    "card_no": {
      "type": "string",
      "description": "子卡号",
      "example": "210200462162308"
    },
    "create_time": {
      "type": "string",
      "description": "创建时间",
      "example": "1620791833000"
    },
    "balance": {
      "type": "number",
      "description": "余额（元）",
      "example": "10.0"
    },
    "success": {
      "type": "boolean",
      "description": "接口调用是否成功",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "接口调用结果码",
      "example": "200"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": 0,
  "paginator": 0,
  "page_no": "1",
  "page_size": "10",
  "total_count": "1",
  "items": [],
  "card_no": "210200462162308",
  "create_time": "1620791833000"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `integer` | ❌ | `` | 返回结果 |
| `paginator` | `integer` | ❌ | `` | 分页信息 |
| `page_no` | `integer` | ❌ | `1` | 页号 |
| `page_size` | `integer` | ❌ | `10` | 分页大小 |
| `total_count` | `integer` | ❌ | `1` | 数据总数 |
| `items` | `array` | ❌ | `` | 数据 |
| `card_no` | `string` | ❌ | `210200462162308` | 子卡号 |
| `create_time` | `string` | ❌ | `1620791833000` | 创建时间 |
| `balance` | `number` | ❌ | `10.0` | 余额（元） |
| `success` | `boolean` | ❌ | `true` | 接口调用是否成功 |
| `code` | `integer` | ❌ | `200` | 接口调用结果码 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.product.card.query.info/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "group_no": "310200462159949",\n  "status": "1",\n  "page_no": "1",\n  "page_size": "10"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.product.card.query.info/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "group_no": "310200462159949",
    "status": "1",
    "page_no": "1",
    "page_size": "10"
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