---
apiName: "youzan.salesman.cps.create.1.0.0"
version: "1.0.0"
appName: "java-salesman-web"
apiGroup: "分销与供货"
method: "setGoodsShareAndCommission"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2546"
---

# youzan.salesman.cps.create.1.0.0

> **所属分组**: 分销与供货  **所属应用**: java-salesman-web

---

## 1. 场景说明

（接口已下线，请使用替代接口【youzan.salesman.customers.set】）设置商品是否可推广和佣金比例API，佣金比例对象非必传字段，分佣金比例和邀请佣金比例，都传递了会使用自定义佣金比例，都没有传递会使用店铺默认的佣金比例；佣金比例传递，邀请佣金比例没有传递，邀请佣金比例也会使用默认的，反之也是一样

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.salesman.cps.create/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.salesman.cps.create/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.salesman.cps.create/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2546)*