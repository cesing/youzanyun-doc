---
apiName: "youzan.bigdata.customer.behave.get.1.0.1"
version: "1.0.1"
appName: "seller-datacenter"
apiGroup: "大客CRM"
method: "findCustomerBehavePage"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1584"
---

# youzan.bigdata.customer.behave.get.1.0.1

> **所属分组**: 大客CRM  **所属应用**: seller-datacenter

---

## 1. 场景说明

获取小程序用户行为数据，当前是提供给腾讯有数

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.1`

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "start_id": {
      "type": "java.lang.Long",
      "description": "上一次获取列表最后一个id",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "页面大小，默认10，最大限制50",
      "example": "10"
    },
    "kdt_id_list": {
      "type": "java.util.List<java.lang.Long>",
      "description": "需要获取的店铺列表",
      "example": "[41433171L]"
    },
    "event_sign": {
      "type": "java.lang.String",
      "description": "事件信息： 小程序启动- performance ，小程序显示- enterapp，小程序隐藏-leaveapp，页面浏览- enterpage，搜索-search， 商品卡曝光-view_goods， 商品卡触发-open_goods，商品页浏览-enterpage，商品加购-add_cart",
      "example": "search"
    }
  },
  "required": []
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.wsc.api.model.customer.CustomerBehaveModel>",
      "description": "返回列表",
      "example": ""
    },
    "id": {
      "type": "java.lang.Long",
      "description": "数据唯一标识",
      "example": "1"
    },
    "current_day": {
      "type": "java.lang.String",
      "description": "日期，格式：yyyy-MM-dd",
      "example": "2020-11-23"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "8888"
    },
    "user_id": {
      "type": "java.lang.Long",
      "description": "有赞客户userId",
      "example": "8106822293"
    },
    "event_sign": {
      "type": "java.lang.String",
      "description": "事件类型,performance:小程序启动,enterapp:小程序显示,leaveapp:小程序隐藏,enterpage:页面浏览,share:页面分享,search:搜索,view_goods:商品卡曝光,open_goods:商品卡触发,add_cart:商品加购,商品页浏览:exposure_goods",
      "example": "search"
    },
    "page_uri": {
      "type": "java.lang.String",
      "description": "当前页uri",
      "example": "packages/salesman/salesman-center/index"
    },
    "page_title": {
      "type": "java.lang.String",
      "description": "页面标题",
      "example": "搜索"
    },
    "sdk_version": {
      "type": "java.lang.String",
      "description": "sdk版本",
      "example": "2.14.0"
    },
    "user_log_time": {
      "type": "java.lang.Long",
      "description": "用户行为触发时间。时间戳，单位：毫秒。",
      "example": "1605680523000"
    },
    "app_id": {
      "type": "java.lang.String",
      "description": "公众号或小程序唯一id",
      "example": "wx12530dfd1c7709a6"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "id": "1",
  "current_day": "2020-11-23",
  "kdt_id": "8888",
  "user_id": "8106822293",
  "event_sign": "search",
  "page_uri": "packages/salesman/salesman-center/index",
  "page_title": "搜索"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1584)*