---
apiName: "youzan.trade.order.operate.pay.1.0.0"
version: "1.0.0"
appName: "trade-open"
apiGroup: "交易订单"
method: "pay"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4024"
---

# youzan.trade.order.operate.pay.1.0.0

> **所属分组**: 交易订单  **所属应用**: trade-open

---

## 1. 场景说明

外部订单支付接口，将订单流转到已支付状态。支付后，订单状态会根据对应下单流程的交付方式流转。例如物流交付订单，会直接将订单推进到待发货。该接口仅支持指定合作方、在开发支持下使用。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.order.operate.pay/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.order.operate.pay/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.order.operate.pay/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4024)*