---
apiName: "youzan.cardvoucher.giftcard.amount.query.3.0.0"
version: "3.0.0"
status: "已上线"
appName: "yz-cardvoucher-biz"
apiGroup: "gift_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.giftcard.GiftCardService"
method: "queryGiftCardAmout"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail]
deprecated: false
since: "2019-06-27"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=418"
---
# youzan.cardvoucher.giftcard.amount.query.3.0.0
> **所属分组**: gift_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线
---
## 1. 场景说明
根据店铺id查询该店铺下礼品卡的激活总数、激活金额总数、激活未使用的金额总数
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.amount.query/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": ""
    },
    "search_kdt_id": {
      "type": "integer",
      "description": "查询店铺id，非必传，为了以后兼容",
      "example": "491491"
    },
    "card_type": {
      "type": "string",
      "description": "卡类型（101：礼品卡）",
      "example": "101"
    }
  },
  "required": [
    "request",
    "card_type"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ✅ 是 | `` |  |
| `search_kdt_id` | `integer` | ❌ 否 | `491491` | 查询店铺id，非必传，为了以后兼容 |
| `card_type` | `string` | ✅ 是 | `101` | 卡类型（101：礼品卡） |
---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": ""
    },
    "card_active_total": {
      "type": "string",
      "description": "卡激活的数量",
      "example": "10"
    },
    "card_active_amout": {
      "type": "string",
      "description": "卡激活的金额",
      "example": "10"
    },
    "card_remainingmount": {
      "type": "string",
      "description": "卡剩余的金额",
      "example": "10"
    },
    "success": {
      "type": "string",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "successful"
    },
    "request_id": {
      "type": "string",
      "description": ""
    },
    "error_data": {
      "type": "string",
      "description": ""
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "card_active_total": "10",
  "card_active_amout": "10",
  "card_remainingmount": "10",
  "success": "true",
  "code": "200",
  "message": "successful",
  "request_id": ""
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `card_active_total` | `string` | ❌ 否 | `10` | 卡激活的数量 |
| `card_active_amout` | `string` | ❌ 否 | `10` | 卡激活的金额 |
| `card_remainingmount` | `string` | ❌ 否 | `10` | 卡剩余的金额 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200 :成功。 |
| `message` | `string` | ❌ 否 | `successful` | 网关返回码描述 |
| `request_id` | `string` | ❌ 否 | `` |  |
| `error_data` | `string` | ❌ 否 | `` |  |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=418

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "request": "<request>",
  "card_type": "101"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.amount.query/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "request": "<request>",
  "card_type": "101"
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
| 方法名称 | `queryGiftCardAmout` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=418)_