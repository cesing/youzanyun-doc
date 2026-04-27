---
apiName: "youzan.guide.order.operate.thirdFix.1.0.1"
version: "1.0.1"
appName: "guide-pyxis"
apiGroup: "其它"
method: "fixThirdAchievement"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4798"
---

# youzan.guide.order.operate.thirdFix.1.0.1

> **所属分组**: 其它  **所属应用**: guide-pyxis

---

## 1. 场景说明

面对打通订单数据，因打通过程中出现问题导致的问题数据需要进行修复时，使用此接口进行对应的数据修复。当前接口仅支持开启三方业绩计算，且按照三方规则计算的订单数据修复。注:使用接口前请先找对应负责人申请token，否则接口默认无权限

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.order.operate.thirdFix/1.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.order.operate.thirdFix/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.order.operate.thirdFix/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4798)*