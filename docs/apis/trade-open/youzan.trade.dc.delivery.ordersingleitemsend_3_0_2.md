---
apiName: "youzan.trade.dc.delivery.ordersingleitemsend.3.0.2"
version: "3.0.2"
appName: "trade-open"
apiGroup: "交易订单"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2930"
---

# youzan.trade.dc.delivery.ordersingleitemsend.3.0.2

> **所属分组**: 交易订单

---

## 1. 场景说明

用于一笔订单一种商品有多个数量进行拆单发货，支持选择多家物流发货。即一笔订单中，同种商品有多个时，必须一次性全部发货，不可以分多次发货，使用（num）数量参数控制一笔订单是否全部发货。支持随心订订单单商品多运单发货，单商品发货数量需要等于单期发货数量。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.dc.delivery.ordersingleitemsend/3.0.2`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.dc.delivery.ordersingleitemsend/3.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.dc.delivery.ordersingleitemsend/3.0.2"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2930)*