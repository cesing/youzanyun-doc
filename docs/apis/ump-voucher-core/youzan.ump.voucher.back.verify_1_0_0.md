---
apiName: "youzan.ump.voucher.back.verify.1.0.0"
version: "1.0.0"
appName: "ump-voucher-core"
apiGroup: "营销优惠"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3040"
---

# youzan.ump.voucher.back.verify.1.0.0

> **所属分组**: 营销优惠

---

## 1. 场景说明

外部券核销回流（双中心打通使用）
该接口不走发放核销校验，直接落数据
若该券已经核销，打印warn日志
若该券不存在，直接落数据，打印warn日志
与核销扩展点com.youzan.ump.voucher.core.extpoint.api.extpoint.VoucherVerifyExtPoint配合使用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.voucher.back.verify/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.voucher.back.verify/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.voucher.back.verify/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3040)*