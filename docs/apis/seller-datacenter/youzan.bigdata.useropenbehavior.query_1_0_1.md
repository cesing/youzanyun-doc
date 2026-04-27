---
apiName: "youzan.bigdata.useropenbehavior.query.1.0.1"
version: "1.0.1"
appName: "seller-datacenter"
apiGroup: "数据分析"
method: "scan"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3033"
---

# youzan.bigdata.useropenbehavior.query.1.0.1

> **所属分组**: 数据分析  **所属应用**: seller-datacenter

---

## 1. 场景说明

店铺用户行为数据接口（大客户专属），每天早上9点更新前一天的用户行为数据

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.1`

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "current_day": {
      "type": "java.lang.String",
      "description": "日期，日期的格式为：yyyy-MM-dd,只支持获取昨日数据",
      "example": "2021-07-08"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "分页信息_页数",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "分页信息_每页的条数，最小为1，最大为100",
      "example": "10"
    }
  },
  "required": [
    "current_day",
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
      "type": "java.util.List<com.youzan.bigdata.datacenter.base.api.model.customer.UserOpenBehaviorModel>",
      "description": "业务数据",
      "example": ""
    },
    "yz_open_id": {
      "type": "java.lang.String",
      "description": "有赞客户id，客户在有赞的唯一id",
      "example": "LnhGm4rh576452722916618240"
    },
    "user_log_time": {
      "type": "java.lang.Long",
      "description": "行为发生时间。13位时间戳。毫秒",
      "example": "1626056989619"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "888888"
    },
    "root_kdt_id": {
      "type": "java.lang.Long",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "888888"
    },
    "current_day": {
      "type": "java.lang.String",
      "description": "日期，格式：yyyyMMdd",
      "example": "20210708"
    },
    "page_url": {
      "type": "java.lang.String",
      "description": "用户行为发生的页面地址",
      "example": "https://www.youzan.com/"
    },
    "page_title": {
      "type": "java.lang.String",
      "description": "用户行为发生的页面标题",
      "example": "主页"
    },
    "event_sign": {
      "type": "java.lang.String",
      "description": "用户行为的事件标识,枚举值过多，具体参见每个大客的大客文档",
      "example": "enterpage"
    },
    "scene_level1": {
      "type": "java.lang.String",
      "description": "流量来源的一级分类：渠道",
      "example": "h5"
    },
    "scene_level2": {
      "type": "java.lang.String",
      "description": "流量来源的二级分类：小程序下为wexin、alipay、baidu、qq等",
      "example": "weixin"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "yz_open_id": "LnhGm4rh576452722916618240",
  "user_log_time": "1626056989619",
  "kdt_id": "888888",
  "root_kdt_id": "888888",
  "current_day": "20210708",
  "page_url": "https://www.youzan.com/",
  "page_title": "主页"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3033)*