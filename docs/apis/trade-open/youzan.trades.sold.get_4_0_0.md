---
apiName: "youzan.trades.sold.get.4.0.0"
version: "4.0.0"
appName: "trade-open"
apiGroup: "交易订单"
method: "queryNewTradeList"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/157"
---

# youzan.trades.sold.get.4.0.0

> **所属分组**: 交易订单  **所属应用**: trade-open

---

## 1. 场景说明

订单搜索接口
排序规则基于订单创建时间和更新时间。
创建时间可以获取指定时间内所有的订单。
更新时间可以获取最新更新订单，但是范围内订单是动态变化的。
1.只有创建时间start_created和end_created，按创建时间排序
2.只有更新时间start_update和end_update，按更新时间排序
3.同时存在创建时间和更新时间，按更新时间排序
4.如创建或更新时间的开始和结束时间不是成对出现，条件无效

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trades.sold.get/4.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trades.sold.get/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trades.sold.get/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/157)*