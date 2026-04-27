---
apiName: "youzan.trade.refund.search.3.0.1"
version: "3.0.1"
appName: "trade-safeguard"
apiGroup: "交易订单"
method: "refundEsQuery"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3694"
---

# youzan.trade.refund.search.3.0.1

> **所属分组**: 交易订单  **所属应用**: trade-safeguard

---

## 1. 场景说明

查询售后单列表（如果入参没有设置查询时间范围，接口默认查询创建时间为近3个月的订单）

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.refund.search/3.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.refund.search/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.refund.search/3.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3694)*