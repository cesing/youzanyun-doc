---
apiName: "youzan.retail.open.update.localDeliveryStatus.1.0.0"
version: "1.0.0"
appName: "retail-open"
apiGroup: "交易订单"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3390"
---

# youzan.retail.open.update.localDeliveryStatus.1.0.0

> **所属分组**: 交易订单

---

## 1. 场景说明

同城配送订单状态和骑手位置同步，用于商家有自己的配送系统，可以实时回传配送信息到有赞，买家端可以实时看到配送信息和状态，仅针对商家自有配送状态同步至有赞。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.retail.open.update.localDeliveryStatus/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.retail.open.update.localDeliveryStatus/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.retail.open.update.localDeliveryStatus/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3390)*