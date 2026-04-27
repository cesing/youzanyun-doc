---
apiName: "youzan.item.update.listing.3.0.1"
version: "3.0.1"
appName: "mall-item"
apiGroup: "商品与库存"
method: "takeUp"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/516"
---

# youzan.item.update.listing.3.0.1

> **所属分组**: 商品与库存  **所属应用**: mall-item

---

## 1. 场景说明

用于上架商品，请求执行成功立即生效。使用yz_open_id选填，用于记录操作人，便于问题追溯。支持单店、微商城连锁总部、微商城连锁分店上架商品，支持微商城连锁总部、零售高级版总部上架分店商品。注意：教育店铺仅支持订购实物扩展包后的实物商品.
备注：2024年7月下线，替代接口youzan.item.display.update

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.update.listing/3.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.item.update.listing/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.update.listing/3.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/516)*