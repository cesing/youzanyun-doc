---
apiName: "youzan.ump.memberprice.batch.update.4.0.0"
version: "4.0.0"
appName: "marketing"
apiGroup: "营销优惠"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1185"
---

# youzan.ump.memberprice.batch.update.4.0.0

> **所属分组**: 营销优惠

---

## 1. 场景说明

批量修改（创建）商品SKU级别的自定义会员价，支持权益卡和等级维度的设置，前提是商家设置了权益卡或者开启了会员等级；该接口限制每次批量设置商品的上限是15个商品，每个商品最多只能保存600个自定义售价设置。接口请求传值正确示例：{"item_customer_discount_d_t_o_s":[{"definitions":[{"bind_alias":"Y27xxxxxx9vjeip","bind_type":2,"discount_type":3,"discount_value":80,"sku_id":371xxx30}],"item_id":89xxxx357}]}

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.memberprice.batch.update/4.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.memberprice.batch.update/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.memberprice.batch.update/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1185)*