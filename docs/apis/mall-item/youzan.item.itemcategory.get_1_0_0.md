---
apiName: "youzan.item.itemcategory.get.1.0.0"
version: "1.0.0"
appName: "mall-item"
apiGroup: "商品与库存"
method: "getItemCategory"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4591"
---

# youzan.item.itemcategory.get.1.0.0

> **所属分组**: 商品与库存  **所属应用**: mall-item

---

## 1. 场景说明

查询商品关联类目。
支持场景： 
- 1、有赞微商城单店查商品。
- 2、有赞门店：根据 商品库 查 网店、门店商品。
- 3、连锁：根据商品库 查 分店门店、网店渠道商品。

不支持场景： 
- 1、有赞门店：根据 门店商品 查 网店商品；
- 2、连锁分店 查 总部商品
- 3、连锁分店 网店渠道 查 门店渠道、门店渠道 查 网店渠道

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.itemcategory.get/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.item.itemcategory.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.itemcategory.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4591)*