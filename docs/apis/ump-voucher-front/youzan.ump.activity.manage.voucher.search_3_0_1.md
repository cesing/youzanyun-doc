---
apiName: "youzan.ump.activity.manage.voucher.search.3.0.1"
version: "3.0.1"
appName: "ump-voucher-front"
apiGroup: "营销优惠"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2967"
---

# youzan.ump.activity.manage.voucher.search.3.0.1

> **所属分组**: 营销优惠

---

## 1. 场景说明

根据凭证状态查询活动下凭证
凭证状态(全部、生效、已使用、已过期、已失效、未使用), 支持查询代金券，折扣券，兑换券

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.activity.manage.voucher.search/3.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.activity.manage.voucher.search/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.activity.manage.voucher.search/3.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2967)*