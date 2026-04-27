---
apiName: "youzan.ump.timelimitdiscount.set.invalid.1.0.0"
version: "1.0.0"
appName: "ump-manage"
apiGroup: "营销优惠"
method: "invalidActivity"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2199"
---

# youzan.ump.timelimitdiscount.set.invalid.1.0.0

> **所属分组**: 营销优惠  **所属应用**: ump-manage

---

## 1. 场景说明

失效限时折扣活动，注意：该活动失效后将无法恢复。有赞连锁总部仅支持操作总部发布的限时折扣，有赞网店仅支持操作网店发布的限时折扣。备注：2024年5月，接口下线。新接入开发者请使用youzan.ump.activity.invalid.id

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.timelimitdiscount.set.invalid/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.timelimitdiscount.set.invalid/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.timelimitdiscount.set.invalid/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2199)*