---
apiName: "youzan.cardvoucher.opencardservice.query.querycustomerpaycards.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "queryCustomerPayCards"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2025-05-15"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4796"
---
# youzan.cardvoucher.opencardservice.query.querycustomerpaycards.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
下单页查询用户可用储值卡列表，返回相关的余额卡、礼品卡信息。
针对开放接口，只提供简单的查询可用卡列表逻辑。
支持的功能
1：如果当前购买的商品不在卡模板配置的【适用商品】范围内，那么该卡不可用
2：如果当前所在店铺不在卡模板配置的【适用店铺】范围内，那么该卡不可用

不支持：
1.不支持判断  卡模板设置的【优惠设置】
2.不支持判断 卡模板设置的【仅限此卡支付时享受相应折扣优惠】
3.不支持判断【储值会员】模式下，卡模板设置的【余额全额支付时可享受会员优惠】
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.opencardservice.query.querycustomerpaycards/1.0.0`
**请求参数 Schema**（10 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "客户号",
      "example": "MVJ5w0uy585097513770430464"
    },
    "items": {
      "type": "array",
      "description": "商品上下文"
    },
    "item_id": {
      "type": "integer",
      "description": "商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.items.inventory.get （查询仓库中商品）获取",
      "example": "365112687"
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
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。表示当前请求的店铺id。连锁店铺为分店店铺id",
      "example": "92732278"
    },
    "pay_amount": {
      "type": "integer",
      "description": "订单金额（单位：分）",
      "example": "50"
    },
    "origin_amount": {
      "type": "integer",
      "description": "订单原价金额（单位：分）",
      "example": "100"
    },
    "distribution": {
      "type": "boolean",
      "description": "当前交易请求是否包含分销商品",
      "example": "false"
    },
    "checked_list": {
      "type": "array",
      "description": "已选卡号列表。首次返回可用卡列表后，用户可以重新手动勾选自己想要支付的卡列表。",
      "example": "[\"310200561086860\"]"
    }
  },
  "required": [
    "yz_open_id",
    "items",
    "item_id",
    "kdt_id",
    "pay_amount",
    "origin_amount"
  ]
}
```
**请求参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `yz_open_id` | `integer` | ✅ | `MVJ5w0uy585097513770430464` | 客户号 |
| `items` | `array` | ✅ | `` | 商品上下文 |
| `item_id` | `integer` | ✅ | `365112687` | 商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.item |
| `outside` | `boolean` | ❌ | `false` | 是否为外部商品，非有赞IC商品设置为true,默认为IC商品 |
| `is_present` | `boolean` | ❌ | `false` | 是否是赠品 |
| `kdt_id` | `integer` | ✅ | `92732278` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。表示当前请求的店铺id。连锁店铺为分店店铺id |
| `pay_amount` | `integer` | ✅ | `50` | 订单金额（单位：分） |
| `origin_amount` | `integer` | ✅ | `100` | 订单原价金额（单位：分） |
| `distribution` | `boolean` | ❌ | `false` | 当前交易请求是否包含分销商品 |
| `checked_list` | `array` | ❌ | `["310200561086860"]` | 已选卡号列表。首次返回可用卡列表后，用户可以重新手动勾选自己想要支付的卡列表。 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "返回的数据"
    },
    "usable_list": {
      "type": "array",
      "description": "可用列表"
    },
    "publish_mch_id": {
      "type": "string",
      "description": "发卡机构商户号",
      "example": "170307112147366149"
    },
    "publish_kdt_id": {
      "type": "integer",
      "description": "发卡机构店铺id"
    },
    "card_name": {
      "type": "string",
      "description": "卡名称",
      "example": "干柴华的测试店铺"
    },
    "summary_card_no": {
      "type": "string",
      "description": "汇总卡号",
      "example": "310200561086860"
    },
    "balance": {
      "type": "integer",
      "description": "余额（分）",
      "example": "200800"
    },
    "use_specification": {
      "type": "string",
      "description": "使用说明"
    },
    "cancel_use_specification": {
      "type": "string",
      "description": "取消勾选使用说明"
    },
    "use_special_channel": {
      "type": "boolean",
      "description": "使用特殊渠道(多人拼团积分商城秒杀赠品下单砍价0元购以外的)",
      "example": "false"
    },
    "usable": {
      "type": "boolean",
      "description": "是否可用",
      "example": "true"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "usable_list": [],
  "publish_mch_id": "170307112147366149",
  "publish_kdt_id": 0,
  "card_name": "干柴华的测试店铺",
  "summary_card_no": "310200561086860",
  "balance": "200800",
  "use_specification": ""
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 返回的数据 |
| `usable_list` | `array` | ❌ | `` | 可用列表 |
| `publish_mch_id` | `string` | ❌ | `170307112147366149` | 发卡机构商户号 |
| `publish_kdt_id` | `integer` | ❌ | `` | 发卡机构店铺id |
| `card_name` | `string` | ❌ | `干柴华的测试店铺` | 卡名称 |
| `summary_card_no` | `string` | ❌ | `310200561086860` | 汇总卡号 |
| `balance` | `integer` | ❌ | `200800` | 余额（分） |
| `use_specification` | `string` | ❌ | `` | 使用说明 |
| `cancel_use_specification` | `string` | ❌ | `` | 取消勾选使用说明 |
| `use_special_channel` | `boolean` | ❌ | `false` | 使用特殊渠道(多人拼团积分商城秒杀赠品下单砍价0元购以外的) |
| `usable` | `boolean` | ❌ | `true` | 是否可用 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.opencardservice.query.querycustomerpaycards/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "yz_open_id": "MVJ5w0uy585097513770430464",\n  "items": [],\n  "item_id": "365112687",\n  "outside": "false",\n  "is_present": "false",\n  "kdt_id": "92732278",\n  "pay_amount": "50",\n  "origin_amount": "100",\n  "distribution": "false",\n  "checked_list": "[\"310200561086860\"]"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.opencardservice.query.querycustomerpaycards/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "yz_open_id": "MVJ5w0uy585097513770430464",
    "items": [],
    "item_id": "365112687",
    "outside": "false",
    "is_present": "false",
    "kdt_id": "92732278",
    "pay_amount": "50",
    "origin_amount": "100",
    "distribution": "false",
    "checked_list": "[\"310200561086860\"]"
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