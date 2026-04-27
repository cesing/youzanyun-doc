---
apiName: "youzan.appstore.open.subscribe.query.1.0.2"
version: "1.0.2"
appName: "appstore"
apiGroup: "其它"
method: "getSubscribeMessageAllowEmpty"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3019"
---

# youzan.appstore.open.subscribe.query.1.0.2

> **所属分组**: 其它  **所属应用**: appstore

---

## 1. 场景说明

查询应用订购和授权记录，当查询订单不存在时返回为空。该接口仅限工具型应用使用，开发者可以使用应用下任意一个有效期内access_token查询该接口，注意：不支持云测试店铺对应的access_token查询

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.2`

**请求参数**（6 个）:

```json
{
  "type": "object",
  "properties": {
    "tid": {
      "type": "java.lang.String",
      "description": "有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E201912341234"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "314123141"
    },
    "start_time": {
      "type": "java.util.Date",
      "description": "开始时间，开始时间和结束时间查询间隔不内超过1个月，时间格式：yyyy-MM-dd-HH-mm-ss",
      "example": "2019-10-21 12:15:35"
    },
    "end_time": {
      "type": "java.util.Date",
      "description": "结束时间，开始时间和结束时间查询间隔不内超过1个月，时间格式：yyyy-MM-dd-HH-mm-ss",
      "example": "2019-10-21 12:15:35"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "查询时当前的页数（分页查询接口必填）",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
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

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.cloud.appstore.api.dto.response.open.SubscribeQueryResponse",
      "description": "响应参数",
      "example": ""
    },
    "details": {
      "type": "java.util.List<com.youzan.cloud.appstore.api.dto.response.open.SubscribeDetail>",
      "description": "订购详细信息",
      "example": ""
    },
    "order_type": {
      "type": "java.lang.Integer",
      "description": "订单类型； 1-应用市场订单； 2-应用内购订单； 4-服务订单（服务市场）； 5-模板市场订单； 6-服务代运营周期订单（服务市场）；",
      "example": "1"
    },
    "app_subscribe_notify_message": {
      "type": "com.youzan.cloud.appstore.api.dto.response.open.AppSubscribeNotifyMessage",
      "description": "应用订购消息",
      "example": ""
    },
    "tid": {
      "type": "java.lang.String",
      "description": "有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "20190312105415047400001"
    },
    "sku_version_text": {
      "type": "java.lang.String",
      "description": "订购版本名称",
      "example": "普通版"
    },
    "sku_interval_text": {
      "type": "java.lang.String",
      "description": "订购时长，单位：天",
      "example": "365"
    },
    "buyer_phone": {
      "type": "java.lang.String",
      "description": "买家电话",
      "example": "15800000000"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "买家id，买家在有赞的唯一id。推荐使用",
      "example": "LnhGm4rh576452722916618240"
    },
    "pay_time": {
      "type": "java.lang.Long",
      "description": "支付时间，Unix时间戳，单位：毫秒",
      "example": "1581231240000"
    },
    "kdt_id": {
      "type": "java.lang.Long",
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
  "details": "",
  "order_type": "1",
  "app_subscribe_notify_message": "",
  "tid": "20190312105415047400001",
  "sku_version_text": "普通版",
  "sku_interval_text": "365",
  "buyer_phone": "15800000000"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.appstore.open.subscribe.query/1.0.2"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3019)*