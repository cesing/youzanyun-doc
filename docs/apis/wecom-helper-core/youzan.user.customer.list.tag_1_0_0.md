---
apiName: "youzan.user.customer.list.tag.1.0.0"
version: "1.0.0"
appName: "wecom-helper-core"
apiGroup: "其它"
method: "pageGroupInfoByKdtId"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4190"
---

# youzan.user.customer.list.tag.1.0.0

> **所属分组**: 其它  **所属应用**: wecom-helper-core

---

## 1. 场景说明

企业微信有一套自己的标签系统，使用企业微信丰富的功能时需要使用企业微信的标签id和标签组id。有赞crm的标签，为了与企业微信的标签互通，会从有赞企微助手拿到crm标签和企业微信标签的映射。该接口提供了店铺维度查询有赞企微助手所有的标签组，标签，以及与crm的标签的映射关系的能力。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.user.customer.list.tag/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.user.customer.list.tag/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.user.customer.list.tag/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4190)*