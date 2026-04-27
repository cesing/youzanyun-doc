---
apiName: "youzan.cardvoucher.valuecard.fund.pay.get.3.0.0"
version: "3.0.0"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "payQuery"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail]
deprecated: false
since: "2020-01-18"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=802"
---
# youzan.cardvoucher.valuecard.fund.pay.get.3.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
支付结果查询，支付受理成功后（youzan.cardvoucher.valuecard.fund.pay），通过此接口获取最后支付结果。也可以通过监听支付结果消息来确认支付结果，两种方式结果完全一致
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.pay.get/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": "支付查询请求"
    },
    "pay_request_no": {
      "type": "string",
      "description": "支付请求号（二选一）",
      "example": "1579307828741yRG5p"
    },
    "pay_order_no": {
      "type": "string",
      "description": "支付订单号（二选一）",
      "example": "CDP200118075307000001"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` | 支付查询请求 |
| `pay_request_no` | `string` | ❌ 否 | `1579307828741yRG5p` | 支付请求号（二选一） |
| `pay_order_no` | `string` | ❌ 否 | `CDP200118075307000001` | 支付订单号（二选一） |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "支付查询结果"
    },
    "pay_request_no": {
      "type": "string",
      "description": "支付请求号",
      "example": "1579307828741yRG5p"
    },
    "pay_order_no": {
      "type": "string",
      "description": "支付订单号",
      "example": "CDP200118075307000001"
    },
    "status": {
      "type": "string",
      "description": "支付状态SUCCES：支付成功FAIL：支付失败ING：支付中",
      "example": "FAIL"
    },
    "code": {
      "type": "string",
      "description": "结果码。200支付成功/支付中，1001支付失败",
      "example": "1001"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "支付失败"
    },
    "amount": {
      "type": "string",
      "description": "储值支付金额",
      "example": "3000000"
    },
    "kdt_id": {
      "type": "integer",
      "description": "受理店铺Id",
      "example": "693301242"
    },
    "buyer_id": {
      "type": "integer",
      "description": "客户Id",
      "example": "693301242"
    },
    "card_list": {
      "type": "string",
      "description": "卡号列表",
      "example": "[\"310200292403962\"]"
    },
    "pay_time": {
      "type": "string",
      "description": "支付时间，格式yyyy-MM-ddHH:mm:ss",
      "example": "2020-01-18 08:37:08.0"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "pay_request_no": "1579307828741yRG5p",
  "pay_order_no": "CDP200118075307000001",
  "status": "FAIL",
  "code": "1001",
  "msg": "支付失败",
  "amount": "3000000",
  "kdt_id": "693301242"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 支付查询结果 |
| `pay_request_no` | `string` | ❌ 否 | `1579307828741yRG5p` | 支付请求号 |
| `pay_order_no` | `string` | ❌ 否 | `CDP200118075307000001` | 支付订单号 |
| `status` | `string` | ❌ 否 | `FAIL` | 支付状态SUCCES：支付成功FAIL：支付失败ING：支付中 |
| `code` | `string` | ❌ 否 | `1001` | 结果码。200支付成功/支付中，1001支付失败 |
| `msg` | `string` | ❌ 否 | `支付失败` | 状态描述 |
| `amount` | `string` | ❌ 否 | `3000000` | 储值支付金额 |
| `kdt_id` | `integer` | ❌ 否 | `693301242` | 受理店铺Id |
| `buyer_id` | `integer` | ❌ 否 | `693301242` | 客户Id |
| `card_list` | `string` | ❌ 否 | `["310200292403962"]` | 卡号列表 |
| `pay_time` | `string` | ❌ 否 | `2020-01-18 08:37:08.0` | 支付时间，格式yyyy-MM-ddHH:mm:ss |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=802

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.pay.get/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {}

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
| 方法名称 | `payQuery` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=802)_