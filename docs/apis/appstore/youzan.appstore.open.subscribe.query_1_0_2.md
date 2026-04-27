---
apiName: "youzan.appstore.open.subscribe.query.1.0.2"
version: "1.0.2"
appName: "appstore"
apiGroup: "open_market"
method: "getSubscribeMessageAllowEmpty"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-07-08"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3019"
---
# youzan.appstore.open.subscribe.query.1.0.2
> **所属分组**: open_market　**所属应用**: appstore
---
## 1. 场景说明
查询应用订购和授权记录，当查询订单不存在时返回为空。该接口仅限工具型应用使用，开发者可以使用应用下任意一个有效期内access_token查询该接口，注意：不支持云测试店铺对应的access_token查询
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.2`
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
**请求参数明细**（6 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `tid` | `string` | ❌ | `E201912341234` | 有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `kdt_id` | `integer` | ❌ | `314123141` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `start_time` | `string` | ✅ | `2019-10-21 12:15:35` | 开始时间，开始时间和结束时间查询间隔不内超过1个月，时间格式：yyyy-MM-dd-HH-mm-ss |
| `end_time` | `string` | ✅ | `2019-10-21 12:15:35` | 结束时间，开始时间和结束时间查询间隔不内超过1个月，时间格式：yyyy-MM-dd-HH-mm-ss |
| `page_no` | `integer` | ✅ | `1` | 查询时当前的页数（分页查询接口必填） |
| `page_size` | `integer` | ✅ | `10` | 每页展示的行数（分页查询接口必填）建议30，最大支持100 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
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
      "type": "string",
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
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 响应参数 |
| `details` | `array` | ❌ | `` | 订购详细信息 |
| `order_type` | `integer` | ❌ | `1` | 订单类型； 1-应用市场订单； 2-应用内购订单； 4-服务订单（服务市场）； 5-模板市场订单； 6-服务代运营周期订单（服务市场）； |
| `app_subscribe_notify_message` | `string` | ❌ | `` | 应用订购消息 |
| `tid` | `string` | ❌ | `20190312105415047400001` | 有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `sku_version_text` | `string` | ❌ | `普通版` | 订购版本名称 |
| `sku_interval_text` | `string` | ❌ | `365` | 订购时长，单位：天 |
| `buyer_phone` | `string` | ❌ | `15800000000` | 买家电话 |
| `yz_open_id` | `integer` | ❌ | `LnhGm4rh576452722916618240` | 买家id，买家在有赞的唯一id。推荐使用 |
| `pay_time` | `integer` | ❌ | `1581231240000` | 支付时间，Unix时间戳，单位：毫秒 |
| `kdt_id` | `integer` | ❌ | `123123` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "tid": "E201912341234",\n  "kdt_id": "314123141",\n  "start_time": "2019-10-21 12:15:35",\n  "end_time": "2019-10-21 12:15:35",\n  "page_no": "1",\n  "page_size": "10"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.2"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "tid": "E201912341234",
    "kdt_id": "314123141",
    "start_time": "2019-10-21 12:15:35",
    "end_time": "2019-10-21 12:15:35",
    "page_no": "1",
    "page_size": "10"
}

resp = requests.post(url, json=payload, headers=headers)
print(resp.json())
```
---
## 5. 错误码
| 错误码 | 类型 | 说明 |
|--------|------|------|
| 10001 | `SYSTEM_ERROR` | 系统内部错误 |
| 10002 | `INVALID_PARAMETER` | 参数错误 |
| 10003 | `UNAUTHORIZED` | 未授权或授权已过期 |
| 10004 | `PERMISSION_DENIED` | 无权限调用此接口 |
| 10005 | `RESOURCE_NOT_FOUND` | 请求的资源不存在 |
| 20001 | `RATE_LIMIT_EXCEEDED` | 调用频率超限 |
| 20002 | `QUOTA_EXCEEDED` | 接口配额已用完 |
---
## 6. 权限与计费

**接口计费状态：未知（请以官网实际披露为准）。**

**拥有此API的能力包：** 暂无数据（请以官网实际披露为准）。

---
## 7. 权限说明

**应用类目 → 权限类型：**

| 应用类目 | 权限类型 |
|----------|----------|
| 有赞微商城、有赞零售、有赞教育、有赞美业 | 普通自研商家（基础权益） |
| 大客户定制接口、美业大客户定制、零售大客户定制、收款二维码-大客专用 | 大客定制接口（需购买大客套餐） |
| 客户关系CRM、门店POS | iPaaS 套餐权益（需购买 iPaaS 套餐） |

> 权限数据来源：[有赞云能力包说明](https://doc.youzanyun.com/detail/content/API/0/120)