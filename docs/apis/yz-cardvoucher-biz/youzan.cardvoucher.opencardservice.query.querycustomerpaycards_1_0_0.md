---
apiName: "youzan.cardvoucher.opencardservice.query.querycustomerpaycards.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.open.OpenCardService"
method: "queryCustomerPayCards"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, retail, retail_online, retail_offline]
deprecated: false
since: "2025-05-15"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4796"
---
# youzan.cardvoucher.opencardservice.query.querycustomerpaycards.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
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
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
      "type": "string",
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
      "type": "string",
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `yz_open_id` | `integer` | ✅ 是 | `MVJ5w0uy585097513770430464` | 客户号 |
| `items` | `array` | ✅ 是 | `` | 商品上下文 |
| `item_id` | `string` | ✅ 是 | `365112687` | 商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查 |
| `outside` | `boolean` | ❌ 否 | `false` | 是否为外部商品，非有赞IC商品设置为true,默认为IC商品 |
| `is_present` | `boolean` | ❌ 否 | `false` | 是否是赠品 |
| `kdt_id` | `integer` | ✅ 是 | `92732278` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。表示当前请求的店铺id。连锁店铺为分店店 |
| `pay_amount` | `integer` | ✅ 是 | `50` | 订单金额（单位：分） |
| `origin_amount` | `integer` | ✅ 是 | `100` | 订单原价金额（单位：分） |
| `distribution` | `boolean` | ❌ 否 | `false` | 当前交易请求是否包含分销商品 |
| `checked_list` | `string` | ❌ 否 | `["310200561086860"]` | 已选卡号列表。首次返回可用卡列表后，用户可以重新手动勾选自己想要支付的卡列表。 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 返回的数据 |
| `usable_list` | `array` | ❌ 否 | `` | 可用列表 |
| `publish_mch_id` | `string` | ❌ 否 | `170307112147366149` | 发卡机构商户号 |
| `publish_kdt_id` | `integer` | ❌ 否 | `` | 发卡机构店铺id |
| `card_name` | `string` | ❌ 否 | `干柴华的测试店铺` | 卡名称 |
| `summary_card_no` | `string` | ❌ 否 | `310200561086860` | 汇总卡号 |
| `balance` | `integer` | ❌ 否 | `200800` | 余额（分） |
| `use_specification` | `string` | ❌ 否 | `` | 使用说明 |
| `cancel_use_specification` | `string` | ❌ 否 | `` | 取消勾选使用说明 |
| `use_special_channel` | `boolean` | ❌ 否 | `false` | 使用特殊渠道(多人拼团积分商城秒杀赠品下单砍价0元购以外的) |
| `usable` | `boolean` | ❌ 否 | `true` | 是否可用 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4796

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "yz_open_id": "MVJ5w0uy585097513770430464",
  "items": "<items>",
  "item_id": "365112687",
  "kdt_id": "92732278",
  "pay_amount": "50"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.opencardservice.query.querycustomerpaycards/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "yz_open_id": "MVJ5w0uy585097513770430464",
  "items": "<items>",
  "item_id": "365112687",
  "kdt_id": "92732278",
  "pay_amount": "50"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.open.OpenCardService` |
| 方法名称 | `queryCustomerPayCards` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4796)_