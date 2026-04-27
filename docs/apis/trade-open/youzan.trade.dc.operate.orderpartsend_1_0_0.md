---
apiName: "youzan.trade.dc.operate.orderpartsend.1.0.0"
version: "1.0.0"
appName: "trade-open"
apiGroup: "交易订单"
method: "orderPartSend"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/5031"
---

# youzan.trade.dc.operate.orderpartsend.1.0.0

> **所属分组**: 交易订单  **所属应用**: trade-open

---

## 1. 场景说明

订单部分发货，支持以下场景
1.单商品拆分多运单全部发货，使用该能力，需要在有赞店铺后台开通多包裹能力，package_list需要传入多个包裹，每个package里的items仅支持传入1个，且oid必须相同。替代原youzan.trade.dc.delivery.ordersingleitemsend.3.0.2接口能力。
2.单商品拆分多运单部分发货，package_list仅支持传入一个，items仅支持传入一个。替代原youzan.trade.dc.operate.ordersingleitempartsend.1.0.0接口能力。
3.多商品拆分多运单部分发货，package_list仅支持传入一个，package_list仅支持传入一个，items可以传入多个。
微商城暂不支持多商品拆分多运单部分发货的场景
部分发货标准能力目前还不完善，目前仅支持大客定制商家接入使用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.dc.operate.orderpartsend/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.dc.operate.orderpartsend/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.dc.operate.orderpartsend/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/5031)*