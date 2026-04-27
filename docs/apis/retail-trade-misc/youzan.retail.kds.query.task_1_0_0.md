---
apiName: "youzan.retail.kds.query.task.1.0.0"
version: "1.0.0"
appName: "retail-trade-misc"
apiGroup: "交易订单"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4175"
---

# youzan.retail.kds.query.task.1.0.0

> **所属分组**: 交易订单

---

## 1. 场景说明

使用场景:外部系统接入有赞订单、商品信息,整合自身kds系统
本接口使用方式:
1.有赞侧先开通kds能力,当前只针对几个特定的店铺开白内测中,后续可支持购买店铺插件获取kds能力
2.针对拥有kds能力的店铺,有赞商品变更以及订单变更的时，会自动构建kds同步任务。可以通过本接口获取对应的kds同步任务中的商品和订单信息

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.retail.kds.query.task/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.retail.kds.query.task/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.retail.kds.query.task/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4175)*