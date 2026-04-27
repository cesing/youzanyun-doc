---
apiName: "youzan.item.update.3.0.1"
version: "3.0.1"
appName: "ic"
apiGroup: "商品与库存"
method: "updateItem301"
timeout: 10000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/517"
---

# youzan.item.update.3.0.1

> **所属分组**: 商品与库存  **所属应用**: ic

---

## 1. 场景说明

推荐使用新版商品更新【youzan.item.incremental.update】，配合新版商品新增【youzan.item.add】和新版查询单个商品详情【youzan.item.detail.get】。
该接口用于更新商品信息，新增支持修改类目数据。
该接口支持微商城连锁总店，不支持微商城零售连锁分店调用。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.update/3.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.item.update/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.update/3.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/517)*