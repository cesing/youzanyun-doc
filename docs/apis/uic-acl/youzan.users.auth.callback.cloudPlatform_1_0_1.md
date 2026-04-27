---
apiName: "youzan.users.auth.callback.cloudPlatform.1.0.1"
version: "1.0.1"
appName: "uic-acl"
apiGroup: "会员与客户"
method: "cloudCallback"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4025"
---

# youzan.users.auth.callback.cloudPlatform.1.0.1

> **所属分组**: 会员与客户  **所属应用**: uic-acl

---

## 1. 场景说明

根据传入的openUserId生成平台帐号，并写入登录态。产生授权登录事件，异步创建客户。
仅限platform映射的授权平台为"cloudPlatform"。
本接口仅限内部项目使用，不开放外部申请

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.users.auth.callback.cloudPlatform/1.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.users.auth.callback.cloudPlatform/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.users.auth.callback.cloudPlatform/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4025)*