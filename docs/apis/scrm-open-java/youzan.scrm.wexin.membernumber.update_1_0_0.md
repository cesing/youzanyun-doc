---
apiName: "youzan.scrm.wexin.membernumber.update.1.0.0"
version: "1.0.0"
appName: "scrm-open-java"
apiGroup: "会员与客户"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4492"
---

# youzan.scrm.wexin.membernumber.update.1.0.0

> **所属分组**: 会员与客户

---

## 1. 场景说明

如果线下三方系统的会员卡号发生了变更，可以使用这个接口来修改微信会员卡号。
适用场景：使用会员&CRM的商家，期望将三方系统中的会员卡号覆盖微信会员卡号。
例如：三方POS扫码微信会员卡识别三方会员场景

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.scrm.wexin.membernumber.update/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.scrm.wexin.membernumber.update/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.scrm.wexin.membernumber.update/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4492)*