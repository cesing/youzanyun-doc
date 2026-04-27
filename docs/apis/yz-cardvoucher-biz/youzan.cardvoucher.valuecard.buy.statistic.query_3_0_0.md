---
apiName: "youzan.cardvoucher.valuecard.buy.statistic.query.3.0.0"
version: "3.0.0"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "queryBuyCardSalesInfo"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail]
deprecated: false
since: "2020-04-26"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=946"
---
# youzan.cardvoucher.valuecard.buy.statistic.query.3.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
查询该店铺下某个卡模板的售卡销量统计数据，返回的数据中包含每个卡封面卡面额对应的售卡汇总数据。
出于系统的稳定性考虑，需要注意如下两点：(1)卡模板号必传；（2）查询时间范围必传，并且时间间隔最长为一年
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.buy.statistic.query/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "template_no": {
      "type": "string",
      "description": "卡模板号(必传)",
      "example": "110201377141123"
    },
    "order_time_before": {
      "type": "string",
      "description": "下单的时间范围(必传,最长时间间隔为一年),发生在orderTimeBefore之后,时间格式是\"yyyy-MM-ddhh:mm:ss\"",
      "example": "2019-05-12 13:00:00"
    },
    "order_time_after": {
      "type": "string",
      "description": "下单的时间范围(必传,最长时间间隔为一年),发生在orderTimeAfter之前,时间格式是\"yyyy-MM-ddhh:mm:ss\"",
      "example": "2020-04-12 13:00:00"
    }
  },
  "required": [
    "template_no",
    "order_time_before",
    "order_time_after"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `template_no` | `string` | ✅ 是 | `110201377141123` | 卡模板号(必传) |
| `order_time_before` | `string` | ✅ 是 | `2019-05-12 13:00:00` | 下单的时间范围(必传,最长时间间隔为一年),发生在orderTimeBefore之后,时间格式是"yyyy-MM-ddh |
| `order_time_after` | `string` | ✅ 是 | `2020-04-12 13:00:00` | 下单的时间范围(必传,最长时间间隔为一年),发生在orderTimeAfter之前,时间格式是"yyyy-MM-ddhh |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": ""
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
    "sales_total_num": {
      "type": "integer",
      "description": "销售总数量",
      "example": "2"
    },
    "sales_total_amount": {
      "type": "integer",
      "description": "销售总金额(单位为分)",
      "example": "2"
    },
    "template_sales_info": {
      "type": "array",
      "description": "卡模板销售明细"
    },
    "goods_id": {
      "type": "integer",
      "description": "商品系统ID/SPU(对应一个卡封面)",
      "example": "600947884"
    },
    "sku_id": {
      "type": "integer",
      "description": "商品系统/SKUID(具体规格,对应一个卡封面下的一个卡面额)",
      "example": "36603352"
    },
    "origin_price": {
      "type": "integer",
      "description": "卡面额(单位为分)",
      "example": "100"
    },
    "sales_price": {
      "type": "integer",
      "description": "实际销售面额(单位为分)",
      "example": "1"
    },
    "sales_num": {
      "type": "integer",
      "description": "售卡总数量",
      "example": "2"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "template_no": "110201377141123",
  "template_name": "测试卡312312",
  "sales_total_num": "2",
  "sales_total_amount": "2",
  "template_sales_info": [],
  "goods_id": "600947884",
  "sku_id": "36603352"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` |  |
| `template_no` | `string` | ❌ 否 | `110201377141123` | 卡模板号 |
| `template_name` | `string` | ❌ 否 | `测试卡312312` | 卡模板名称 |
| `sales_total_num` | `integer` | ❌ 否 | `2` | 销售总数量 |
| `sales_total_amount` | `integer` | ❌ 否 | `2` | 销售总金额(单位为分) |
| `template_sales_info` | `array` | ❌ 否 | `` | 卡模板销售明细 |
| `goods_id` | `integer` | ❌ 否 | `600947884` | 商品系统ID/SPU(对应一个卡封面) |
| `sku_id` | `integer` | ❌ 否 | `36603352` | 商品系统/SKUID(具体规格,对应一个卡封面下的一个卡面额) |
| `origin_price` | `integer` | ❌ 否 | `100` | 卡面额(单位为分) |
| `sales_price` | `integer` | ❌ 否 | `1` | 实际销售面额(单位为分) |
| `sales_num` | `integer` | ❌ 否 | `2` | 售卡总数量 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=946

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "template_no": "110201377141123",
  "order_time_before": "2019-05-12 13:00:00",
  "order_time_after": "2020-04-12 13:00:00"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.buy.statistic.query/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "template_no": "110201377141123",
  "order_time_before": "2019-05-12 13:00:00",
  "order_time_after": "2020-04-12 13:00:00"
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
| 方法名称 | `queryBuyCardSalesInfo` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=946)_