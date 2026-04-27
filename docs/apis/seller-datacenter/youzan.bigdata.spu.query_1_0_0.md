---
apiName: "youzan.bigdata.spu.query.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "商品与库存"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1947"
---

# youzan.bigdata.spu.query.1.0.0

> **所属分组**: 商品与库存

---

## 1. 场景说明

商品分析-单个商品详情数据接口；查询T-1的数据，次日上午8点查询，否则数据不完整。查询规则：0：实时查询当前数据，1：自然天，6：自定义查询天数。 当date_type=0时start_day和end_day必传当天日期。 当date_type=1时start_day和end_day可以查询历史天数数据，仅支持查询一天，不支持查询当天数据。 当date_type=6时start_day和end_day查询间隔不能大于3天，不支持查询当天数据。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.0`

**认证方式**: 凭证式

**请求参数**（5 个）:

```json
{
  "type": "object",
  "properties": {
    "basic_param": {
      "type": "com.youzan.bigdata.datacenter.base.api.param.goods.GoodsDetailDayParam",
      "description": "基本参数",
      "example": ""
    },
    "item_id": {
      "type": "java.lang.Long",
      "description": "商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.items.inventory.get （查询仓库中商品）获取",
      "example": "844136834"
    },
    "start_day": {
      "type": "java.lang.String",
      "description": "查询起始日期，可设置的最早日期为从当前时间往前推3个月；格式”yyyy-MM-dd“；",
      "example": "2020-12-07"
    },
    "end_day": {
      "type": "java.lang.String",
      "description": "查询结束日期，可设置的最早日期为从当前时间往前推3个月；格式”yyyy-MM-dd“；",
      "example": "2020-12-08"
    },
    "date_type": {
      "type": "java.lang.Integer",
      "description": "查询类型，0：实时查询当前数据，1：自然天，6：自定义查询天数。 当date_type=0时start_day和end_day必传当天日期。 当date_type=1时start_day和end_day可以查询历史天数数据，仅支持查询一天，不支持查询当天数据。 当date_type=6时start_day和end_day查询间隔不能大于3天，不支持查询当天数据。",
      "example": "6"
    }
  },
  "required": [
    "item_id",
    "start_day",
    "end_day",
    "date_type"
  ]
}
```

**响应参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.api.common.vo.ListWithPaginatorVO<T>",
      "description": "返回数据",
      "example": ""
    },
    "page": {
      "type": "int",
      "description": "当前页码",
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
    "item_id": {
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
  "page": "1",
  "page_size": "5",
  "total_count": "1",
  "items": "",
  "item_id": "844136834",
  "expose_uv": "1",
  "expose_cnt": "1"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1947)*