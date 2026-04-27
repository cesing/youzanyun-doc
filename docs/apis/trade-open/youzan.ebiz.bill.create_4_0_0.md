---
apiName: "youzan.ebiz.bill.create.4.0.0"
version: "4.0.0"
appName: "trade-open"
apiGroup: "分销与供货"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/958"
---

# youzan.ebiz.bill.create.4.0.0

> **所属分组**: 分销与供货

---

## 1. 场景说明

生成分销买家单，并使用店铺余额支付采购单货款。仅限大客定制商家使用。如需使用该接口需要评估是否属于分销业务场景，如不属于则无需使用该接口。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ebiz.bill.create/4.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ebiz.bill.create/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ebiz.bill.create/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/958)*