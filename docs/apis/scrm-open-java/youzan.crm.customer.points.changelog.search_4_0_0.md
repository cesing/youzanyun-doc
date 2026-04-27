---
apiName: "youzan.crm.customer.points.changelog.search.4.0.0"
version: "4.0.0"
appName: "scrm-open-java"
apiGroup: "营销优惠"
method: "getPointsLog"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/885"
---

# youzan.crm.customer.points.changelog.search.4.0.0

> **所属分组**: 营销优惠  **所属应用**: scrm-open-java

---

## 1. 场景说明

查询用户接口操作积分日志，不支持查询所有来源积分日志，日志按照单应用维度查询，应用仅支持查询自己操作的积分记录。例如：A应用调用开放接口变更的积分，不支持使用B应用查询其积分日志。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.crm.customer.points.changelog.search/4.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.crm.customer.points.changelog.search/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.crm.customer.points.changelog.search/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/885)*