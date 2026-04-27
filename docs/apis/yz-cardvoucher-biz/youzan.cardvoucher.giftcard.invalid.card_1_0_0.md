---
apiName: "youzan.cardvoucher.giftcard.invalid.card.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.open.GiftCardOpenService"
method: "invalidCard"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, retail_d_partner, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offline, retail_offline_channel, retail_partner, edu, edu_head, edu_branch]
deprecated: false
since: "2023-04-07"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4030"
---
# youzan.cardvoucher.giftcard.invalid.card.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
失效礼品卡的电子卡，仅激活之前的卡可进行失效
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.invalid.card/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "operator_open_id": {
      "type": "integer",
      "description": "操作人",
      "example": "xvJrRKC0702883114891939840"
    },
    "card_no": {
      "type": "string",
      "description": "电子卡号",
      "example": "310200549496389"
    }
  },
  "required": [
    "operator_open_id",
    "card_no"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `operator_open_id` | `integer` | ✅ 是 | `xvJrRKC0702883114891939840` | 操作人 |
| `card_no` | `string` | ✅ 是 | `310200549496389` | 电子卡号 |
---
## 3. 响应
**响应参数 Schema**（7 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": ""
    },
    "invalid_result": {
      "type": "boolean",
      "description": "失效结果，true 成功，false失败",
      "example": "true"
    },
    "success": {
      "type": "string",
      "description": "是否请求成功",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": ""
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
  "invalid_result": "true",
  "success": "true",
  "code": "200",
  "message": "",
  "request_id": "",
  "error_data": ""
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `invalid_result` | `boolean` | ❌ 否 | `true` | 失效结果，true 成功，false失败 |
| `success` | `string` | ❌ 否 | `true` | 是否请求成功 |
| `code` | `string` | ❌ 否 | `200` |  |
| `message` | `string` | ❌ 否 | `` |  |
| `request_id` | `string` | ❌ 否 | `` |  |
| `error_data` | `string` | ❌ 否 | `` |  |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4030

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "operator_open_id": "xvJrRKC0702883114891939840",
  "card_no": "310200549496389"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.invalid.card/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "operator_open_id": "xvJrRKC0702883114891939840",
  "card_no": "310200549496389"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.open.GiftCardOpenService` |
| 方法名称 | `invalidCard` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4030)_