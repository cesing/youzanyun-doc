---
apiName: "youzan.mei.custom.pay.operate.4.0.0"
version: "4.0.0"
appName: "mei-open"
apiGroup: "美业"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3679"
---

# youzan.mei.custom.pay.operate.4.0.0

> **所属分组**: 美业

---

## 1. 场景说明

自定义支付订单接口，支持通过标记现金支付，及自定义记账方式支付
注意：该接口仅完成订单的标记支付，无法完成钱款收取，请在调用接口标记订单支付完成后，通过其他渠道完成钱款收取，因错误理解和使用该接口导致的资金损失，有赞概不负责。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.mei.custom.pay.operate/4.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.mei.custom.pay.operate/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.mei.custom.pay.operate/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3679)*