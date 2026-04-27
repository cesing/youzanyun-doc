---
apiName: "youzan.appstore.open.subscribe.query.1.0.2"
version: "1.0.2"
status: "已上线/变更中"
appName: "appstore"
apiGroup: "open_market"
serviceName: "com.youzan.cloud.appstore.api.service.open.AppstoreSubscribeQuery"
method: "getSubscribeMessageAllowEmpty"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2021-07-08"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3019"
---
# youzan.appstore.open.subscribe.query.1.0.2
> **所属分组**: open_market　**所属应用**: appstore　**状态**: 已上线/变更中
---
## 1. 场景说明
查询应用订购和授权记录，当查询订单不存在时返回为空。该接口仅限工具型应用使用，开发者可以使用应用下任意一个有效期内access_token查询该接口，注意：不支持云测试店铺对应的access_token查询
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.2`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（6 个参数）:
```json
{
  "type": "object",
  "properties": {
    "tid": {
      "type": "string",
      "description": "有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E201912341234"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "314123141"
    },
    "start_time": {
      "type": "string",
      "description": "开始时间，开始时间和结束时间查询间隔不内超过1个月，时间格式：yyyy-MM-dd-HH-mm-ss",
      "example": "2019-10-21 12:15:35"
    },
    "end_time": {
      "type": "string",
      "description": "结束时间，开始时间和结束时间查询间隔不内超过1个月，时间格式：yyyy-MM-dd-HH-mm-ss",
      "example": "2019-10-21 12:15:35"
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
| `tid` | `string` | ❌ 否 | `E201912341234` | 有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `kdt_id` | `integer` | ❌ 否 | `314123141` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `start_time` | `string` | ✅ 是 | `2019-10-21 12:15:35` | 开始时间，开始时间和结束时间查询间隔不内超过1个月，时间格式：yyyy-MM-dd-HH-mm-ss |
| `end_time` | `string` | ✅ 是 | `2019-10-21 12:15:35` | 结束时间，开始时间和结束时间查询间隔不内超过1个月，时间格式：yyyy-MM-dd-HH-mm-ss |
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
      "description": "响应参数"
    },
    "details": {
      "type": "array",
      "description": "订购详细信息"
    },
    "order_type": {
      "type": "integer",
      "description": "订单类型； 1-应用市场订单； 2-应用内购订单； 4-服务订单（服务市场）； 5-模板市场订单； 6-服务代运营周期订单（服务市场）；",
      "example": "1"
    },
    "app_subscribe_notify_message": {
      "type": "object",
      "description": "应用订购消息"
    },
    "tid": {
      "type": "string",
      "description": "有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "20190312105415047400001"
    },
    "sku_version_text": {
      "type": "string",
      "description": "订购版本名称",
      "example": "普通版"
    },
    "sku_interval_text": {
      "type": "string",
      "description": "订购时长，单位：天",
      "example": "365"
    },
    "buyer_phone": {
      "type": "string",
      "description": "买家电话",
      "example": "15800000000"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "买家id，买家在有赞的唯一id。推荐使用",
      "example": "LnhGm4rh576452722916618240"
    },
    "pay_time": {
      "type": "integer",
      "description": "支付时间，Unix时间戳，单位：毫秒",
      "example": "1581231240000"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
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
  "tid": "20190312105415047400001",
  "sku_version_text": "普通版",
  "sku_interval_text": "365",
  "buyer_phone": "15800000000"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 响应参数 |
| `details` | `array` | ❌ 否 | `` | 订购详细信息 |
| `order_type` | `integer` | ❌ 否 | `1` | 订单类型； 1-应用市场订单； 2-应用内购订单； 4-服务订单（服务市场）； 5-模板市场订单； 6-服务代运营周期订 |
| `app_subscribe_notify_message` | `object` | ❌ 否 | `` | 应用订购消息 |
| `tid` | `string` | ❌ 否 | `20190312105415047400001` | 有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `sku_version_text` | `string` | ❌ 否 | `普通版` | 订购版本名称 |
| `sku_interval_text` | `string` | ❌ 否 | `365` | 订购时长，单位：天 |
| `buyer_phone` | `string` | ❌ 否 | `15800000000` | 买家电话 |
| `yz_open_id` | `integer` | ❌ 否 | `LnhGm4rh576452722916618240` | 买家id，买家在有赞的唯一id。推荐使用 |
| `pay_time` | `integer` | ❌ 否 | `1581231240000` | 支付时间，Unix时间戳，单位：毫秒 |
| `kdt_id` | `integer` | ❌ 否 | `123123` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3019

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.2' \
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

url = "https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.2"
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
| 方法名称 | `getSubscribeMessageAllowEmpty` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3019)_