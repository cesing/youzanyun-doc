---
apiName: "youzan.cardvoucher.valuecard.fund.recharge.get.3.0.0"
version: "3.0.0"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "rechargeQuery"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail]
deprecated: false
since: "2019-03-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=109"
---
# youzan.cardvoucher.valuecard.fund.recharge.get.3.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
充值结果查询，充值受理成功后（youzan.cardvoucher.valuecard.fund.recharge），通过此接口获取最后充值结果。也可以通过监听充值结果消息来确认充值结果，两种方式结果完全一致。注意：仅支持查询通过有赞云API接口充值的订单。
推荐使用新版本（3.0.1）
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.recharge.get/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "recharge_request_no": {
      "type": "string",
      "description": "充值请求号（recharge_order_no或recharge_request_no二选一）取值自：youzan.cardvoucher.valuecard.fund.recharge中的recharge_request_no",
      "example": "RN190284744501249"
    },
    "recharge_order_no": {
      "type": "string",
      "description": "充值订单号（recharge_order_no或recharge_request_no二选一）取值自：youzan.cardvoucher.valuecard.fund.recharge中的recharge_order_no",
      "example": "CDRG190723152420000049"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `recharge_request_no` | `string` | ❌ 否 | `RN190284744501249` | 充值请求号（recharge_order_no或recharge_request_no二选一）取值自：youzan.ca |
| `recharge_order_no` | `string` | ❌ 否 | `CDRG190723152420000049` | 充值订单号（recharge_order_no或recharge_request_no二选一）取值自：youzan.ca |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "接口返回数据"
    },
    "recharge_request_no": {
      "type": "string",
      "description": "充值请求号",
      "example": "weixiao20190724001"
    },
    "recharge_order_no": {
      "type": "string",
      "description": "充值订单号",
      "example": "CDRG190723152420000049"
    },
    "status": {
      "type": "string",
      "description": "充值结果状态，SUCCESS:充值成功, FAIL:充值失败, ING:充值中",
      "example": "SUCCESS"
    },
    "code": {
      "type": "string",
      "description": "网关返回码，表示本次请求是否成功。200 成功",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "充值成功"
    },
    "amount": {
      "type": "string",
      "description": "储值充值金额，单位：分",
      "example": "130"
    },
    "success": {
      "type": "string",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "请求成功"
    },
    "request_id": {
      "type": "string",
      "description": "已废弃",
      "example": "已废弃"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "recharge_request_no": "weixiao20190724001",
  "recharge_order_no": "CDRG190723152420000049",
  "status": "SUCCESS",
  "code": "200",
  "msg": "充值成功",
  "amount": "130",
  "success": "true"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 接口返回数据 |
| `recharge_request_no` | `string` | ❌ 否 | `weixiao20190724001` | 充值请求号 |
| `recharge_order_no` | `string` | ❌ 否 | `CDRG190723152420000049` | 充值订单号 |
| `status` | `string` | ❌ 否 | `SUCCESS` | 充值结果状态，SUCCESS:充值成功, FAIL:充值失败, ING:充值中 |
| `code` | `string` | ❌ 否 | `200` | 结果码，200：充值成功、充值中 1001：充值失败 1002：充值失败，店铺未签约或签约已过期 1003：充值失败，储 |
| `msg` | `string` | ❌ 否 | `充值成功` | 状态描述 |
| `amount` | `string` | ❌ 否 | `130` | 储值充值金额，单位：分 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200 成功 |
| `message` | `string` | ❌ 否 | `请求成功` | 网关返回码描述 |
| `request_id` | `string` | ❌ 否 | `已废弃` | 已废弃 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=109

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.recharge.get/3.0.0"
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
| 方法名称 | `rechargeQuery` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=109)_