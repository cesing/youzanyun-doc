---
apiName: "youzan.bigdata.consumer.goods.get.1.0.0"
version: "1.0.0"
appName: "consumer-datacenter"
apiGroup: "item"
method: "getRecommendGoods"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2020-10-20"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1454"
---
# youzan.bigdata.consumer.goods.get.1.0.0
> **所属分组**: item　**所属应用**: consumer-datacenter
---
## 1. 场景说明
基于用户ID获取店铺内个性化推荐商品列表。未登录用户返回综合评分高的商品
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.consumer.goods.get/1.0.0`
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
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `yz_open_id` | `integer` | ✅ | `joPykG3E620676084475629568` | 用户ID |
| `page_no` | `integer` | ✅ | `1` | 页码。默认1，上限20 |
| `page_size` | `integer` | ✅ | `30` | 单页大小。默认30，上限30 |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
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
**响应参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 调用返回的数据 |
| `total` | `integer` | ❌ | `1` | 可推荐的商品总数 |
| `count` | `integer` | ❌ | `1` | 列表内商品数量 |
| `recommend_list` | `array` | ❌ | `` | 根据原商品推荐的商品列表 |
| `url` | `string` | ❌ | `https://shop192223.m.youzan.com/wscgoods` | 商品链接地址 |
| `image_url` | `string` | ❌ | `https://img.yzcdn.cn/upload_files/2016/0` | 商品图片地址 |
| `price` | `integer` | ❌ | `9900` | 价格，单位分 |
| `title` | `string` | ❌ | `商品标题样例` | 商品标题 |
| `alias` | `string` | ❌ | `3nvdblmrj6p2v` | 商品Alias |
| `postage` | `integer` | ❌ | `500` | 运费，单位分 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.consumer.goods.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "yz_open_id": "joPykG3E620676084475629568",\n  "page_no": "1",\n  "page_size": "30"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.consumer.goods.get/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "yz_open_id": "joPykG3E620676084475629568",
    "page_no": "1",
    "page_size": "30"
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