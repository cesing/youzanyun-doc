---
apiName: "youzan.appstore.open.data.page.track.get.1.0.0"
version: "1.0.0"
status: "待上线"
appName: "data-sync"
apiGroup: "open_market"
serviceName: "com.youzan.cloud.data.sync.api.service.DataAnalysisService"
method: "getPageData"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc]
deprecated: false
since: "2019-07-29"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=573"
---
# youzan.appstore.open.data.page.track.get.1.0.0
> **所属分组**: open_market　**所属应用**: data-sync　**状态**: 待上线
---
## 1. 场景说明
查询微页面导流数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.data.page.track.get/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "query_request": {
      "type": "object",
      "description": ""
    },
    "page_id": {
      "type": "string",
      "description": "页面id",
      "example": "229101"
    },
    "query_date": {
      "type": "string",
      "description": "查询日期，例：20190729",
      "example": "20190725"
    }
  },
  "required": [
    "query_request",
    "page_id",
    "query_date"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `query_request` | `object` | ✅ 是 | `` |  |
| `page_id` | `string` | ✅ 是 | `229101` | 页面id |
| `query_date` | `string` | ✅ 是 | `20190725` | 查询日期，例：20190729 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": ""
    },
    "page_id": {
      "type": "string",
      "description": "页面id",
      "example": "229101"
    },
    "statistic_date": {
      "type": "string",
      "description": "统计日期",
      "example": "20190725"
    },
    "add_cart_uv": {
      "type": "integer",
      "description": "从页面添加购物车人数",
      "example": "1"
    },
    "order_uv": {
      "type": "integer",
      "description": "从页面下单人数",
      "example": "2"
    },
    "item_uv": {
      "type": "integer",
      "description": "从页面访问商详人数",
      "example": "3"
    },
    "item_pv": {
      "type": "integer",
      "description": "从页面访问商祥次数",
      "example": "4"
    },
    "coupon_uv": {
      "type": "integer",
      "description": "从页面访问优惠券人数",
      "example": "5"
    },
    "coupon_pv": {
      "type": "integer",
      "description": "从页面访问优惠券次数",
      "example": "6"
    },
    "coupon_take_uv": {
      "type": "integer",
      "description": "从页面领取优惠券人数",
      "example": "7"
    },
    "success": {
      "type": "string",
      "description": "调用结果",
      "example": "true"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "page_id": "229101",
  "statistic_date": "20190725",
  "add_cart_uv": "1",
  "order_uv": "2",
  "item_uv": "3",
  "item_pv": "4",
  "coupon_uv": "5"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `page_id` | `string` | ❌ 否 | `229101` | 页面id |
| `statistic_date` | `string` | ❌ 否 | `20190725` | 统计日期 |
| `add_cart_uv` | `integer` | ❌ 否 | `1` | 从页面添加购物车人数 |
| `order_uv` | `integer` | ❌ 否 | `2` | 从页面下单人数 |
| `item_uv` | `integer` | ❌ 否 | `3` | 从页面访问商详人数 |
| `item_pv` | `integer` | ❌ 否 | `4` | 从页面访问商祥次数 |
| `coupon_uv` | `integer` | ❌ 否 | `5` | 从页面访问优惠券人数 |
| `coupon_pv` | `integer` | ❌ 否 | `6` | 从页面访问优惠券次数 |
| `coupon_take_uv` | `integer` | ❌ 否 | `7` | 从页面领取优惠券人数 |
| `success` | `string` | ❌ 否 | `true` | 调用结果 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=573

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "query_request": "<query_request>",
  "page_id": "229101",
  "query_date": "20190725"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.data.page.track.get/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "query_request": "<query_request>",
  "page_id": "229101",
  "query_date": "20190725"
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
| 服务名称 | `com.youzan.cloud.data.sync.api.service.DataAnalysisService` |
| 方法名称 | `getPageData` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=573)_