---
apiName: "youzan.trade.virtualticket.third.operate.delay.1.0.0"
version: "1.0.0"
appName: "trade-open"
apiGroup: "其它"
method: "batchDelayTicketVerify"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/5009"
---

# youzan.trade.virtualticket.third.operate.delay.1.0.0

> **所属分组**: 其它  **所属应用**: trade-open

---

## 1. 场景说明

延期订单下的电子卡券，其中目标要延长的结束时间要大于当前卡券的有效时间，否则不会执行真正的更新

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.virtualticket.third.operate.delay/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.virtualticket.third.operate.delay/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.virtualticket.third.operate.delay/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/5009)*