---
apiName: "youzan.bigdata.consumer.goods.get.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "consumer-datacenter"
apiGroup: "item"
serviceName: "com.youzan.bigdata.datacenter.consumer.api.service.GoodsOpenService"
method: "getRecommendGoods"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2020-10-20"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1454"
---
# youzan.bigdata.consumer.goods.get.1.0.0
> **所属分组**: item　**所属应用**: consumer-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
基于用户ID获取店铺内个性化推荐商品列表。未登录用户返回综合评分高的商品
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.consumer.goods.get/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "用户ID",
      "example": "joPykG3E620676084475629568"
    },
    "page_no": {
      "type": "integer",
      "description": "页码。默认1，上限20",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "单页大小。默认30，上限30",
      "example": "30"
    }
  },
  "required": [
    "yz_open_id",
    "page_no",
    "page_size"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `yz_open_id` | `integer` | ✅ 是 | `joPykG3E620676084475629568` | 用户ID |
| `page_no` | `integer` | ✅ 是 | `1` | 页码。默认1，上限20 |
| `page_size` | `integer` | ✅ 是 | `30` | 单页大小。默认30，上限30 |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "调用返回的数据"
    },
    "total": {
      "type": "integer",
      "description": "可推荐的商品总数",
      "example": "1"
    },
    "count": {
      "type": "integer",
      "description": "列表内商品数量",
      "example": "1"
    },
    "recommend_list": {
      "type": "array",
      "description": "根据原商品推荐的商品列表"
    },
    "url": {
      "type": "string",
      "description": "商品链接地址",
      "example": "https://shop192223.m.youzan.com/wscgoods/detail/1y3yr1eexdhk7"
    },
    "image_url": {
      "type": "string",
      "description": "商品图片地址",
      "example": "https://img.yzcdn.cn/upload_files/2016/09/19/Fk8CoaU1Pf7d4QQa0AjZ1_OCSxsb.png"
    },
    "price": {
      "type": "integer",
      "description": "价格，单位分",
      "example": "9900"
    },
    "title": {
      "type": "string",
      "description": "商品标题",
      "example": "商品标题样例"
    },
    "alias": {
      "type": "string",
      "description": "商品Alias",
      "example": "3nvdblmrj6p2v"
    },
    "postage": {
      "type": "integer",
      "description": "运费，单位分",
      "example": "500"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "total": "1",
  "count": "1",
  "recommend_list": [],
  "url": "https://shop192223.m.youzan.com/wscgoods/detail/1y3yr1eexdhk7",
  "image_url": "https://img.yzcdn.cn/upload_files/2016/09/19/Fk8CoaU1Pf7d4QQa0AjZ1_OCSxsb.png",
  "price": "9900",
  "title": "商品标题样例"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 调用返回的数据 |
| `total` | `integer` | ❌ 否 | `1` | 可推荐的商品总数 |
| `count` | `integer` | ❌ 否 | `1` | 列表内商品数量 |
| `recommend_list` | `array` | ❌ 否 | `` | 根据原商品推荐的商品列表 |
| `url` | `string` | ❌ 否 | `https://shop192223.m.youzan.co` | 商品链接地址 |
| `image_url` | `string` | ❌ 否 | `https://img.yzcdn.cn/upload_fi` | 商品图片地址 |
| `price` | `integer` | ❌ 否 | `9900` | 价格，单位分 |
| `title` | `string` | ❌ 否 | `商品标题样例` | 商品标题 |
| `alias` | `string` | ❌ 否 | `3nvdblmrj6p2v` | 商品Alias |
| `postage` | `integer` | ❌ 否 | `500` | 运费，单位分 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1454

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "yz_open_id": "joPykG3E620676084475629568",
  "page_no": "1",
  "page_size": "30"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.consumer.goods.get/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "yz_open_id": "joPykG3E620676084475629568",
  "page_no": "1",
  "page_size": "30"
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
| 服务名称 | `com.youzan.bigdata.datacenter.consumer.api.service.GoodsOpenService` |
| 方法名称 | `getRecommendGoods` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1454)_