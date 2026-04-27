---
apiName: "youzan.appstore.open.subscribe.query.1.0.0"
version: "1.0.0"
status: "待上线"
appName: "appstore"
apiGroup: "open_market"
serviceName: "com.youzan.cloud.appstore.api.service.open.AppstoreSubscribeQuery"
method: "getSubscribeMessage"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc]
deprecated: false
since: "2019-05-27"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=322"
---
# youzan.appstore.open.subscribe.query.1.0.0
> **所属分组**: open_market　**所属应用**: appstore　**状态**: 待上线
---
## 1. 场景说明
查询应用订购和授权记录
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "order_no": {
      "type": "string",
      "description": "订单编号",
      "example": "E2109113123141231231"
    },
    "start_time": {
      "type": "string",
      "description": "开始时间（年-月-日 时:分:秒）时间间隔不超过1个月",
      "example": "2019-05-02 12:00:00"
    },
    "end_time": {
      "type": "string",
      "description": "结束时间（年-月-日 时:分:秒）时间间隔不超过1个月",
      "example": "2019-05-22 12:00:00"
    },
    "page_no": {
      "type": "integer",
      "description": "查询时当前的页数（分页查询接口必填）",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页展示的行数（分页查询接口必填）建议30，最大支持100",
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
| `order_no` | `string` | ❌ 否 | `E2109113123141231231` | 订单编号 |
| `start_time` | `string` | ✅ 是 | `2019-05-02 12:00:00` | 开始时间（年-月-日 时:分:秒）时间间隔不超过1个月 |
| `end_time` | `string` | ✅ 是 | `2019-05-22 12:00:00` | 结束时间（年-月-日 时:分:秒）时间间隔不超过1个月 |
| `page_no` | `integer` | ✅ 是 | `1` | 查询时当前的页数（分页查询接口必填） |
| `page_size` | `integer` | ✅ 是 | `10` | 每页展示的行数（分页查询接口必填）建议30，最大支持100 |
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
    "details": {
      "type": "array",
      "description": ""
    },
    "order_type": {
      "type": "integer",
      "description": "订单类型@seecom.youzan.cloud.appstore.api.constant.SubscribeTypeEnum"
    },
    "app_subscribe_notify_message": {
      "type": "object",
      "description": "应用订购消息"
    },
    "order_no": {
      "type": "string",
      "description": "订单编号",
      "example": "E20190509181910080300061"
    },
    "sku_version_text": {
      "type": "string",
      "description": "订购版本名称",
      "example": "试用版"
    },
    "sku_interval_text": {
      "type": "string",
      "description": "订购时长，单位：天",
      "example": "365"
    },
    "buyer_phone": {
      "type": "string",
      "description": "订购人手机号",
      "example": "135xxxx1234"
    },
    "buyer_id": {
      "type": "integer",
      "description": "订购人id",
      "example": "865115939"
    },
    "pay_time": {
      "type": "integer",
      "description": "支付时间， Unix时间戳，单位：毫秒",
      "example": "1558949704000"
    },
    "kdt_id": {
      "type": "integer",
      "description": "订购店铺id",
      "example": "18163424"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "details": [],
  "order_type": 0,
  "app_subscribe_notify_message": "",
  "order_no": "E20190509181910080300061",
  "sku_version_text": "试用版",
  "sku_interval_text": "365",
  "buyer_phone": "135xxxx1234"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `details` | `array` | ❌ 否 | `` |  |
| `order_type` | `integer` | ❌ 否 | `` | 订单类型@seecom.youzan.cloud.appstore.api.constant.SubscribeType |
| `app_subscribe_notify_message` | `object` | ❌ 否 | `` | 应用订购消息 |
| `order_no` | `string` | ❌ 否 | `E20190509181910080300061` | 订单编号 |
| `sku_version_text` | `string` | ❌ 否 | `试用版` | 订购版本名称 |
| `sku_interval_text` | `string` | ❌ 否 | `365` | 订购时长，单位：天 |
| `buyer_phone` | `string` | ❌ 否 | `135xxxx1234` | 订购人手机号 |
| `buyer_id` | `integer` | ❌ 否 | `865115939` | 订购人id |
| `pay_time` | `integer` | ❌ 否 | `1558949704000` | 支付时间， Unix时间戳，单位：毫秒 |
| `kdt_id` | `integer` | ❌ 否 | `18163424` | 订购店铺id |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=322

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "start_time": "2019-05-02 12:00:00",
  "end_time": "2019-05-22 12:00:00",
  "page_no": "1",
  "page_size": "10"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "start_time": "2019-05-02 12:00:00",
  "end_time": "2019-05-22 12:00:00",
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
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=322)_