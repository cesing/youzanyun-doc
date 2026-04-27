---
apiName: "youzan.bigdata.spu.query.1.0.1"
version: "1.0.1"
appName: "seller-datacenter"
apiGroup: "商品与库存"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3768"
---

# youzan.bigdata.spu.query.1.0.1

> **所属分组**: 商品与库存

---

## 1. 场景说明

商品分析-单个商品详情数据接口-V2版；查询T-1的数据，次日上午8点查询，否则数据不完整。1、查询规则：date_type取值说明：0：实时查询当前数据，1：自然天，2：自然周，3：自然月，6：自定义查询天数。 2、具体说明：当date_type=0时currentDay必传当天日期。 当date_type=1时start_day和end_day可以查询历史天数数据，仅支持查询一天，不支持查询当天数据。 当date_type=6时start_day和end_day查询间隔不能大于30天，不支持查询当天数据。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.1`

**认证方式**: 凭证式

**请求参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "basic_param": {
      "type": "com.youzan.bigdata.datacenter.base.api.param.goods.GoodsDayRangeParam",
      "description": "基本参数",
      "example": ""
    },
    "root_kdt_id": {
      "type": "java.lang.Long",
      "description": "总店Id，各种店铺形态都必须传递的参数",
      "example": "63077"
    },
    "kdt_id_list": {
      "type": "java.util.List<java.lang.Long>",
      "description": "查询店铺kdtId列表，如果是单店查询， 请传递仅包含单店kdtId的List；如果查询总部所有数据，该参数不传；如果查询某个子店数据，该参数传子店kdtId；如果查询合伙人数据，该参数传合伙人kdtId",
      "example": "[63077]"
    },
    "goods_id": {
      "type": "java.lang.Long",
      "description": "商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.items.inventory.get （查询仓库中商品）获取",
      "example": "1961780459"
    },
    "shop_role": {
      "type": "java.lang.Long",
      "description": "店铺类型: 该参数指被筛选店铺的类型， 如果是查询所有店铺则传递总部的类型。 0 -> 非连锁单店, 1 -> 连锁总部, 2 -> 连锁BU, 4 -> 连锁合伙人",
      "example": "0"
    },
    "date_type": {
      "type": "java.lang.Integer",
      "description": "时间类型，0：实时；1：自然日；2：自然周；3：自然月；6：自定义",
      "example": "6"
    },
    "time_param": {
      "type": "com.youzan.bigdata.datacenter.base.api.param.dayrange.TimeRange",
      "description": "时间",
      "example": ""
    },
    "start_day": {
      "type": "java.lang.Integer",
      "description": "开始时间，格式为yyyyMMdd，和endDay合用，闭区间",
      "example": "20220401"
    },
    "end_day": {
      "type": "java.lang.Integer",
      "description": "结束时间，格式为yyyyMMdd，和startDay合用，闭区间,如果表示某一天的话，必须和startDay相等",
      "example": "20220430"
    },
    "current_day": {
      "type": "java.lang.Integer",
      "description": "今日时间，当查询实时数据时，该参数必传，为当天日期",
      "example": "20220518"
    }
  },
  "required": [
    "root_kdt_id",
    "goods_id",
    "shop_role",
    "date_type",
    "time_param",
    "start_day",
    "end_day"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.api.common.vo.ListWithPaginatorVO<T>",
      "description": "返回数据",
      "example": ""
    },
    "paginator": {
      "type": "com.youzan.api.common.response.Paginator",
      "description": "分页数据",
      "example": ""
    },
    "page": {
      "type": "int",
      "description": "分页数",
      "example": "1"
    },
    "page_size": {
      "type": "int",
      "description": "每页数据条数",
      "example": "5"
    },
    "total_count": {
      "type": "int",
      "description": "总数据条数",
      "example": "1"
    },
    "items": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.base.api.model.goods.GoodsIndicatorsModel>",
      "description": "商品详情数据",
      "example": ""
    },
    "goods_id": {
      "type": "java.lang.Long",
      "description": "商品id",
      "example": "844136834"
    },
    "expose_uv": {
      "type": "java.lang.Long",
      "description": "曝光人数",
      "example": "1"
    },
    "expose_cnt": {
      "type": "java.lang.Long",
      "description": "曝光次数",
      "example": "1"
    },
    "goods_uv": {
      "type": "java.lang.Long",
      "description": "访客数",
      "example": "1"
    },
    "goods_pv": {
      "type": "java.lang.Long",
      "description": "浏览量",
      "example": "1"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "paginator": "",
  "page": "1",
  "page_size": "5",
  "total_count": "1",
  "items": "",
  "goods_id": "844136834",
  "expose_uv": "1"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3768)*