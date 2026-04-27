---
apiName: "youzan.item.full.sku.update.1.0.0"
version: "1.0.0"
appName: "mall-item"
apiGroup: "商品与库存"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3003"
---

# youzan.item.full.sku.update.1.0.0

> **所属分组**: 商品与库存

---

## 1. 场景说明

商品sku信息全量更新接口；支持店铺类型：微商城单店，有赞连锁。支持微商城单店更新商品，微商城连锁总部更新商品，有赞微商城分店独立更新商品，零售高级版总部更新商品。目前仅支持实物商品、虚拟商品、电子卡券、茶饮烘焙类型。注意：商品规格全量更新，不传即表示删除。推荐配合商品新增【youzan.item.add】,查询单个商品详情【youzan.item.detail.get】使用和增量更新商品信息接口【youzan.item.incremental.update】

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.full.sku.update/1.0.0`

**认证方式**: 凭证式

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
curl -X POST 'https://open.youzanyun.com/api/youzan.item.full.sku.update/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.full.sku.update/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3003)*