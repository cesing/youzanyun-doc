---
apiName: "youzan.scrm.tag.template.delete.1.0.0"
version: "1.0.0"
appName: "scrm-open-java"
apiGroup: "会员与客户"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1386"
---

# youzan.scrm.tag.template.delete.1.0.0

> **所属分组**: 会员与客户

---

## 1. 场景说明

删除商家标签模板接口，当外部软件需要删除商家下某个标签模板时调用，删除后，原有打上这个标签的相关客户会自动移除。备注：2024年4月，接口下线。新接入开发者请使用youzan.scrm.tag.category.update

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.scrm.tag.template.delete/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.scrm.tag.template.delete/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.scrm.tag.template.delete/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1386)*