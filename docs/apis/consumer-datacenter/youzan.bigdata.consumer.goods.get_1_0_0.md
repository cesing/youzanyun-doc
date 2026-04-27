---
apiName: "youzan.bigdata.consumer.goods.get.1.0.0"
version: "1.0.0"
appName: "consumer-datacenter"
apiGroup: "商品与库存"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1454"
---

# youzan.bigdata.consumer.goods.get.1.0.0

> **所属分组**: 商品与库存

---

## 1. 场景说明

基于用户ID获取店铺内个性化推荐商品列表。未登录用户返回综合评分高的商品

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.consumer.goods.get/1.0.0`

**认证方式**: 凭证式

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "用户ID",
      "example": "joPykG3E620676084475629568"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "页码。默认1，上限20",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
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

**响应参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.consumer.api.response.ResponseOpenDTO",
      "description": "调用返回的数据",
      "example": ""
    },
    "total": {
      "type": "java.lang.Integer",
      "description": "可推荐的商品总数",
      "example": "1"
    },
    "count": {
      "type": "java.lang.Integer",
      "description": "列表内商品数量",
      "example": "1"
    },
    "recommend_list": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.consumer.api.vo.GoodsRecommendVO>",
      "description": "根据原商品推荐的商品列表",
      "example": ""
    },
    "url": {
      "type": "java.lang.String",
      "description": "商品链接地址",
      "example": "https://shop192223.m.youzan.com/wscgoods/detail/1y3yr1eexdhk7"
    },
    "image_url": {
      "type": "java.lang.String",
      "description": "商品图片地址",
      "example": "https://img.yzcdn.cn/upload_files/2016/09/19/Fk8CoaU1Pf7d4QQa0AjZ1_OCSxsb.png"
    },
    "price": {
      "type": "java.lang.Long",
      "description": "价格，单位分",
      "example": "9900"
    },
    "title": {
      "type": "java.lang.String",
      "description": "商品标题",
      "example": "商品标题样例"
    },
    "alias": {
      "type": "java.lang.String",
      "description": "商品Alias",
      "example": "3nvdblmrj6p2v"
    },
    "postage": {
      "type": "java.lang.Long",
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
  "recommend_list": "",
  "url": "https://shop192223.m.youzan.com/wscgoods/detail/1y3yr1eexdhk7",
  "image_url": "https://img.yzcdn.cn/upload_files/2016/09/19/Fk8CoaU1Pf7d4QQa0AjZ1_OCSxsb.png",
  "price": "9900",
  "title": "商品标题样例"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.consumer.goods.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.consumer.goods.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1454)*