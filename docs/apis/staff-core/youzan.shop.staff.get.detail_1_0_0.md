---
apiName: "youzan.shop.staff.get.detail.1.0.0"
version: "1.0.0"
appName: "staff-core"
apiGroup: "店铺信息"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1391"
---

# youzan.shop.staff.get.detail.1.0.0

> **所属分组**: 店铺信息

---

## 1. 场景说明

分页查询员工详情信息，支持单店（mode="SELF_SHOP"，默认）和连锁范围(mode="CHAIN_SHOP")查询，单店时无需分页

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.shop.staff.get.detail/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.shop.staff.get.detail/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.shop.staff.get.detail/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1391)*