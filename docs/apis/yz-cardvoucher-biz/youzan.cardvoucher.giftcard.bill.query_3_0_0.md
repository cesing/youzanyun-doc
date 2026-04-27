---
apiName: "youzan.cardvoucher.giftcard.bill.query.3.0.0"
version: "3.0.0"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "gift_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.giftcard.GiftCardService"
method: "queryGiftCardBillByCondition"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [retail, wsc, wsc_head, retail_head_high]
deprecated: false
since: "2019-08-13"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=580"
---
# youzan.cardvoucher.giftcard.bill.query.3.0.0
> **所属分组**: gift_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
最大限制查询条数5000（不含）；
新储值商家查询全部卡交易记录，老储值商家仅支持查询礼品卡交易记录；
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.bill.query/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（6 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": "请求参数"
    },
    "biz_type": {
      "type": "string",
      "description": "业务类型(\"RECHARGE\",\"充值\"),(\"GROUP_GIVE_RECHARGE\",\"赠送\"),(\"REFUND\",\"退款\"),(\"RECHARGE_REFUND\",\"充值退款\"),(\"PAY\",\"消费\"),(\"CARD_ACCOUNT_ADJUSTMENT_ADD\",\"调账增加\"),(\"CARD_ACCOUNT_ADJUSTMENT_SUBTRACT\",\"调账减少\"),(\"CARD_BALANCE_IMPORT_ADD\",\"导入增加\"),(\"CARD_BALANCE_IMPORT_SUBTRACT\",\"导入减少\"),(\"RECEDE_CARD\",\"退卡\"),(\"GIFT_CARD_ACTIVE\",\"激活\"),(\"RECHARGE_BONUS\",\"充值赠送\"),(\"REFUND_CLOSE_TRANSFER_IN\",\"退款销卡转入\"),(\"REFUND_CLOSE_TRANSFER_OUT\",\"退款销卡转出\"),(\"COMBINE_IN\",\"卡换绑转入\"),,(\"COMBINE_OUT\",\"卡换绑转出\")",
      "example": "PAY"
    },
    "begin_time": {
      "type": "string",
      "description": "支付/退款/激活的时间范围，查询begin_time之后发生的记录，格式：yyyy-MM-dd HH:mm:ss",
      "example": "2019-05-12 00:00:00"
    },
    "end_time": {
      "type": "string",
      "description": "支付/退款/激活的时间范围，查询end_time之前发生的记录，格式：yyyy-MM-dd HH:mm:ss",
      "example": "2019-08-13 00:00:00"
    },
    "page": {
      "type": "string",
      "description": "页码，从1开始正整数。如果记录较多请使用时间参数分割。page_size和page相乘总条数不能大于5000条",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页条数。默认20，最大为50，建议使用默认分页。如果记录较多请使用时间参数分割。page_size 和page相乘总条数不能大于5000条",
      "example": "20"
    }
  },
  "required": [
    "biz_type",
    "page",
    "page_size"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` | 请求参数 |
| `biz_type` | `string` | ✅ 是 | `PAY` | 业务类型("RECHARGE","充值"),("GROUP_GIVE_RECHARGE","赠送"),("REFUND" |
| `begin_time` | `string` | ❌ 否 | `2019-05-12 00:00:00` | 支付/退款/激活的时间范围，查询begin_time之后发生的记录，格式：yyyy-MM-dd HH:mm:ss |
| `end_time` | `string` | ❌ 否 | `2019-08-13 00:00:00` | 支付/退款/激活的时间范围，查询end_time之前发生的记录，格式：yyyy-MM-dd HH:mm:ss |
| `page` | `string` | ✅ 是 | `1` | 页码，从1开始正整数。如果记录较多请使用时间参数分割。page_size和page相乘总条数不能大于5000条 |
| `page_size` | `string` | ✅ 是 | `20` | 每页条数。默认20，最大为50，建议使用默认分页。如果记录较多请使用时间参数分割。page_size 和page相乘总条 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "integer",
      "description": "响应参数"
    },
    "paginator": {
      "type": "integer",
      "description": "分页模型"
    },
    "page": {
      "type": "string",
      "description": "页码，从1开始正整数",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页条数。默认20，最大为50",
      "example": "10"
    },
    "total_count": {
      "type": "string",
      "description": "查询数据总条数",
      "example": "100"
    },
    "items": {
      "type": "array",
      "description": "礼品卡详情"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "491491"
    },
    "mobile": {
      "type": "string",
      "description": "手机号码",
      "example": "13161559233"
    },
    "group_no": {
      "type": "string",
      "description": "卡号",
      "example": "310100029297523"
    },
    "sum_dnom": {
      "type": "string",
      "description": "卡余额，单位：分（sum_dnom=principal_dnom+bonus_dnom）",
      "example": "1000"
    },
    "principal_dnom": {
      "type": "string",
      "description": "卡本金金额，单位：分",
      "example": "500"
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
  "page_size": "10",
  "total_count": "100",
  "items": [],
  "kdt_id": "491491",
  "mobile": "13161559233"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `integer` | ❌ 否 | `` | 响应参数 |
| `paginator` | `integer` | ❌ 否 | `` | 分页模型 |
| `page` | `string` | ❌ 否 | `1` | 页码，从1开始正整数 |
| `page_size` | `string` | ❌ 否 | `10` | 每页条数。默认20，最大为50 |
| `total_count` | `string` | ❌ 否 | `100` | 查询数据总条数 |
| `items` | `array` | ❌ 否 | `` | 礼品卡详情 |
| `kdt_id` | `integer` | ❌ 否 | `491491` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `mobile` | `string` | ❌ 否 | `13161559233` | 手机号码 |
| `group_no` | `string` | ❌ 否 | `310100029297523` | 卡号 |
| `sum_dnom` | `string` | ❌ 否 | `1000` | 卡余额，单位：分（sum_dnom=principal_dnom+bonus_dnom） |
| `principal_dnom` | `string` | ❌ 否 | `500` | 卡本金金额，单位：分 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=580

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "biz_type": "PAY",
  "page": "1",
  "page_size": "20"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.bill.query/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "biz_type": "PAY",
  "page": "1",
  "page_size": "20"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.giftcard.GiftCardService` |
| 方法名称 | `queryGiftCardBillByCondition` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=580)_