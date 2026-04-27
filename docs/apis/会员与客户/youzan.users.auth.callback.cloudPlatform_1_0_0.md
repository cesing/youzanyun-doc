---
apiName: "youzan.users.auth.callback.cloudPlatform.1.0.0"
version: "1.0.0"
appName: "uic-acl"
apiGroup: "会员与客户"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3809"
---

# youzan.users.auth.callback.cloudPlatform.1.0.0

> **所属分组**: 会员与客户

---

## 1. 场景说明

有赞云商家平台授权登录，根据传入的openUserId生成平台帐号，并写入登录态。产生授权登录事件，异步创建客户。
仅限platform映射的授权平台为"cloudPlatform"。
适用于农夫山泉的农行渠道、建行渠道等

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.users.auth.callback.cloudPlatform/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.users.auth.callback.cloudPlatform/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.users.auth.callback.cloudPlatform/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3809)*