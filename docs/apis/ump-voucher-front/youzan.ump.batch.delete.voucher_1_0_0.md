---
apiName: "youzan.ump.batch.delete.voucher.1.0.0"
version: "1.0.0"
appName: "ump-voucher-front"
apiGroup: "营销优惠"
method: "deleteUserVouchers"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4433"
---

# youzan.ump.batch.delete.voucher.1.0.0

> **所属分组**: 营销优惠  **所属应用**: ump-voucher-front

---

## 1. 场景说明

批量删除用户拥有的全部优惠券。
注意：
1、单次只能删除 200 张，当用户拥有超出200张优惠券的场景，需要上游循环调用本接口完成删除，搭配youzan.ump.promocard.buyer.search 接口查询判断是否完成删除，延迟1秒。
2、本批量删除接口，不会触发优惠券相关消息。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.batch.delete.voucher/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.batch.delete.voucher/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.batch.delete.voucher/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4433)*