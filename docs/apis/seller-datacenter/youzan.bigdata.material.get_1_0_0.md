---
apiName: "youzan.bigdata.material.get.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "ka_customization"
method: "getMaterialsCloud"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2020-11-03"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1504"
---
# youzan.bigdata.material.get.1.0.0
> **所属分组**: ka_customization　**所属应用**: seller-datacenter
---
## 1. 场景说明
获取素材相关的统计数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.material.get/1.0.0`
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
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `param` | `array` | ❌ | `` | 是店铺ID和素材ID的列表， 即可以请求多个素材ID |
| `kdt_id` | `integer` | ✅ | `63077` | 网店铺id， 和下面的material_id成对使用 |
| `material_id` | `integer` | ✅ | `1001` | 素材id，和上面的kdt_id成对使用 |
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
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 返回数据 |
| `kdt_id` | `integer` | ❌ | `63077` | 店铺Id |
| `material_id` | `integer` | ❌ | `1111` | 素材Id |
| `forward_cnt` | `integer` | ❌ | `1` | 素材转发次数 |
| `forward_user_cnt` | `integer` | ❌ | `2` | 素材转发人数 |
| `read_cnt` | `integer` | ❌ | `3` | 素材阅读次数(素材为文章笔记，才统计) |
| `read_user_cnt` | `integer` | ❌ | `4` | 素材阅读人数(素材为文章笔记，才统计) |
| `cloud_material_goods_index_model_list` | `array` | ❌ | `` | 素材关联的商品统计数据 |
| `item_id` | `integer` | ❌ | `2222` | 素材关联商品id |
| `item_view_cnt` | `integer` | ❌ | `11` | 关联商品的浏览次数 |
| `item_view_user_cnt` | `integer` | ❌ | `12` | 关联商品的浏览人数 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.material.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "kdt_id": "63077",\n  "material_id": "1001"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.material.get/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "kdt_id": "63077",
    "material_id": "1001"
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