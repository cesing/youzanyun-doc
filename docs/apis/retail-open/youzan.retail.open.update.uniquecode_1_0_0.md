---
apiName: "youzan.retail.open.update.uniquecode.1.0.0"
version: "1.0.0"
appName: "retail-open"
apiGroup: "零售门店"
method: "replaceUniqueCode"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4888"
---

# youzan.retail.open.update.uniquecode.1.0.0

> **所属分组**: 零售门店  **所属应用**: retail-open

---

## 1. 场景说明

使用场景：商家唯一码管理中存在唯一码录入到错误sku，想重新使用该唯一码录入到正确商品上。需要更改系统中此唯一码，然后重新录入此唯一码。
注意：
  要替换的唯一码状态仅支持采购退货、已报损、已作废状态

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.retail.open.update.uniquecode/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.retail.open.update.uniquecode/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.retail.open.update.uniquecode/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4888)*