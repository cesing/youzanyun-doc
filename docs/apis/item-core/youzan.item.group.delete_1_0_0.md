---
apiName: "youzan.item.group.delete.1.0.0"
version: "1.0.0"
appName: "item-core"
apiGroup: "商品与库存"
method: "delete"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4667"
---

# youzan.item.group.delete.1.0.0

> **所属分组**: 商品与库存  **所属应用**: item-core

---

## 1. 场景说明

删除商品分组。
支持场景：
- 微商城单店
- 零售单店
- 连锁总部删除自己创建的分组。
- 分店删除自己创建的分组。

不支持场景：
- 连锁总部不能删除分店创建的分组。
- 连锁分店不能删除总部创建的分组。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.group.delete/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.item.group.delete/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.group.delete/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4667)*