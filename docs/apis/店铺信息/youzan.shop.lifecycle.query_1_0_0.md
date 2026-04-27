---
apiName: "youzan.shop.lifecycle.query.1.0.0"
version: "1.0.0"
appName: "shop-front"
apiGroup: "店铺信息"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4066"
---

# youzan.shop.lifecycle.query.1.0.0

> **所属分组**: 店铺信息

---

## 1. 场景说明

用于查询店铺生命周期。在单店模式下可查询当前店铺的生命周期；在连锁场景下，可查询在同一连锁下的门店，网店，独立仓，合伙人,外部店铺,分销供货店铺,前置仓,虚拟MU。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.shop.lifecycle.query/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.shop.lifecycle.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.shop.lifecycle.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4066)*