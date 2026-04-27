---
apiName: "youzan.wecom.statistics.query.groupoverview.1.0.0"
version: "1.0.0"
appName: "wecom-helper-core"
apiGroup: "其它"
method: "getGroupChatOverviewData"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4975"
---

# youzan.wecom.statistics.query.groupoverview.1.0.0

> **所属分组**: 其它  **所属应用**: wecom-helper-core

---

## 1. 场景说明

查询一段时间范围内，企助店铺的社群概况数据
时间范围必须是自然日（例如2025-09-01到2025-09-01）、自然周（例如2025-09-01到2025-09-07）、自然月(例如2025-09-01到2025-09-30)。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.wecom.statistics.query.groupoverview/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.wecom.statistics.query.groupoverview/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.wecom.statistics.query.groupoverview/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4975)*