---
apiName: "youzan.trade.order.operate.success.1.0.0"
version: "1.0.0"
appName: "trade-open"
apiGroup: "交易订单"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3980"
---

# youzan.trade.order.operate.success.1.0.0

> **所属分组**: 交易订单

---

## 1. 场景说明

【大客专属，需内部技术添加白名单】订单流转到交易完成，仅支持外部订单导入至有赞系统后将状态同步为交易完成。不可将有赞商城直接生成的交易订单进行状态变更。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.order.operate.success/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.order.operate.success/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.order.operate.success/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3980)*