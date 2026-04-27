---
apiName: "youzan.scrm.order.trade.out.create.1.0.0"
version: "1.0.0"
appName: "scrm-open-java"
apiGroup: "交易订单"
method: "orderCreate"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4346"
---

# youzan.scrm.order.trade.out.create.1.0.0

> **所属分组**: 交易订单  **所属应用**: scrm-open-java

---

## 1. 场景说明

区别外部开单接口，更加适用于CRM的订单导入，两者参数保持一致，如果有需求可以直接切换。接口仅支持指定合作方使用，自营商家使用需购买大客定制套餐服务或有赞CRM。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.scrm.order.trade.out.create/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.scrm.order.trade.out.create/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.scrm.order.trade.out.create/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4346)*