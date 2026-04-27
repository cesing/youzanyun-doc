---
apiName: "youzan.cardvoucher.delivery.card.list.info.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "retail_valuecard"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "pageQueryUserDeliveryCards"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [retail]
deprecated: false
since: "2021-11-12"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3380"
---
# youzan.cardvoucher.delivery.card.list.info.1.0.0
> **所属分组**: retail_valuecard　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
分页查询店铺下用户的提货卡列表，返回结果中包含了可用和不可用的提货卡数据，如果提货卡不可用，结果中会告知不可用的原因，方便商家进行识别筛选。在使用提货卡核销功能时，需先通过该接口查询用户的提货卡信息。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.list.info/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "用户Id，用户手机号与用户Id二选一必填",
      "example": "7j3Gi1UH732330877366837248"
    },
    "mobile": {
      "type": "string",
      "description": "用户手机号，用户手机号与用户Id二选一必填",
      "example": "18573028713"
    },
    "card_no": {
      "type": "string",
      "description": "储值卡号",
      "example": "310200461055007"
    },
    "max_left_delivery_num": {
      "type": "integer",
      "description": "最大剩余可提货数量",
      "example": "3"
    },
    "min_left_delivery_num": {
      "type": "integer",
      "description": "最小剩余可提货数量",
      "example": "1"
    },
    "page_no": {
      "type": "integer",
      "description": "页号，不传默认为1，最大可传200",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "页码，不传默认为10，最大可传50",
      "example": "20"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `yz_open_id` | `integer` | ❌ 否 | `7j3Gi1UH732330877366837248` | 用户Id，用户手机号与用户Id二选一必填 |
| `mobile` | `string` | ❌ 否 | `18573028713` | 用户手机号，用户手机号与用户Id二选一必填 |
| `card_no` | `string` | ❌ 否 | `310200461055007` | 储值卡号 |
| `max_left_delivery_num` | `integer` | ❌ 否 | `3` | 最大剩余可提货数量 |
| `min_left_delivery_num` | `integer` | ❌ 否 | `1` | 最小剩余可提货数量 |
| `page_no` | `integer` | ❌ 否 | `1` | 页号，不传默认为1，最大可传200 |
| `page_size` | `integer` | ❌ 否 | `20` | 页码，不传默认为10，最大可传50 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "integer",
      "description": "返回数据"
    },
    "paginator": {
      "type": "integer",
      "description": "分页信息"
    },
    "page": {
      "type": "string",
      "description": "页号，默认为1，最大为200",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "页码，默认为10，最大为50",
      "example": "20"
    },
    "total_count": {
      "type": "string",
      "description": "数据总数",
      "example": "2"
    },
    "items": {
      "type": "array",
      "description": "提货卡列表信息"
    },
    "mobile": {
      "type": "string",
      "description": "手机号码",
      "example": "18573028713"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "310200461055007"
    },
    "original_price": {
      "type": "integer",
      "description": "卡面额（单位为分）",
      "example": "10000"
    },
    "card_name": {
      "type": "string",
      "description": "卡模板名称",
      "example": "提货卡"
    },
    "status": {
      "type": "string",
      "description": "卡状态（normal：正常；freeze：停用；cmpfrz：冻结；close：销卡；receding：退卡中；receded：已退卡）",
      "example": "normal"
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
  "total_count": "2",
  "items": [],
  "mobile": "18573028713",
  "card_no": "310200461055007"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `integer` | ❌ 否 | `` | 返回数据 |
| `paginator` | `integer` | ❌ 否 | `` | 分页信息 |
| `page` | `string` | ❌ 否 | `1` | 页号，默认为1，最大为200 |
| `page_size` | `string` | ❌ 否 | `20` | 页码，默认为10，最大为50 |
| `total_count` | `string` | ❌ 否 | `2` | 数据总数 |
| `items` | `array` | ❌ 否 | `` | 提货卡列表信息 |
| `mobile` | `string` | ❌ 否 | `18573028713` | 手机号码 |
| `card_no` | `string` | ❌ 否 | `310200461055007` | 卡号 |
| `original_price` | `integer` | ❌ 否 | `10000` | 卡面额（单位为分） |
| `card_name` | `string` | ❌ 否 | `提货卡` | 卡模板名称 |
| `status` | `string` | ❌ 否 | `normal` | 卡状态（normal：正常；freeze：停用；cmpfrz：冻结；close：销卡；receding：退卡中；rece |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3380

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.delivery.card.list.info/1.0.0"
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
| 方法名称 | `pageQueryUserDeliveryCards` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3380)_