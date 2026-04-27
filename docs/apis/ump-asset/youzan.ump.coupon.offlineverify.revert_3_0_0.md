---
apiName: "youzan.ump.coupon.offlineverify.revert.3.0.0"
version: "3.0.0"
appName: "ump-asset"
apiGroup: "营销优惠"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/359"
---

# youzan.ump.coupon.offlineverify.revert.3.0.0

> **所属分组**: 营销优惠

---

## 1. 场景说明

仅支持通过核销接口【youzan.ump.coupon.consume.verify】核销的优惠券/码退还，不支持店铺后台店铺工具核销的优惠券/码退还。同一个优惠活动下多张券/码,仅支持退还最近的一个。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.coupon.offlineverify.revert/3.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.coupon.offlineverify.revert/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.coupon.offlineverify.revert/3.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/359)*