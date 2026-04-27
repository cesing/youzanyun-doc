---
apiName: "youzan.item.detail.get.1.0.1"
version: "1.0.1"
appName: "mall-item"
apiGroup: "商品与库存"
method: "getItemDetail"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3754"
---

# youzan.item.detail.get.1.0.1

> **所属分组**: 商品与库存  **所属应用**: mall-item

---

## 1. 场景说明

该接口用于查询单个商品详细信息，需使用对应店铺下的item_id。该接口支持微商城单店、零售连锁总部、网店调用，有赞连锁总店、网店调用。注意：如果是连锁店铺情况下不支持使用alias调用，仅支持item_id调用。推荐配合商品新增【youzan.item.add】和商品更新【youzan.item.incremental.update】使用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.detail.get/1.0.1`

**请求参数**（0 个）:

```json
{
  "type": "object",
  "properties": {},
  "required": []
}
```

**响应参数**（0 个）:

```json
{
  "type": "object",
  "properties": {}
}
```

**成功响应示例**:

```json
{}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.item.detail.get/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.detail.get/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3754)*