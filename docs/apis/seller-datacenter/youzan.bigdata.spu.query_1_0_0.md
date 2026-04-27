---
apiName: "youzan.bigdata.spu.query.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "item"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.goods.GoodsDetailService"
method: "getGoodsDetail"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail_head_high]
deprecated: false
since: "2020-12-09"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1947"
---
# youzan.bigdata.spu.query.1.0.0
> **所属分组**: item　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
商品分析-单个商品详情数据接口；查询T-1的数据，次日上午8点查询，否则数据不完整。查询规则：0：实时查询当前数据，1：自然天，6：自定义查询天数。 当date_type=0时start_day和end_day必传当天日期。 当date_type=1时start_day和end_day可以查询历史天数数据，仅支持查询一天，不支持查询当天数据。 当date_type=6时start_day和end_day查询间隔不能大于3天，不支持查询当天数据。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "basic_param": {
      "type": "object",
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `basic_param` | `object` | ❌ 否 | `` | 基本参数 |
| `item_id` | `integer` | ✅ 是 | `844136834` | 商品Id，有赞生成的店铺下商品唯一id，平台唯一。可以通过列表接口如youzan.items.onsale.get （查 |
| `start_day` | `string` | ✅ 是 | `2020-12-07` | 查询起始日期，可设置的最早日期为从当前时间往前推3个月；格式”yyyy-MM-dd“； |
| `end_day` | `string` | ✅ 是 | `2020-12-08` | 查询结束日期，可设置的最早日期为从当前时间往前推3个月；格式”yyyy-MM-dd“； |
| `date_type` | `integer` | ✅ 是 | `6` | 查询类型，0：实时查询当前数据，1：自然天，6：自定义查询天数。 当date_type=0时start_day和end_ |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "返回数据"
    },
    "page": {
      "type": "string",
      "description": "当前页码",
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
  "data": "",
  "page": "1",
  "page_size": "5",
  "total_count": "1",
  "items": [],
  "item_id": "844136834",
  "expose_uv": "1",
  "expose_cnt": "1"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 返回数据 |
| `page` | `string` | ❌ 否 | `1` | 当前页码 |
| `page_size` | `string` | ❌ 否 | `5` | 每页数据条数 |
| `total_count` | `string` | ❌ 否 | `1` | 总数据条数 |
| `items` | `array` | ❌ 否 | `` | 商品详情数据 |
| `item_id` | `integer` | ❌ 否 | `844136834` | 商品id |
| `expose_uv` | `integer` | ❌ 否 | `1` | 曝光人数 |
| `expose_cnt` | `integer` | ❌ 否 | `1` | 曝光次数 |
| `goods_uv` | `integer` | ❌ 否 | `1` | 访客数 |
| `goods_pv` | `integer` | ❌ 否 | `1` | 浏览量 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1947

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "item_id": "844136834",
  "start_day": "2020-12-07",
  "end_day": "2020-12-08",
  "date_type": "6"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.spu.query/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "item_id": "844136834",
  "start_day": "2020-12-07",
  "end_day": "2020-12-08",
  "date_type": "6"
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
| 方法名称 | `getGoodsDetail` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1947)_