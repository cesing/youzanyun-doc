---
apiName: "youzan.trade.virtualticket.third.cover.3.0.1"
version: "3.0.1"
appName: "trade-open"
apiGroup: "trading_setting_advanced"
method: "batchCoverTicketStatus"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/564"
---

# youzan.trade.virtualticket.third.cover.3.0.1

> **所属分组**: trading_setting_advanced  **所属应用**: trade-open

---

## 1. 场景说明

电子卡券外部卡券状态同步请开发者根据实际订单下单店铺的ID进行获取token后调用本接口(该接口只会同步卡券状态，不会联动处理订单状态，如果期望卡券核销完成可以同时推进订单状态，需要请调用核销接口：youzan.trade.virtualticket.third.batch.verify)

（废弃，不推荐新增使用，建议使用各个状态推进的对应接口）

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.virtualticket.third.cover/3.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.virtualticket.third.cover/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.virtualticket.third.cover/3.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/564)*