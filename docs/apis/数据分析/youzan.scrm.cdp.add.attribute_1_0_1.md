---
apiName: "youzan.scrm.cdp.add.attribute.1.0.1"
version: "1.0.1"
appName: "cdp-data-integration"
apiGroup: "数据分析"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4858"
---

# youzan.scrm.cdp.add.attribute.1.0.1

> **所属分组**: 数据分析

---

## 1. 场景说明

CRM产品为商家自研提供对用户自定义属性的接入能力，需要提前在有赞侧登记用户自定义属性组和属性的元数据，之后通过这个接口可以创建自定义属性可用的筛选项，用于CRM客户分群筛选。【仅限指定合作伙伴使用】

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.scrm.cdp.add.attribute/1.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.scrm.cdp.add.attribute/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.scrm.cdp.add.attribute/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4858)*