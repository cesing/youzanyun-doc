---
apiName: "youzan.bigdata.spu.query.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "item"
method: "getGoodsDetail"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2020-12-09"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1947"
---
# youzan.bigdata.spu.query.1.0.0
> **所属分组**: item　**所属应用**: seller-datacenter
---
## 1. 场景说明
商品分析-单个商品详情数据接口；查询T-1的数据，次日上午8点查询，否则数据不完整。查询规则：0：实时查询当前数据，1：自然天，6：自定义查询天数。 当date_type=0时start_day和end_day必传当天日期。 当date_type=1时start_day和end_day可以查询历史天数数据，仅支持查询一天，不支持查询当天数据。 当date_type=6时start_day和end_day查询间隔不能大于3天，不支持查询当天数据。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.0`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "basic_param": {
      "type": "string",
      "description": "基本参数"
    },
    "item_id": {
      "type": "integer",
      "description": "商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.items.inventory.get （查询仓库中商品）获取",
      "example": "844136834"
    },
    "start_day": {
      "type": "string",
      "description": "查询起始日期，可设置的最早日期为从当前时间往前推3个月；格式”yyyy-MM-dd“；",
      "example": "2020-12-07"
    },
    "end_day": {
      "type": "string",
      "description": "查询结束日期，可设置的最早日期为从当前时间往前推3个月；格式”yyyy-MM-dd“；",
      "example": "2020-12-08"
    },
    "date_type": {
      "type": "integer",
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
**请求参数明细**（5 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `basic_param` | `string` | ❌ | `` | 基本参数 |
| `item_id` | `integer` | ✅ | `844136834` | 商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查询出售中商品）和 youzan.item |
| `start_day` | `string` | ✅ | `2020-12-07` | 查询起始日期，可设置的最早日期为从当前时间往前推3个月；格式”yyyy-MM-dd“； |
| `end_day` | `string` | ✅ | `2020-12-08` | 查询结束日期，可设置的最早日期为从当前时间往前推3个月；格式”yyyy-MM-dd“； |
| `date_type` | `integer` | ✅ | `6` | 查询类型，0：实时查询当前数据，1：自然天，6：自定义查询天数。 当date_type=0时start_day和end_day必传当天日期。 当date_typ |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "返回数据"
    },
    "page": {
      "type": "integer",
      "description": "当前页码",
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
    "item_id": {
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
  "page": "1",
  "page_size": "5",
  "total_count": "1",
  "items": [],
  "item_id": "844136834",
  "expose_uv": "1",
  "expose_cnt": "1"
}
```
**响应参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 返回数据 |
| `page` | `integer` | ❌ | `1` | 当前页码 |
| `page_size` | `integer` | ❌ | `5` | 每页数据条数 |
| `total_count` | `integer` | ❌ | `1` | 总数据条数 |
| `items` | `array` | ❌ | `` | 商品详情数据 |
| `item_id` | `integer` | ❌ | `844136834` | 商品id |
| `expose_uv` | `integer` | ❌ | `1` | 曝光人数 |
| `expose_cnt` | `integer` | ❌ | `1` | 曝光次数 |
| `goods_uv` | `integer` | ❌ | `1` | 访客数 |
| `goods_pv` | `integer` | ❌ | `1` | 浏览量 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "item_id": "844136834",\n  "start_day": "2020-12-07",\n  "end_day": "2020-12-08",\n  "date_type": "6"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "item_id": "844136834",
    "start_day": "2020-12-07",
    "end_day": "2020-12-08",
    "date_type": "6"
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