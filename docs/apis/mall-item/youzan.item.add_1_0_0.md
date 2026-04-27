---
apiName: "youzan.item.add.1.0.0"
version: "1.0.0"
appName: "mall-item"
apiGroup: "商品与库存"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1113"
---

# youzan.item.add.1.0.0

> **所属分组**: 商品与库存

---

## 1. 场景说明

商品新增接口，支持店铺类型：微商城单店，有赞连锁。支持微商城单店新增商品，微商城连锁总部新增商品，有赞微商城分店独立新增商品，零售高级版总部新增商品。目前仅支持实物商品、虚拟商品、电子卡券、茶饮烘焙类型。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.add/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.item.add/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.add/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1113)*