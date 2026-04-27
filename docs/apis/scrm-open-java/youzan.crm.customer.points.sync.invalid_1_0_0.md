---
apiName: "youzan.crm.customer.points.sync.invalid.1.0.0"
version: "1.0.0"
appName: "scrm-open-java"
apiGroup: "营销优惠"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4878"
---

# youzan.crm.customer.points.sync.invalid.1.0.0

> **所属分组**: 营销优惠

---

## 1. 场景说明

回滚积分变更操作。加减积分、同步积分后，如果需要回滚本次操作，使用本API，本API会清除操作幂等key以及回退积分。回退成功后，积分变更消息对应的event_type为120，biz_value为rollback_ + 入参biz_value

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.crm.customer.points.sync.invalid/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.crm.customer.points.sync.invalid/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.crm.customer.points.sync.invalid/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4878)*