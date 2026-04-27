---
apiName: "youzan.bigdata.material.get.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "ka_customization"
serviceName: "com.youzan.bigdata.datacenter.proxy.api.service.seller.SellerMaterialIndexService"
method: "getMaterialsCloud"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc]
deprecated: false
since: "2020-11-03"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1504"
---
# youzan.bigdata.material.get.1.0.0
> **所属分组**: ka_customization　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
获取素材相关的统计数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.material.get/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "param": {
      "type": "array",
      "description": "是店铺ID和素材ID的列表， 即可以请求多个素材ID"
    },
    "kdt_id": {
      "type": "integer",
      "description": "网店铺id， 和下面的material_id成对使用",
      "example": "63077"
    },
    "material_id": {
      "type": "integer",
      "description": "素材id，和上面的kdt_id成对使用",
      "example": "1001"
    }
  },
  "required": [
    "kdt_id",
    "material_id"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `param` | `array` | ❌ 否 | `` | 是店铺ID和素材ID的列表， 即可以请求多个素材ID |
| `kdt_id` | `integer` | ✅ 是 | `63077` | 网店铺id， 和下面的material_id成对使用 |
| `material_id` | `integer` | ✅ 是 | `1001` | 素材id，和上面的kdt_id成对使用 |
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
    "kdt_id": {
      "type": "integer",
      "description": "店铺Id",
      "example": "63077"
    },
    "material_id": {
      "type": "integer",
      "description": "素材Id",
      "example": "1111"
    },
    "forward_cnt": {
      "type": "integer",
      "description": "素材转发次数",
      "example": "1"
    },
    "forward_user_cnt": {
      "type": "integer",
      "description": "素材转发人数",
      "example": "2"
    },
    "read_cnt": {
      "type": "integer",
      "description": "素材阅读次数(素材为文章笔记，才统计)",
      "example": "3"
    },
    "read_user_cnt": {
      "type": "integer",
      "description": "素材阅读人数(素材为文章笔记，才统计)",
      "example": "4"
    },
    "cloud_material_goods_index_model_list": {
      "type": "array",
      "description": "素材关联的商品统计数据"
    },
    "item_id": {
      "type": "integer",
      "description": "素材关联商品id",
      "example": "2222"
    },
    "item_view_cnt": {
      "type": "integer",
      "description": "关联商品的浏览次数",
      "example": "11"
    },
    "item_view_user_cnt": {
      "type": "integer",
      "description": "关联商品的浏览人数",
      "example": "12"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "kdt_id": "63077",
  "material_id": "1111",
  "forward_cnt": "1",
  "forward_user_cnt": "2",
  "read_cnt": "3",
  "read_user_cnt": "4",
  "cloud_material_goods_index_model_list": []
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` | 返回数据 |
| `kdt_id` | `integer` | ❌ 否 | `63077` | 店铺Id |
| `material_id` | `integer` | ❌ 否 | `1111` | 素材Id |
| `forward_cnt` | `integer` | ❌ 否 | `1` | 素材转发次数 |
| `forward_user_cnt` | `integer` | ❌ 否 | `2` | 素材转发人数 |
| `read_cnt` | `integer` | ❌ 否 | `3` | 素材阅读次数(素材为文章笔记，才统计) |
| `read_user_cnt` | `integer` | ❌ 否 | `4` | 素材阅读人数(素材为文章笔记，才统计) |
| `cloud_material_goods_index_model_list` | `array` | ❌ 否 | `` | 素材关联的商品统计数据 |
| `item_id` | `integer` | ❌ 否 | `2222` | 素材关联商品id |
| `item_view_cnt` | `integer` | ❌ 否 | `11` | 关联商品的浏览次数 |
| `item_view_user_cnt` | `integer` | ❌ 否 | `12` | 关联商品的浏览人数 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1504

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "kdt_id": "63077",
  "material_id": "1001"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.material.get/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "kdt_id": "63077",
  "material_id": "1001"
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
| 服务名称 | `com.youzan.bigdata.datacenter.proxy.api.service.seller.SellerMaterialIndexService` |
| 方法名称 | `getMaterialsCloud` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1504)_