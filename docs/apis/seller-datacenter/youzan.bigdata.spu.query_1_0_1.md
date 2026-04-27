---
apiName: "youzan.bigdata.spu.query.1.0.1"
version: "1.0.1"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "item"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.goods.GoodsDetailService"
method: "getGoodsDetailV2"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, retail_d_partner, retail_head, retail_online, retail_partner, retail_head_high, retail_offline]
deprecated: false
since: "2022-05-18"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3768"
---
# youzan.bigdata.spu.query.1.0.1
> **所属分组**: item　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
商品分析-单个商品详情数据接口-V2版；查询T-1的数据，次日上午8点查询，否则数据不完整。1、查询规则：date_type取值说明：0：实时查询当前数据，1：自然天，2：自然周，3：自然月，6：自定义查询天数。 2、具体说明：当date_type=0时currentDay必传当天日期。 当date_type=1时start_day和end_day可以查询历史天数数据，仅支持查询一天，不支持查询当天数据。 当date_type=6时start_day和end_day查询间隔不能大于30天，不支持查询当天数据。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（10 个参数）:
```json
{
  "type": "object",
  "properties": {
    "basic_param": {
      "type": "object",
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
      "type": "object",
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `basic_param` | `object` | ❌ 否 | `` | 基本参数 |
| `root_kdt_id` | `integer` | ✅ 是 | `63077` | 总店Id，各种店铺形态都必须传递的参数 |
| `kdt_id_list` | `integer` | ❌ 否 | `[63077]` | 查询店铺kdtId列表，如果是单店查询， 请传递仅包含单店kdtId的List；如果查询总部所有数据，该参数不传；如果查 |
| `goods_id` | `integer` | ✅ 是 | `1961780459` | 商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查 |
| `shop_role` | `integer` | ✅ 是 | `0` | 店铺类型: 该参数指被筛选店铺的类型， 如果是查询所有店铺则传递总部的类型。 0 -> 非连锁单店, 1 -> 连锁总部 |
| `date_type` | `integer` | ✅ 是 | `6` | 时间类型，0：实时；1：自然日；2：自然周；3：自然月；6：自定义 |
| `time_param` | `object` | ✅ 是 | `` | 时间 |
| `start_day` | `integer` | ✅ 是 | `20220401` | 开始时间，格式为yyyyMMdd，和endDay合用，闭区间 |
| `end_day` | `integer` | ✅ 是 | `20220430` | 结束时间，格式为yyyyMMdd，和startDay合用，闭区间,如果表示某一天的话，必须和startDay相等 |
| `current_day` | `integer` | ❌ 否 | `20220518` | 今日时间，当查询实时数据时，该参数必传，为当天日期 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "返回数据"
    },
    "paginator": {
      "type": "object",
      "description": "分页数据"
    },
    "page": {
      "type": "string",
      "description": "分页数",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页数据条数",
      "example": "5"
    },
    "total_count": {
      "type": "string",
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
  "data": "",
  "paginator": "",
  "page": "1",
  "page_size": "5",
  "total_count": "1",
  "items": [],
  "goods_id": "844136834",
  "expose_uv": "1"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 返回数据 |
| `paginator` | `object` | ❌ 否 | `` | 分页数据 |
| `page` | `string` | ❌ 否 | `1` | 分页数 |
| `page_size` | `string` | ❌ 否 | `5` | 每页数据条数 |
| `total_count` | `string` | ❌ 否 | `1` | 总数据条数 |
| `items` | `array` | ❌ 否 | `` | 商品详情数据 |
| `goods_id` | `integer` | ❌ 否 | `844136834` | 商品id |
| `expose_uv` | `integer` | ❌ 否 | `1` | 曝光人数 |
| `expose_cnt` | `integer` | ❌ 否 | `1` | 曝光次数 |
| `goods_uv` | `integer` | ❌ 否 | `1` | 访客数 |
| `goods_pv` | `integer` | ❌ 否 | `1` | 浏览量 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3768

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "root_kdt_id": "63077",
  "goods_id": "1961780459",
  "shop_role": "0",
  "date_type": "6",
  "time_param": "<time_param>"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.1"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "root_kdt_id": "63077",
  "goods_id": "1961780459",
  "shop_role": "0",
  "date_type": "6",
  "time_param": "<time_param>"
}

response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

> ⚠️ **注意**：以上为示例代码，`access_token` 需要通过 OAuth2.0 流程获取。
> 真实调用地址和参数请以管理后台详情页为准。

---
## 5. 错误码
## 错误码

| 错误码 | 说明 | 处理建议 |
|--------|------|----------|
| 1000 | 系统内部错误 | 稍后重试或联系技术支持 |
| 1001 | 鉴权失败 | 检查 access_token 是否有效 |
| 1002 | 参数校验失败 | 检查必填参数是否完整 |
| 1003 | 权限不足 | 确认应用已开通对应接口权限 |
| 1004 | 频率超限 | 降低请求频率或申请更高配额 |
| 1005 | 资源不存在 | 检查请求的业务 ID 是否正确 |
| 1006 | 请求超时 | 增加超时时间或稍后重试 |
| 1007 | 账户欠费 | 完成账户充值后重试 |

> 更多错误码请参考：[有赞云错误码文档](https://doc.youzanyun.com) |

---
## 6. 内部服务信息
| 字段 | 值 |
|------|---|
| 协议类型 | dubbo |
| 服务名称 | `com.youzan.bigdata.datacenter.base.api.service.goods.GoodsDetailService` |
| 方法名称 | `getGoodsDetailV2` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3768)_