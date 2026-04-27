---
apiName: "youzan.logistics.takeout.fengniaoauthorize.update.authorization.1.0.0"
version: "1.0.0"
appName: "delivery"
apiGroup: "物流配送"
method: "fengniaoAuthorizeCallback"
timeout: 5000
authType: "无认证"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2793"
---

# youzan.logistics.takeout.fengniaoauthorize.update.authorization.1.0.0

> **所属分组**: 物流配送  **所属应用**: delivery

---

## 1. 场景说明

自结算授权回调接口-仅限蜂鸟合作方使用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.logistics.takeout.fengniaoauthorize.update.authorization/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.logistics.takeout.fengniaoauthorize.update.authorization/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.logistics.takeout.fengniaoauthorize.update.authorization/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2793)*