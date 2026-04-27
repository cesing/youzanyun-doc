---
apiName: "youzan.cardvoucher.openCardService.verify.checkCustomerPayCards.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "checkCustomerPayCards"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2025-05-16"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4803"
---
# youzan.cardvoucher.openCardService.verify.checkCustomerPayCards.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
创建订单前，校验卡列表是否可用
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.openCardService.verify.checkCustomerPayCards/1.0.0`
**请求参数 Schema**（10 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "客户号",
      "example": "SoQvb61L732695759723438080"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。当前请求的店铺id,连锁店铺为分店店铺di",
      "example": "92732278"
    },
    "items": {
      "type": "array",
      "description": "商品上下文"
    },
    "item_id": {
      "type": "integer",
      "description": "商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.items.inventory.get （查询仓库中商品）获取",
      "example": "399515043"
    },
    "outside": {
      "type": "boolean",
      "description": "是否为外部商品，非有赞IC商品设置为true,默认为IC商品",
      "example": "false"
    },
    "is_present": {
      "type": "boolean",
      "description": "是否是赠品",
      "example": "false"
    },
    "card_no_list": {
      "type": "array",
      "description": "卡号列表",
      "example": "[\"310200463069568\"]"
    },
    "card_type": {
      "type": "integer",
      "description": "卡类型",
      "example": "102"
    },
    "sales_channel_id": {
      "type": "integer",
      "description": "销售渠道Id",
      "example": "0"
    },
    "app_name": {
      "type": "string",
      "description": "应用名称",
      "example": "app_name"
    }
  },
  "required": [
    "yz_open_id",
    "kdt_id"
  ]
}
```
**请求参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `yz_open_id` | `integer` | ✅ | `SoQvb61L732695759723438080` | 客户号 |
| `kdt_id` | `integer` | ✅ | `92732278` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。当前请求的店铺id,连锁店铺为分店店铺di |
| `items` | `array` | ❌ | `` | 商品上下文 |
| `item_id` | `integer` | ❌ | `399515043` | 商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.item |
| `outside` | `boolean` | ❌ | `false` | 是否为外部商品，非有赞IC商品设置为true,默认为IC商品 |
| `is_present` | `boolean` | ❌ | `false` | 是否是赠品 |
| `card_no_list` | `array` | ❌ | `["310200463069568"]` | 卡号列表 |
| `card_type` | `integer` | ❌ | `102` | 卡类型 |
| `sales_channel_id` | `integer` | ❌ | `0` | 销售渠道Id |
| `app_name` | `string` | ❌ | `app_name` | 应用名称 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "返回数据"
    },
    "card_name": {
      "type": "string",
      "description": "卡名称",
      "example": "礼品卡"
    },
    "summary_card_no": {
      "type": "string",
      "description": "汇总卡号",
      "example": "310200463069568"
    },
    "balance": {
      "type": "integer",
      "description": "余额（分）",
      "example": "89720"
    },
    "yz_open_id": {
      "type": "string",
      "description": "有赞用户id",
      "example": "SoQvb61L732695759723438080"
    },
    "card_status": {
      "type": "string",
      "description": "卡状态。\"normal\"（正常状态）,\"freeze\"（C端冻结状态）,\"cmpfrz\"（完全冻结状态），\"close\"（注销），\"receding\"（退卡中），\"receded\"（已退卡）",
      "example": "normal"
    },
    "card_type": {
      "type": "integer",
      "description": "卡类型102储值卡。目前都是102的卡了",
      "example": "102"
    },
    "freezing_sum_dnom": {
      "type": "integer",
      "description": "被冻结的金额",
      "example": "0"
    },
    "is_exclusion": {
      "type": "boolean",
      "description": "是否互斥卡(无优惠卡)",
      "example": "false"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "网关返回码，表示本次请求是否成功。200 成功",
      "example": "200"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "card_name": "礼品卡",
  "summary_card_no": "310200463069568",
  "balance": "89720",
  "yz_open_id": "SoQvb61L732695759723438080",
  "card_status": "normal",
  "card_type": "102",
  "freezing_sum_dnom": "0"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 返回数据 |
| `card_name` | `string` | ❌ | `礼品卡` | 卡名称 |
| `summary_card_no` | `string` | ❌ | `310200463069568` | 汇总卡号 |
| `balance` | `integer` | ❌ | `89720` | 余额（分） |
| `yz_open_id` | `string` | ❌ | `SoQvb61L732695759723438080` | 有赞用户id |
| `card_status` | `string` | ❌ | `normal` | 卡状态。"normal"（正常状态）,"freeze"（C端冻结状态）,"cmpfrz"（完全冻结状态），"close"（注销），"receding"（退卡中） |
| `card_type` | `integer` | ❌ | `102` | 卡类型102储值卡。目前都是102的卡了 |
| `freezing_sum_dnom` | `integer` | ❌ | `0` | 被冻结的金额 |
| `is_exclusion` | `boolean` | ❌ | `false` | 是否互斥卡(无优惠卡) |
| `success` | `boolean` | ❌ | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `integer` | ❌ | `200` | 网关返回码，表示本次请求是否成功。200 成功 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.openCardService.verify.checkCustomerPayCards/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "yz_open_id": "SoQvb61L732695759723438080",\n  "kdt_id": "92732278",\n  "item_id": "399515043",\n  "outside": "false",\n  "is_present": "false",\n  "card_no_list": "[\"310200463069568\"]",\n  "card_type": "102",\n  "sales_channel_id": "0",\n  "app_name": "app_name"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.openCardService.verify.checkCustomerPayCards/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "yz_open_id": "SoQvb61L732695759723438080",
    "kdt_id": "92732278",
    "item_id": "399515043",
    "outside": "false",
    "is_present": "false",
    "card_no_list": "[\"310200463069568\"]",
    "card_type": "102",
    "sales_channel_id": "0",
    "app_name": "app_name"
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