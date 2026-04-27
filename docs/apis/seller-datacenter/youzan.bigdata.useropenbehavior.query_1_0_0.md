---
apiName: "youzan.bigdata.useropenbehavior.query.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "数据分析"
method: "scan"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3021"
---

# youzan.bigdata.useropenbehavior.query.1.0.0

> **所属分组**: 数据分析  **所属应用**: seller-datacenter

---

## 1. 场景说明

店铺用户行为数据接口（大客户专属），每天早上9点更新前一天的用户行为数据

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.0`

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "current_day": {
      "type": "java.lang.String",
      "description": "日期，日期的格式为：yyyy-MM-dd",
      "example": "2021-07-08"
    },
    "page_num": {
      "type": "java.lang.Integer",
      "description": "页数",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "每页查看的条数",
      "example": "100"
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
      "type": "java.util.List<com.youzan.bigdata.datacenter.base.api.model.customer.UserOpenBehaviorModel>",
      "description": "业务数据",
      "example": ""
    },
    "yz_uid": {
      "type": "java.lang.String",
      "description": "有赞用户id",
      "example": "1"
    },
    "user_log_time": {
      "type": "java.lang.Long",
      "description": "行为发生时间。13位时间戳",
      "example": "1234567891234"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "91619160"
    },
    "hq_kdt_id": {
      "type": "java.lang.Long",
      "description": "连锁店铺,总店id,非连锁店铺等同于kdt_id",
      "example": "91619160"
    },
    "current_day": {
      "type": "java.lang.String",
      "description": "日期，格式：yyyy-MM-dd",
      "example": "2021-07-08"
    },
    "page": {
      "type": "java.lang.String",
      "description": "行为发生页面地址",
      "example": "https://shimo.im/docs/VMAPV72EwMSayEqg"
    },
    "page_title": {
      "type": "java.lang.String",
      "description": "行为发生页面标题",
      "example": "埋点分析中间层"
    },
    "event_sign": {
      "type": "java.lang.String",
      "description": "行为事件标识",
      "example": "enterpage"
    },
    "scene_level1": {
      "type": "java.lang.String",
      "description": "流量来源第一级:小程序下为weapp",
      "example": "enterpage"
    },
    "scene_level2": {
      "type": "java.lang.String",
      "description": "流量来源第二级:小程序下为wexin、alipay、baidu、qq等",
      "example": "enterpage"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "yz_uid": "1",
  "user_log_time": "1234567891234",
  "kdt_id": "91619160",
  "hq_kdt_id": "91619160",
  "current_day": "2021-07-08",
  "page": "https://shimo.im/docs/VMAPV72EwMSayEqg",
  "page_title": "埋点分析中间层"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3021)*