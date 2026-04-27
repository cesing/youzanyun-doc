---
apiName: "youzan.salesman.shoppingguide.get.Info.1.0.0"
version: "1.0.0"
appName: "retail-sales"
apiGroup: "分销与供货"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2779"
---

# youzan.salesman.shoppingguide.get.Info.1.0.0

> **所属分组**: 分销与供货

---

## 1. 场景说明

根据导购员订单号查询导购员信息；（客户跟店铺A的导购员A有专属关系，客户在门店B通过导购员B进行下单，此时门店B产生的订单会有两笔业绩，分别是导购员A的专属业绩和导购员B的销售业绩，这时候会返回两个手机号）,本接口仅支持导购助手之后的版本.

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.salesman.shoppingguide.get.Info/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.salesman.shoppingguide.get.Info/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.salesman.shoppingguide.get.Info/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2779)*