---
apiName: "youzan.bigdata.spu.query.1.0.1"
version: "1.0.1"
appName: "seller-datacenter"
apiGroup: "item"
method: "getGoodsDetailV2"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-05-18"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3768"
---
# youzan.bigdata.spu.query.1.0.1
> **所属分组**: item　**所属应用**: seller-datacenter
---
## 1. 场景说明
商品分析-单个商品详情数据接口-V2版；查询T-1的数据，次日上午8点查询，否则数据不完整。1、查询规则：date_type取值说明：0：实时查询当前数据，1：自然天，2：自然周，3：自然月，6：自定义查询天数。 2、具体说明：当date_type=0时currentDay必传当天日期。 当date_type=1时start_day和end_day可以查询历史天数数据，仅支持查询一天，不支持查询当天数据。 当date_type=6时start_day和end_day查询间隔不能大于30天，不支持查询当天数据。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.1`
**请求参数 Schema**（10 个参数）:
```json
{
  "type": "object",
  "properties": {
    "basic_param": {
      "type": "string",
      "description": "基本参数"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "总店Id，各种店铺形态都必须传递的参数",
      "example": "63077"
    },
    "kdt_id_list": {
      "type": "integer",
      "description": "查询店铺kdtId列表，如果是单店查询， 请传递仅包含单店kdtId的List；如果查询总部所有数据，该参数不传；如果查询某个子店数据，该参数传子店kdtId；如果查询合伙人数据，该参数传合伙人kdtId",
      "example": "[63077]"
    },
    "goods_id": {
      "type": "integer",
      "description": "商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.items.inventory.get （查询仓库中商品）获取",
      "example": "1961780459"
    },
    "shop_role": {
      "type": "integer",
      "description": "店铺类型: 该参数指被筛选店铺的类型， 如果是查询所有店铺则传递总部的类型。 0 -> 非连锁单店, 1 -> 连锁总部, 2 -> 连锁BU, 4 -> 连锁合伙人",
      "example": "0"
    },
    "date_type": {
      "type": "integer",
      "description": "时间类型，0：实时；1：自然日；2：自然周；3：自然月；6：自定义",
      "example": "6"
    },
    "time_param": {
      "type": "string",
      "description": "时间"
    },
    "start_day": {
      "type": "integer",
      "description": "开始时间，格式为yyyyMMdd，和endDay合用，闭区间",
      "example": "20220401"
    },
    "end_day": {
      "type": "integer",
      "description": "结束时间，格式为yyyyMMdd，和startDay合用，闭区间,如果表示某一天的话，必须和startDay相等",
      "example": "20220430"
    },
    "current_day": {
      "type": "integer",
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
**请求参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `basic_param` | `string` | ❌ | `` | 基本参数 |
| `root_kdt_id` | `integer` | ✅ | `63077` | 总店Id，各种店铺形态都必须传递的参数 |
| `kdt_id_list` | `integer` | ❌ | `[63077]` | 查询店铺kdtId列表，如果是单店查询， 请传递仅包含单店kdtId的List；如果查询总部所有数据，该参数不传；如果查询某个子店数据，该参数传子店kdtId； |
| `goods_id` | `integer` | ✅ | `1961780459` | 商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.item |
| `shop_role` | `integer` | ✅ | `0` | 店铺类型: 该参数指被筛选店铺的类型， 如果是查询所有店铺则传递总部的类型。 0 -> 非连锁单店, 1 -> 连锁总部, 2 -> 连锁BU, 4 -> 连锁 |
| `date_type` | `integer` | ✅ | `6` | 时间类型，0：实时；1：自然日；2：自然周；3：自然月；6：自定义 |
| `time_param` | `string` | ✅ | `` | 时间 |
| `start_day` | `integer` | ✅ | `20220401` | 开始时间，格式为yyyyMMdd，和endDay合用，闭区间 |
| `end_day` | `integer` | ✅ | `20220430` | 结束时间，格式为yyyyMMdd，和startDay合用，闭区间,如果表示某一天的话，必须和startDay相等 |
| `current_day` | `integer` | ❌ | `20220518` | 今日时间，当查询实时数据时，该参数必传，为当天日期 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "返回数据"
    },
    "paginator": {
      "type": "string",
      "description": "分页数据"
    },
    "page": {
      "type": "integer",
      "description": "分页数",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页数据条数",
      "example": "5"
    },
    "total_count": {
      "type": "integer",
      "description": "总数据条数",
      "example": "1"
    },
    "items": {
      "type": "array",
      "description": "商品详情数据"
    },
    "goods_id": {
      "type": "integer",
      "description": "商品id",
      "example": "844136834"
    },
    "expose_uv": {
      "type": "integer",
      "description": "曝光人数",
      "example": "1"
    },
    "expose_cnt": {
      "type": "integer",
      "description": "曝光次数",
      "example": "1"
    },
    "goods_uv": {
      "type": "integer",
      "description": "访客数",
      "example": "1"
    },
    "goods_pv": {
      "type": "integer",
      "description": "浏览量",
      "example": "1"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "paginator": "",
  "page": "1",
  "page_size": "5",
  "total_count": "1",
  "items": [],
  "goods_id": "844136834",
  "expose_uv": "1"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 返回数据 |
| `paginator` | `string` | ❌ | `` | 分页数据 |
| `page` | `integer` | ❌ | `1` | 分页数 |
| `page_size` | `integer` | ❌ | `5` | 每页数据条数 |
| `total_count` | `integer` | ❌ | `1` | 总数据条数 |
| `items` | `array` | ❌ | `` | 商品详情数据 |
| `goods_id` | `integer` | ❌ | `844136834` | 商品id |
| `expose_uv` | `integer` | ❌ | `1` | 曝光人数 |
| `expose_cnt` | `integer` | ❌ | `1` | 曝光次数 |
| `goods_uv` | `integer` | ❌ | `1` | 访客数 |
| `goods_pv` | `integer` | ❌ | `1` | 浏览量 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "root_kdt_id": "63077",\n  "kdt_id_list": "[63077]",\n  "goods_id": "1961780459",\n  "shop_role": "0",\n  "date_type": "6",\n  "time_param": "示例值",\n  "start_day": "20220401",\n  "end_day": "20220430",\n  "current_day": "20220518"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.1"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "root_kdt_id": "63077",
    "kdt_id_list": "[63077]",
    "goods_id": "1961780459",
    "shop_role": "0",
    "date_type": "6",
    "time_param": "示例值",
    "start_day": "20220401",
    "end_day": "20220430",
    "current_day": "20220518"
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