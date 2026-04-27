---
apiName: "youzan.trade.dc.delivery.ordersingleitemsend.3.0.1"
version: "3.0.1"
appName: "trade-open"
apiGroup: "交易订单"
method: "orderSingleItemSend"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/525"
---

# youzan.trade.dc.delivery.ordersingleitemsend.3.0.1

> **所属分组**: 交易订单  **所属应用**: trade-open

---

## 1. 场景说明

用于一笔订单一种商品有多个数量进行拆单发货，支持选择多家物流发货。支持分开调用，使用（num）数量参数控制一笔订单是否全部发货。如果要分开调用调用间隔需要大于10秒以上，请开发者做好逻辑处理，否则会出现报错"不能同时发起两笔相同的发货请求"。物流信息同步有赞成功后，用户端和商家端可以在订单详情页面查看物流轨迹
零售多仓改派的不支持

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.dc.delivery.ordersingleitemsend/3.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.dc.delivery.ordersingleitemsend/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.dc.delivery.ordersingleitemsend/3.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/525)*