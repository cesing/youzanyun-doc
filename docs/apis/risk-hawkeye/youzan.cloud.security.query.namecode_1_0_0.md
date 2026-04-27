---
apiName: "youzan.cloud.security.query.namecode.1.0.0"
version: "1.0.0"
appName: "risk-hawkeye"
apiGroup: "会员与客户"
method: "matchByPhoneOrBuyerId"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4126"
---

# youzan.cloud.security.query.namecode.1.0.0

> **所属分组**: 会员与客户  **所属应用**: risk-hawkeye

---

## 1. 场景说明

根据手机号和买家用户id判断是否在有赞用户风控黑名单中，用于判断买家是否是羊毛党等风险用户。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cloud.security.query.namecode/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.security.query.namecode/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cloud.security.query.namecode/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4126)*