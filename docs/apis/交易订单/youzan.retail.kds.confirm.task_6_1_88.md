---
apiName: "youzan.retail.kds.confirm.task.6.1.88"
version: "6.1.88"
appName: "retail-trade-misc"
apiGroup: "交易订单"
authType: "无认证"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4201"
---

# youzan.retail.kds.confirm.task.6.1.88

> **所属分组**: 交易订单

---

## 1. 场景说明

使用场景:外部系统接入有赞订单、商品信息,整合自身kds系统 本接口使用方式: 
1.拉取完kds同步任务之后调用本接口更改对应的同步任务状态,相当于同步成功的回调 
2.如果拉取完不确认,会再次拉取到未确认的同步任务

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.retail.kds.confirm.task/6.1.88`

**认证方式**: 无认证

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
curl -X POST 'https://open.youzanyun.com/api/youzan.retail.kds.confirm.task/6.1.88' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.retail.kds.confirm.task/6.1.88"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4201)*