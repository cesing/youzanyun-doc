---
apiName: "youzan.trade.order.update.orderExtend.1.0.0"
version: "1.0.0"
appName: "trade-open"
apiGroup: "交易订单"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3886"
---

# youzan.trade.order.update.orderExtend.1.0.0

> **所属分组**: 交易订单

---

## 1. 场景说明

新增或更新订单扩展字段接口。需要修改订单的扩展字段就传入extras字段。 注：扩展字段当前仅支持SPECIAL_CLOUD_COUNTER_ORDER，如需新增可通过有赞云社区提交新需求。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.order.update.orderExtend/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.order.update.orderExtend/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.order.update.orderExtend/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3886)*