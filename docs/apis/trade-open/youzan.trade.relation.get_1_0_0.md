---
apiName: "youzan.trade.relation.get.1.0.0"
version: "1.0.0"
appName: "trade-open"
apiGroup: "交易订单"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2963"
---

# youzan.trade.relation.get.1.0.0

> **所属分组**: 交易订单

---

## 1. 场景说明

使用场景：
1.同一个店铺分销商品和普通商品一起下单
2.同一个店铺虚拟商品和普通商品一起下单
3.同一个店铺不同的分销商的商品一起下单生成vid，该vid字段接口需要配合下单储值卡支付扩展点使用
4.保税跨境达到金额阈值后拆单
V单获取来源：youzan.trade.get.4.0.2接口中的orders_combine_id字段

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trade.relation.get/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.relation.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trade.relation.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2963)*