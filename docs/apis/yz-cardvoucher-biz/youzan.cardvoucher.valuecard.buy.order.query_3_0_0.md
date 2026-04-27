---
apiName: "youzan.cardvoucher.valuecard.buy.order.query.3.0.0"
version: "3.0.0"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "pageQueryBuyCardOrder"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail, retail_head_high]
deprecated: false
since: "2020-04-26"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=947"
---
# youzan.cardvoucher.valuecard.buy.order.query.3.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
查询该店铺下的用户购卡详情，如果传入卡模板号，则表示查询卡模板的用户购卡详情；否则查询所有的购卡详情。
出于系统稳定性考虑，需要注意如下两点：(1)查询时间间隔必传，并且时间间隔最大允许一年；(2)分页大小最大不能超过50，页号最大不能超过200
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.buy.order.query/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "template_no": {
      "type": "string",
      "description": "卡模板号(非必传)",
      "example": "110201377141123"
    },
    "order_time_before": {
      "type": "string",
      "description": "下单的时间范围(必传,最长时间间隔不能超过一年),发生在orderTimeBefore之后,时间格式是\"yyyy-MM-ddhh:mm:ss\"",
      "example": "2019-05-01 00:00:00"
    },
    "order_time_after": {
      "type": "string",
      "description": "下单的时间范围(比传,最长时间间隔不能超过一年),发生在orderTimeAfter之前,时间格式是\"yyyy-MM-ddhh:mm:ss\"",
      "example": "2020-04-20 00:00:00"
    },
    "page_no": {
      "type": "integer",
      "description": "页码,默认为1,不能大于200",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "分页大小,默认为10,不能大于50",
      "example": "10"
    }
  },
  "required": [
    "order_time_before",
    "order_time_after"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `template_no` | `string` | ❌ 否 | `110201377141123` | 卡模板号(非必传) |
| `order_time_before` | `string` | ✅ 是 | `2019-05-01 00:00:00` | 下单的时间范围(必传,最长时间间隔不能超过一年),发生在orderTimeBefore之后,时间格式是"yyyy-MM- |
| `order_time_after` | `string` | ✅ 是 | `2020-04-20 00:00:00` | 下单的时间范围(比传,最长时间间隔不能超过一年),发生在orderTimeAfter之前,时间格式是"yyyy-MM-d |
| `page_no` | `integer` | ❌ 否 | `1` | 页码,默认为1,不能大于200 |
| `page_size` | `integer` | ❌ 否 | `10` | 分页大小,默认为10,不能大于50 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "integer",
      "description": "data"
    },
    "paginator": {
      "type": "integer",
      "description": "分页结构体"
    },
    "page": {
      "type": "string",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "分页大小",
      "example": "20"
    },
    "total_count": {
      "type": "string",
      "description": "总数量",
      "example": "40"
    },
    "items": {
      "type": "array",
      "description": ""
    },
    "kdt_id": {
      "type": "integer",
      "description": "总部店铺ID",
      "example": "43205202"
    },
    "source_kdt_id": {
      "type": "integer",
      "description": "受理机构店铺ID",
      "example": "43205202"
    },
    "template_no": {
      "type": "string",
      "description": "卡模板号",
      "example": "110201377141123"
    },
    "template_name": {
      "type": "string",
      "description": "卡模板名称",
      "example": "测试卡312312"
    },
    "order_no": {
      "type": "string",
      "description": "订单号",
      "example": "E20200418113348017100001"
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
  "total_count": "40",
  "items": [],
  "kdt_id": "43205202",
  "source_kdt_id": "43205202"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `integer` | ❌ 否 | `` | data |
| `paginator` | `integer` | ❌ 否 | `` | 分页结构体 |
| `page` | `string` | ❌ 否 | `1` | 页码 |
| `page_size` | `string` | ❌ 否 | `20` | 分页大小 |
| `total_count` | `string` | ❌ 否 | `40` | 总数量 |
| `items` | `array` | ❌ 否 | `` |  |
| `kdt_id` | `integer` | ❌ 否 | `43205202` | 总部店铺ID |
| `source_kdt_id` | `integer` | ❌ 否 | `43205202` | 受理机构店铺ID |
| `template_no` | `string` | ❌ 否 | `110201377141123` | 卡模板号 |
| `template_name` | `string` | ❌ 否 | `测试卡312312` | 卡模板名称 |
| `order_no` | `string` | ❌ 否 | `E20200418113348017100001` | 订单号 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=947

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "order_time_before": "2019-05-01 00:00:00",
  "order_time_after": "2020-04-20 00:00:00"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.buy.order.query/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "order_time_before": "2019-05-01 00:00:00",
  "order_time_after": "2020-04-20 00:00:00"
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
| 方法名称 | `pageQueryBuyCardOrder` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=947)_