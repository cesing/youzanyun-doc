---
apiName: "youzan.cardvoucher.openCardService.verify.checkCustomerPayCards.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.open.OpenCardService"
method: "checkCustomerPayCards"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, retail, retail_online]
deprecated: false
since: "2025-05-16"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4803"
---
# youzan.cardvoucher.openCardService.verify.checkCustomerPayCards.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
创建订单前，校验卡列表是否可用
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.openCardService.verify.checkCustomerPayCards/1.0.0`
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
      "example": "SoQvb61L732695759723438080"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。当前请求的店铺id,连锁店铺为分店店铺di",
      "example": "92732278"
    },
    "items": {
      "type": "array",
      "description": "商品上下文"
    },
    "item_id": {
      "type": "string",
      "description": "商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.items.inventory.get （查询仓库中商品）获取",
      "example": "399515043"
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
    "card_no_list": {
      "type": "string",
      "description": "卡号列表",
      "example": "[\"310200463069568\"]"
    },
    "card_type": {
      "type": "integer",
      "description": "卡类型",
      "example": "102"
    },
    "sales_channel_id": {
      "type": "integer",
      "description": "销售渠道Id",
      "example": "0"
    },
    "app_name": {
      "type": "string",
      "description": "应用名称",
      "example": "app_name"
    }
  },
  "required": [
    "yz_open_id",
    "kdt_id"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `yz_open_id` | `integer` | ✅ 是 | `SoQvb61L732695759723438080` | 客户号 |
| `kdt_id` | `integer` | ✅ 是 | `92732278` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。当前请求的店铺id,连锁店铺为分店店铺d |
| `items` | `array` | ❌ 否 | `` | 商品上下文 |
| `item_id` | `string` | ❌ 否 | `399515043` | 商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查 |
| `outside` | `boolean` | ❌ 否 | `false` | 是否为外部商品，非有赞IC商品设置为true,默认为IC商品 |
| `is_present` | `boolean` | ❌ 否 | `false` | 是否是赠品 |
| `card_no_list` | `string` | ❌ 否 | `["310200463069568"]` | 卡号列表 |
| `card_type` | `integer` | ❌ 否 | `102` | 卡类型 |
| `sales_channel_id` | `integer` | ❌ 否 | `0` | 销售渠道Id |
| `app_name` | `string` | ❌ 否 | `app_name` | 应用名称 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "返回数据"
    },
    "card_name": {
      "type": "string",
      "description": "卡名称",
      "example": "礼品卡"
    },
    "summary_card_no": {
      "type": "string",
      "description": "汇总卡号",
      "example": "310200463069568"
    },
    "balance": {
      "type": "integer",
      "description": "余额（分）",
      "example": "89720"
    },
    "yz_open_id": {
      "type": "string",
      "description": "有赞用户id",
      "example": "SoQvb61L732695759723438080"
    },
    "card_status": {
      "type": "string",
      "description": "卡状态。\"normal\"（正常状态）,\"freeze\"（C端冻结状态）,\"cmpfrz\"（完全冻结状态），\"close\"（注销），\"receding\"（退卡中），\"receded\"（已退卡）",
      "example": "normal"
    },
    "card_type": {
      "type": "string",
      "description": "卡类型102储值卡。目前都是102的卡了",
      "example": "102"
    },
    "freezing_sum_dnom": {
      "type": "string",
      "description": "被冻结的金额",
      "example": "0"
    },
    "is_exclusion": {
      "type": "boolean",
      "description": "是否互斥卡(无优惠卡)",
      "example": "false"
    },
    "success": {
      "type": "string",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "网关返回码，表示本次请求是否成功。200 成功",
      "example": "200"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "card_name": "礼品卡",
  "summary_card_no": "310200463069568",
  "balance": "89720",
  "yz_open_id": "SoQvb61L732695759723438080",
  "card_status": "normal",
  "card_type": "102",
  "freezing_sum_dnom": "0"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` | 返回数据 |
| `card_name` | `string` | ❌ 否 | `礼品卡` | 卡名称 |
| `summary_card_no` | `string` | ❌ 否 | `310200463069568` | 汇总卡号 |
| `balance` | `integer` | ❌ 否 | `89720` | 余额（分） |
| `yz_open_id` | `string` | ❌ 否 | `SoQvb61L732695759723438080` | 有赞用户id |
| `card_status` | `string` | ❌ 否 | `normal` | 卡状态。"normal"（正常状态）,"freeze"（C端冻结状态）,"cmpfrz"（完全冻结状态），"close" |
| `card_type` | `string` | ❌ 否 | `102` | 卡类型102储值卡。目前都是102的卡了 |
| `freezing_sum_dnom` | `string` | ❌ 否 | `0` | 被冻结的金额 |
| `is_exclusion` | `boolean` | ❌ 否 | `false` | 是否互斥卡(无优惠卡) |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200 成功 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4803

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "yz_open_id": "SoQvb61L732695759723438080",
  "kdt_id": "92732278"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.openCardService.verify.checkCustomerPayCards/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "yz_open_id": "SoQvb61L732695759723438080",
  "kdt_id": "92732278"
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
| 方法名称 | `checkCustomerPayCards` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4803)_