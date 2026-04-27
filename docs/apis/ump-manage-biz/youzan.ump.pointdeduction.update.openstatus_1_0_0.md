---
apiName: "youzan.ump.pointdeduction.update.openstatus.1.0.0"
version: "1.0.0"
appName: "ump-manage-biz"
apiGroup: "营销优惠"
method: "openRule"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4174"
---

# youzan.ump.pointdeduction.update.openstatus.1.0.0

> **所属分组**: 营销优惠  **所属应用**: ump-manage-biz

---

## 1. 场景说明

开启/关闭积分抵现规则。该接口只会更改规则的开启状态，调用前需在店铺后台配置好规则。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.pointdeduction.update.openstatus/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.pointdeduction.update.openstatus/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.pointdeduction.update.openstatus/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4174)*