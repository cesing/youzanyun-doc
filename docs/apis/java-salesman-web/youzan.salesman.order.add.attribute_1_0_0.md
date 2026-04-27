---
apiName: "youzan.salesman.order.add.attribute.1.0.0"
version: "1.0.0"
appName: "java-salesman-web"
apiGroup: "分销与供货"
method: "orderAttribute"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4197"
---

# youzan.salesman.order.add.attribute.1.0.0

> **所属分组**: 分销与供货  **所属应用**: java-salesman-web

---

## 1. 场景说明

将归因结果为不归因的订单归因给指定分销员，未开放给所有商家，需要对接请先联系对应的服务运营。
风险提示：改变分销员归因结果，会影响导购分佣计算，如果商家设置了导购与分销员佣金冲突的话，会有导购与分销员同时计算佣金的可能，导致导购多分提成出去，需要与技术人员确认使用场景。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.salesman.order.add.attribute/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.salesman.order.add.attribute/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.salesman.order.add.attribute/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4197)*