---
apiName: "youzan.bigdata.material.get.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "大客CRM"
method: "getMaterialsCloud"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1504"
---

# youzan.bigdata.material.get.1.0.0

> **所属分组**: 大客CRM  **所属应用**: seller-datacenter

---

## 1. 场景说明

获取素材相关的统计数据

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.material.get/1.0.0`

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "param": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.proxy.api.param.seller.MaterialIndexParam>",
      "description": "是店铺ID和素材ID的列表， 即可以请求多个素材ID",
      "example": ""
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "网店铺id， 和下面的material_id成对使用",
      "example": "63077"
    },
    "material_id": {
      "type": "java.lang.Long",
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

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.proxy.api.model.seller.CloudMaterialIndexModel>",
      "description": "返回数据",
      "example": ""
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺Id",
      "example": "63077"
    },
    "material_id": {
      "type": "java.lang.Long",
      "description": "素材Id",
      "example": "1111"
    },
    "forward_cnt": {
      "type": "java.lang.Long",
      "description": "素材转发次数",
      "example": "1"
    },
    "forward_user_cnt": {
      "type": "java.lang.Long",
      "description": "素材转发人数",
      "example": "2"
    },
    "read_cnt": {
      "type": "java.lang.Long",
      "description": "素材阅读次数(素材为文章笔记，才统计)",
      "example": "3"
    },
    "read_user_cnt": {
      "type": "java.lang.Long",
      "description": "素材阅读人数(素材为文章笔记，才统计)",
      "example": "4"
    },
    "cloud_material_goods_index_model_list": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.proxy.api.model.seller.CloudMaterialGoodsIndexModel>",
      "description": "素材关联的商品统计数据",
      "example": ""
    },
    "item_id": {
      "type": "java.lang.Long",
      "description": "素材关联商品id",
      "example": "2222"
    },
    "item_view_cnt": {
      "type": "java.lang.Long",
      "description": "关联商品的浏览次数",
      "example": "11"
    },
    "item_view_user_cnt": {
      "type": "java.lang.Long",
      "description": "关联商品的浏览人数",
      "example": "12"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "kdt_id": "63077",
  "material_id": "1111",
  "forward_cnt": "1",
  "forward_user_cnt": "2",
  "read_cnt": "3",
  "read_user_cnt": "4",
  "cloud_material_goods_index_model_list": ""
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.material.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.material.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1504)*