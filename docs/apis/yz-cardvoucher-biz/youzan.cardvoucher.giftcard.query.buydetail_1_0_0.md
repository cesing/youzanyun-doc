---
apiName: "youzan.cardvoucher.giftcard.query.buydetail.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "queryBuyDetail"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-05-09"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4065"
---
# youzan.cardvoucher.giftcard.query.buydetail.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
礼品卡模板详情查询：可分页查询礼品卡模板详细信息。与个人中心->余额->礼品卡->购买礼品卡->礼品卡模板详细页面中的查询效果一致。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buydetail/1.0.0`
**请求参数 Schema**（1 个参数）:
```json
{
  "type": "object",
  "properties": {
    "template_no": {
      "type": "string",
      "description": "模版号",
      "example": "110204008016011"
    }
  },
  "required": [
    "template_no"
  ]
}
```
**请求参数明细**（1 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `template_no` | `string` | ✅ | `110204008016011` | 模版号 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "数据"
    },
    "template_name": {
      "type": "string",
      "description": "模板名称",
      "example": "礼品卡"
    },
    "template_img": {
      "type": "string",
      "description": "模板背景图片",
      "example": "https://img01.yzcdn.cn/upload_files/2023/02/06/FmHkosO7YgMI7h1KdDM7QcnEr7gE.png"
    },
    "instructions": {
      "type": "string",
      "description": "使用须知",
      "example": "购卡成功后，你可选择自己使用或赠送给朋友"
    },
    "product_infos": {
      "type": "array",
      "description": "卡面对应商品详细信息"
    },
    "original_price": {
      "type": "integer",
      "description": "原始单价，单位：分",
      "example": "10000"
    },
    "sale_price": {
      "type": "integer",
      "description": "实际销售单价，单位：分",
      "example": "8000"
    },
    "stock": {
      "type": "integer",
      "description": "库存 ，单位：张",
      "example": "79"
    },
    "gift_packs": {
      "type": "array",
      "description": "礼包信息"
    },
    "rule_rights": {
      "type": "string",
      "description": "规则权益"
    },
    "coupon_rights": {
      "type": "array",
      "description": "优惠券权益列表"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "template_name": "礼品卡",
  "template_img": "https://img01.yzcdn.cn/upload_files/2023/02/06/FmHkosO7YgMI7h1KdDM7QcnEr7gE.png",
  "instructions": "购卡成功后，你可选择自己使用或赠送给朋友",
  "product_infos": [],
  "original_price": "10000",
  "sale_price": "8000",
  "stock": "79"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 数据 |
| `template_name` | `string` | ❌ | `礼品卡` | 模板名称 |
| `template_img` | `string` | ❌ | `https://img01.yzcdn.cn/upload_files/2023` | 模板背景图片 |
| `instructions` | `string` | ❌ | `购卡成功后，你可选择自己使用或赠送给朋友` | 使用须知 |
| `product_infos` | `array` | ❌ | `` | 卡面对应商品详细信息 |
| `original_price` | `integer` | ❌ | `10000` | 原始单价，单位：分 |
| `sale_price` | `integer` | ❌ | `8000` | 实际销售单价，单位：分 |
| `stock` | `integer` | ❌ | `79` | 库存 ，单位：张 |
| `gift_packs` | `array` | ❌ | `` | 礼包信息 |
| `rule_rights` | `string` | ❌ | `` | 规则权益 |
| `coupon_rights` | `array` | ❌ | `` | 优惠券权益列表 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buydetail/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "template_no": "110204008016011"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buydetail/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "template_no": "110204008016011"
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