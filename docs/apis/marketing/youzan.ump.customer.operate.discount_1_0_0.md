---
apiName: "youzan.ump.customer.operate.discount.1.0.0"
version: "1.0.0"
appName: "marketing"
apiGroup: "营销优惠"
method: "operationCustomerDiscount"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4094"
---

# youzan.ump.customer.operate.discount.1.0.0

> **所属分组**: 营销优惠  **所属应用**: marketing

---

## 1. 场景说明

单个商品批量修改（创建）SKU级别的自定义会员价，支持权益卡和会员等级维度的设置，前提是商家设置了权益卡或者开启了会员等级；
该接口会对商品下所有sku数据进行全量更新，若没传某个sku会员价，则代表清空，可通过youzan.ump.memberprice.query.3.0.0获取该商品的自定义会员价信息。
该接口限制每次最多只能保存600个自定义售价设置；该接口支持所有版本会员价修改；
失败场景下，可能存在部分sku修改成功，部分sku修改失败；

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.customer.operate.discount/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.customer.operate.discount/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.customer.operate.discount/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4094)*