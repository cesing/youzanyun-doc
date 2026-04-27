---
apiName: "youzan.mei.promoter.customer.bind.3.0.0"
version: "3.0.0"
appName: "mei-open"
apiGroup: "美业"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/496"
---

# youzan.mei.promoter.customer.bind.3.0.0

> **所属分组**: 美业

---

## 1. 场景说明

将一批顾客绑定到某个推广员下面.例如手机号为18999999999的客户为推广员,现在要将18988888888,18977777777两个顾客绑定成他的客户,那么18988888888,18977777777这两个客户在购买店铺的推广商品的时候18999999999这个推广员将获得收益

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.mei.promoter.customer.bind/3.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.mei.promoter.customer.bind/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.mei.promoter.customer.bind/3.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/496)*