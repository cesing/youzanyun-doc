---
apiName: "youzan.datacenter.datastandard.team.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "数据分析"
method: "teamCommonDataService"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/924"
---

# youzan.datacenter.datastandard.team.1.0.0

> **所属分组**: 数据分析  **所属应用**: seller-datacenter

---

## 1. 场景说明

1.订单相关指标（如下单人数）以下单时间统计，支付相关指标（如支付人数）以支付成功时间统计（拼团订单成团算支付、货到付款订单发货算支付）。订单查询页面根据下单时间查询对应订单。若顾客当日下单、次日支付，则下单与支付数据会有一天时间差，请注意区分。
2.由于是离线数据，建议每天早晨9：00后再请求。
3.支持查询最近90天的数据

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.datacenter.datastandard.team/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.datacenter.datastandard.team/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.datacenter.datastandard.team/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/924)*