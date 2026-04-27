---
apiName: "youzan.ump.thirdpartyactivity.create.1.0.2"
version: "1.0.2"
appName: "ump-voucher-front"
apiGroup: "营销优惠"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4762"
---

# youzan.ump.thirdpartyactivity.create.1.0.2

> **所属分组**: 营销优惠

---

## 1. 场景说明

三方券活动创建。
目前默认商家 三方券+有赞券 活动上限2000个，所以开发者对接三方券创建接口时，需要再同时对接三方券删除接口，避免后续券达到上限不能再创建。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.thirdpartyactivity.create/1.0.2`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.thirdpartyactivity.create/1.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.thirdpartyactivity.create/1.0.2"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4762)*