---
apiName: "youzan.ump.activity.invalid.id.1.0.1"
version: "1.0.1"
appName: "ump-manage-biz"
apiGroup: "营销优惠"
method: "invalidActivity"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3772"
---

# youzan.ump.activity.invalid.id.1.0.1

> **所属分组**: 营销优惠  **所属应用**: ump-manage-biz

---

## 1. 场景说明

通用的活动失效接口，支持内部活动失效，支持外部自定义活动失效。注意，该活动失效后将无法恢复，网店创建的活动只能被当前网店所失效。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.activity.invalid.id/1.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.activity.invalid.id/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.activity.invalid.id/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3772)*