---
apiName: "youzan.cardvoucher.recharge.rule.query.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "queryRechargeRule"
timeout: "1000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-02-24"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2400"
---
# youzan.cardvoucher.recharge.rule.query.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
该接口用于查看商家某张储值卡模板的储值规则。目前仅支持查询充值设置中的礼包信息和卡面额信息。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.recharge.rule.query/1.0.0`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】",
      "example": "MVJ5w0uy585097513770430464"
    },
    "template_no": {
      "type": "string",
      "description": "储值卡模版号，为空时默认查询店铺储值余额模板",
      "example": "110101052740001"
    },
    "channel_type": {
      "type": "string",
      "description": "渠道类型限制 ALL:全部，ONLINE:线上充值，OFFLINE:线下充值，为空时默认值为ALL",
      "example": "ALL"
    }
  },
  "required": [
    "yz_open_id"
  ]
}
```
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `yz_open_id` | `integer` | ✅ | `MVJ5w0uy585097513770430464` | 有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】 |
| `template_no` | `string` | ❌ | `110101052740001` | 储值卡模版号，为空时默认查询店铺储值余额模板 |
| `channel_type` | `string` | ❌ | `ALL` | 渠道类型限制 ALL:全部，ONLINE:线上充值，OFFLINE:线下充值，为空时默认值为ALL |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "返回参数"
    },
    "product_infos": {
      "type": "array",
      "description": "可选充值面额列表"
    },
    "amount": {
      "type": "integer",
      "description": "充值金额（单位：分）",
      "example": "1000"
    },
    "gift_packs": {
      "type": "array",
      "description": "礼包信息列表"
    },
    "gift_pack_id": {
      "type": "string",
      "description": "礼包ID",
      "example": "10000255"
    },
    "gift_pack_name": {
      "type": "string",
      "description": "礼包名称",
      "example": "充值10元送1元"
    },
    "fact_amount": {
      "type": "integer",
      "description": "实际支付金额（单位：分）",
      "example": "1000"
    },
    "rule_rights": {
      "type": "string",
      "description": "礼包具体权益"
    },
    "coupon_rights": {
      "type": "array",
      "description": "优惠券权益"
    },
    "coupon_id": {
      "type": "string",
      "description": "优惠券ID，即优惠券/码活动时的活动id，activity_id、coupon_id都是优惠活动id",
      "example": "1990"
    },
    "coupon_name": {
      "type": "string",
      "description": "优惠券名称",
      "example": "10元饮品券"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "product_infos": [],
  "amount": "1000",
  "gift_packs": [],
  "gift_pack_id": "10000255",
  "gift_pack_name": "充值10元送1元",
  "fact_amount": "1000",
  "rule_rights": ""
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 返回参数 |
| `product_infos` | `array` | ❌ | `` | 可选充值面额列表 |
| `amount` | `integer` | ❌ | `1000` | 充值金额（单位：分） |
| `gift_packs` | `array` | ❌ | `` | 礼包信息列表 |
| `gift_pack_id` | `string` | ❌ | `10000255` | 礼包ID |
| `gift_pack_name` | `string` | ❌ | `充值10元送1元` | 礼包名称 |
| `fact_amount` | `integer` | ❌ | `1000` | 实际支付金额（单位：分） |
| `rule_rights` | `string` | ❌ | `` | 礼包具体权益 |
| `coupon_rights` | `array` | ❌ | `` | 优惠券权益 |
| `coupon_id` | `string` | ❌ | `1990` | 优惠券ID，即优惠券/码活动时的活动id，activity_id、coupon_id都是优惠活动id |
| `coupon_name` | `string` | ❌ | `10元饮品券` | 优惠券名称 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.recharge.rule.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "yz_open_id": "MVJ5w0uy585097513770430464",\n  "template_no": "110101052740001",\n  "channel_type": "ALL"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.recharge.rule.query/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "yz_open_id": "MVJ5w0uy585097513770430464",
    "template_no": "110101052740001",
    "channel_type": "ALL"
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