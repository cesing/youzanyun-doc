---
apiName: "youzan.appstore.open.subscribe.query.1.0.1"
version: "1.0.1"
status: "待上线"
appName: "appstore"
apiGroup: "open_market"
serviceName: "com.youzan.cloud.appstore.api.service.open.AppstoreSubscribeQuery"
method: "getSubscribeMessage"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2019-05-27"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=526"
---
# youzan.appstore.open.subscribe.query.1.0.1
> **所属分组**: open_market　**所属应用**: appstore　**状态**: 待上线
---
## 1. 场景说明
查询应用订购和授权记录
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（6 个参数）:
```json
{
  "type": "object",
  "properties": {
    "order_no": {
      "type": "string",
      "description": "订单编号",
      "example": "E201912341234"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺ID",
      "example": "314123141"
    },
    "start_time": {
      "type": "string",
      "description": "订单支付开始时间",
      "example": "2019-10-21 12:15:35"
    },
    "end_time": {
      "type": "string",
      "description": "订单支付结束时间",
      "example": "2019-10-21 12:15:35"
    },
    "page_no": {
      "type": "integer",
      "description": "查询时当前的页数（分页查询接口必填）",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页展示的行数（分页查询接口必填）",
      "example": "10"
    }
  },
  "required": [
    "start_time",
    "end_time",
    "page_no",
    "page_size"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `order_no` | `string` | ❌ 否 | `E201912341234` | 订单编号 |
| `kdt_id` | `integer` | ❌ 否 | `314123141` | 店铺ID |
| `start_time` | `string` | ✅ 是 | `2019-10-21 12:15:35` | 订单支付开始时间 |
| `end_time` | `string` | ✅ 是 | `2019-10-21 12:15:35` | 订单支付结束时间 |
| `page_no` | `integer` | ✅ 是 | `1` | 查询时当前的页数（分页查询接口必填） |
| `page_size` | `integer` | ✅ 是 | `10` | 每页展示的行数（分页查询接口必填） |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "响应集合"
    },
    "details": {
      "type": "array",
      "description": "详细信息"
    },
    "order_type": {
      "type": "integer",
      "description": "订单类型；1: 应用订单 2: 内购订单 5：模板订单",
      "example": "1"
    },
    "app_subscribe_notify_message": {
      "type": "object",
      "description": "应用订购消息"
    },
    "order_no": {
      "type": "string",
      "description": "订单号",
      "example": "E20191234123"
    },
    "sku_version_text": {
      "type": "string",
      "description": "订购版本名称",
      "example": "普通版"
    },
    "sku_interval_text": {
      "type": "string",
      "description": "订购时长(天)",
      "example": "365"
    },
    "buyer_phone": {
      "type": "string",
      "description": "买家电话",
      "example": "15800000000"
    },
    "buyer_id": {
      "type": "integer",
      "description": "买家id",
      "example": "12351235"
    },
    "pay_time": {
      "type": "integer",
      "description": "支付时间",
      "example": "1581231240000"
    },
    "kdt_id": {
      "type": "integer",
      "description": "绑定店铺id",
      "example": "123123"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "details": [],
  "order_type": "1",
  "app_subscribe_notify_message": "",
  "order_no": "E20191234123",
  "sku_version_text": "普通版",
  "sku_interval_text": "365",
  "buyer_phone": "15800000000"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 响应集合 |
| `details` | `array` | ❌ 否 | `` | 详细信息 |
| `order_type` | `integer` | ❌ 否 | `1` | 订单类型；1: 应用订单 2: 内购订单 5：模板订单 |
| `app_subscribe_notify_message` | `object` | ❌ 否 | `` | 应用订购消息 |
| `order_no` | `string` | ❌ 否 | `E20191234123` | 订单号 |
| `sku_version_text` | `string` | ❌ 否 | `普通版` | 订购版本名称 |
| `sku_interval_text` | `string` | ❌ 否 | `365` | 订购时长(天) |
| `buyer_phone` | `string` | ❌ 否 | `15800000000` | 买家电话 |
| `buyer_id` | `integer` | ❌ 否 | `12351235` | 买家id |
| `pay_time` | `integer` | ❌ 否 | `1581231240000` | 支付时间 |
| `kdt_id` | `integer` | ❌ 否 | `123123` | 绑定店铺id |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=526

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "start_time": "2019-10-21 12:15:35",
  "end_time": "2019-10-21 12:15:35",
  "page_no": "1",
  "page_size": "10"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.1"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "start_time": "2019-10-21 12:15:35",
  "end_time": "2019-10-21 12:15:35",
  "page_no": "1",
  "page_size": "10"
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
| 服务名称 | `com.youzan.cloud.appstore.api.service.open.AppstoreSubscribeQuery` |
| 方法名称 | `getSubscribeMessage` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=526)_