---
apiName: "youzan.bigdata.customer.behave.get.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "大客CRM"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1562"
---

# youzan.bigdata.customer.behave.get.1.0.0

> **所属分组**: 大客CRM

---

## 1. 场景说明

获取小程序用户行为数据，当前是提供给腾讯有数

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.0`

**认证方式**: 凭证式

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "page_no": {
      "type": "java.lang.Integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "页面大小， 最大50",
      "example": "20"
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
      "type": "com.youzan.api.common.vo.ListWithPaginatorVO<com.youzan.bigdata.datacenter.wsc.api.model.customer.CustomerBehaveModel>",
      "description": "响应参数",
      "example": ""
    },
    "paginator": {
      "type": "com.youzan.api.common.response.Paginator",
      "description": "页面信息",
      "example": ""
    },
    "page_no": {
      "type": "int",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "int",
      "description": "页面大小",
      "example": "20"
    },
    "total_count": {
      "type": "int",
      "description": "总数据条数",
      "example": "907"
    },
    "items": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.wsc.api.model.customer.CustomerBehaveModel>",
      "description": "返回列表",
      "example": ""
    },
    "current_day": {
      "type": "java.lang.String",
      "description": "日期yyyy-MM-dd",
      "example": "2020-11-18"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "41433171"
    },
    "user_id": {
      "type": "java.lang.Long",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用",
      "example": "LnhGm4rh576452722916618240"
    },
    "event_sign": {
      "type": "java.lang.String",
      "description": "事件类型：小程序启动-performance ，小程序显示-enterapp，小程序隐藏-leaveapp，页面浏览-enterpage，搜索-search， 商品卡曝光-view_goods， 商品卡触发-open_goods，商品页浏览-enterpage，商品加购-add_cart",
      "example": "search"
    },
    "page_uri": {
      "type": "java.lang.String",
      "description": "当前页uri",
      "example": "packages/salesman/salesman-center/index"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "paginator": "",
  "page_no": "1",
  "page_size": "20",
  "total_count": "907",
  "items": "",
  "current_day": "2020-11-18",
  "kdt_id": "41433171"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1562)*