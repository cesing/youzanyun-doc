---
apiName: "youzan.crm.customer.pointstore.update.pointgoods.1.0.0"
version: "1.0.0"
appName: "scrm-open-java"
apiGroup: "营销优惠"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/998"
---

# youzan.crm.customer.pointstore.update.pointgoods.1.0.0

> **所属分组**: 营销优惠

---

## 1. 场景说明

更新积分商城的商品信息，最小必传参数示例：{
  "update_point_goods": {
    "term_start_at": 1625068800,
    "term_end_at": 1625155200,
    "goods_id": 405519242,
    "goods_type": 1,
    "available_stock": 1,
    "operator": {
      "account_type": 5,
      "account_id": "7j3Gi1UH732330877366837248"
    }
  }
}


---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.crm.customer.pointstore.update.pointgoods/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.crm.customer.pointstore.update.pointgoods/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.crm.customer.pointstore.update.pointgoods/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/998)*