---
apiName: "youzan.cardvoucher.card.bill.query.3.0.1"
version: "3.0.1"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "pageQueryValueCardBill"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail]
deprecated: false
since: "2019-07-22"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=560"
---
# youzan.cardvoucher.card.bill.query.3.0.1
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
用户卡账单查询       
备注说明：ADJUST_ADD、ADJUST_SUBTRACT为新增查询业务类型，为兼容历史接口查询返回，当biz_type输入为ADJUST_ADD或ADJUST_SUBTRACT时，返回类型按照此类型返回，否则会算入其他类型中

---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.bill.query/3.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】",
      "example": "MVJ5w0uy585097513770430464"
    },
    "card_no": {
      "type": "string",
      "description": "汇总卡卡号",
      "example": "310201043501229"
    },
    "biz_type": {
      "type": "string",
      "description": "业务类型,ALL(全部) RECHARGE(充值) PAY(支付消费) REFUND(退款) OTHER(其他) ADJUST_ADD(调账-增加) ADJUST_SUBTRACT(调账-减少)",
      "example": "ALL"
    },
    "start_time": {
      "type": "string",
      "description": "开始时间，格式：yyyy-MM-dd HH:mm:ss",
      "example": "2019-01-01 00:00:00"
    },
    "end_time": {
      "type": "string",
      "description": "结束时间，格式：yyyy-MM-dd HH:mm:ss",
      "example": "2019-07-24 00:00:00"
    },
    "page": {
      "type": "string",
      "description": "页码，从1开始正整数。如果记录较多请使用时间参数分割",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页条数。默认20条，最大不能超过50，建议使用默认分页。如果记录较多请使用时间参数分割",
      "example": "20"
    }
  },
  "required": [
    "yz_open_id",
    "card_no",
    "biz_type"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `yz_open_id` | `integer` | ✅ 是 | `MVJ5w0uy585097513770430464` | 有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】 |
| `card_no` | `string` | ✅ 是 | `310201043501229` | 汇总卡卡号 |
| `biz_type` | `string` | ✅ 是 | `ALL` | 业务类型,ALL(全部) RECHARGE(充值) PAY(支付消费) REFUND(退款) OTHER(其他) ADJ |
| `start_time` | `string` | ❌ 否 | `2019-01-01 00:00:00` | 开始时间，格式：yyyy-MM-dd HH:mm:ss |
| `end_time` | `string` | ❌ 否 | `2019-07-24 00:00:00` | 结束时间，格式：yyyy-MM-dd HH:mm:ss |
| `page` | `string` | ❌ 否 | `1` | 页码，从1开始正整数。如果记录较多请使用时间参数分割 |
| `page_size` | `string` | ❌ 否 | `20` | 每页条数。默认20条，最大不能超过50，建议使用默认分页。如果记录较多请使用时间参数分割 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "integer",
      "description": "请求数据"
    },
    "paginator": {
      "type": "integer",
      "description": "分页信息"
    },
    "page": {
      "type": "string",
      "description": "页码，从1开始正整数",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页条数。默认20条",
      "example": "20"
    },
    "total_count": {
      "type": "string",
      "description": "查询获得数据总条数",
      "example": "29"
    },
    "items": {
      "type": "array",
      "description": "实体信息"
    },
    "shop_name": {
      "type": "string",
      "description": "店铺名称",
      "example": "微商城开放平台测试"
    },
    "water_no": {
      "type": "string",
      "description": "支付工具业务流水号",
      "example": "190724142115000000"
    },
    "symbol": {
      "type": "boolean",
      "description": "资金流向，true：资金增加，false：资金减少",
      "example": "true"
    },
    "biz_type": {
      "type": "string",
      "description": "业务类型，ALL：全部 RECHARGE：充值 PAY：支付消费 REFUND：退款 OTHER：其他",
      "example": "RECHARGE"
    },
    "biz_type_desc": {
      "type": "string",
      "description": "业务类型描述",
      "example": "充值-微商城开放平台测试"
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
  "total_count": "29",
  "items": [],
  "shop_name": "微商城开放平台测试",
  "water_no": "190724142115000000"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `integer` | ❌ 否 | `` | 请求数据 |
| `paginator` | `integer` | ❌ 否 | `` | 分页信息 |
| `page` | `string` | ❌ 否 | `1` | 页码，从1开始正整数 |
| `page_size` | `string` | ❌ 否 | `20` | 每页条数。默认20条 |
| `total_count` | `string` | ❌ 否 | `29` | 查询获得数据总条数 |
| `items` | `array` | ❌ 否 | `` | 实体信息 |
| `shop_name` | `string` | ❌ 否 | `微商城开放平台测试` | 店铺名称 |
| `water_no` | `string` | ❌ 否 | `190724142115000000` | 支付工具业务流水号 |
| `symbol` | `boolean` | ❌ 否 | `true` | 资金流向，true：资金增加，false：资金减少 |
| `biz_type` | `string` | ❌ 否 | `RECHARGE` | 业务类型，ALL：全部 RECHARGE：充值 PAY：支付消费 REFUND：退款 OTHER：其他 |
| `biz_type_desc` | `string` | ❌ 否 | `充值-微商城开放平台测试` | 业务类型描述 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=560

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "yz_open_id": "MVJ5w0uy585097513770430464",
  "card_no": "310201043501229",
  "biz_type": "ALL"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.bill.query/3.0.1"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "yz_open_id": "MVJ5w0uy585097513770430464",
  "card_no": "310201043501229",
  "biz_type": "ALL"
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
| 方法名称 | `pageQueryValueCardBill` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=560)_