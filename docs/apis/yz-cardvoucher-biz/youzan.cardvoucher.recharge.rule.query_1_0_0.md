---
apiName: "youzan.cardvoucher.recharge.rule.query.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "queryRechargeRule"
timeout: "1000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2021-02-24"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=2400"
---
# youzan.cardvoucher.recharge.rule.query.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
该接口用于查看商家某张储值卡模板的储值规则。目前仅支持查询充值设置中的礼包信息和卡面额信息。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.recharge.rule.query/1.0.0`
**超时时间**: `1000ms`
**鉴权方式**: `需要Token`
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `yz_open_id` | `integer` | ✅ 是 | `MVJ5w0uy585097513770430464` | 有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】 |
| `template_no` | `string` | ❌ 否 | `110101052740001` | 储值卡模版号，为空时默认查询店铺储值余额模板 |
| `channel_type` | `string` | ❌ 否 | `ALL` | 渠道类型限制 ALL:全部，ONLINE:线上充值，OFFLINE:线下充值，为空时默认值为ALL |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
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
      "type": "object",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 返回参数 |
| `product_infos` | `array` | ❌ 否 | `` | 可选充值面额列表 |
| `amount` | `integer` | ❌ 否 | `1000` | 充值金额（单位：分） |
| `gift_packs` | `array` | ❌ 否 | `` | 礼包信息列表 |
| `gift_pack_id` | `string` | ❌ 否 | `10000255` | 礼包ID |
| `gift_pack_name` | `string` | ❌ 否 | `充值10元送1元` | 礼包名称 |
| `fact_amount` | `integer` | ❌ 否 | `1000` | 实际支付金额（单位：分） |
| `rule_rights` | `object` | ❌ 否 | `` | 礼包具体权益 |
| `coupon_rights` | `array` | ❌ 否 | `` | 优惠券权益 |
| `coupon_id` | `string` | ❌ 否 | `1990` | 优惠券ID，即优惠券/码活动时的活动id，activity_id、coupon_id都是优惠活动id |
| `coupon_name` | `string` | ❌ 否 | `10元饮品券` | 优惠券名称 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=2400

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "yz_open_id": "MVJ5w0uy585097513770430464"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.recharge.rule.query/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "yz_open_id": "MVJ5w0uy585097513770430464"
}

response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

> ⚠️ **注意**：以上为示例代码，`access_token` 需要通过 OAuth2.0 流程获取。
> 真实调用地址和参数请以管理后台详情页为准。

---
## 5. 错误码
## 错误码

| 错误码 | 说明 | 处理建议 |
|--------|------|----------|
| 1000 | 系统内部错误 | 稍后重试或联系技术支持 |
| 1001 | 鉴权失败 | 检查 access_token 是否有效 |
| 1002 | 参数校验失败 | 检查必填参数是否完整 |
| 1003 | 权限不足 | 确认应用已开通对应接口权限 |
| 1004 | 频率超限 | 降低请求频率或申请更高配额 |
| 1005 | 资源不存在 | 检查请求的业务 ID 是否正确 |
| 1006 | 请求超时 | 增加超时时间或稍后重试 |
| 1007 | 账户欠费 | 完成账户充值后重试 |

> 更多错误码请参考：[有赞云错误码文档](https://doc.youzanyun.com) |

---
## 6. 内部服务信息
| 字段 | 值 |
|------|---|
| 协议类型 | dubbo |
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService` |
| 方法名称 | `queryRechargeRule` |
| 超时时间 | 1000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=2400)_