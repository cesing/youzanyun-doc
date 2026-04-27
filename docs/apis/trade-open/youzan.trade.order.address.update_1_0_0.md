---
apiName: "youzan.trade.order.address.update.1.0.0"
version: "1.0.0"
appName: "trade-open"
apiGroup: "交易订单"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1467"
---

# youzan.trade.order.address.update.1.0.0

> **所属分组**: 交易订单

---

## 1. 场景说明

修改订单收货地址。订单收货地址仅支持修改一次，商户可以调用该接口修改订单的收货地址，此接口仅提供修改地址能力，不会重新计算邮费。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.order.address.update/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.order.address.update/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.order.address.update/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1467)*