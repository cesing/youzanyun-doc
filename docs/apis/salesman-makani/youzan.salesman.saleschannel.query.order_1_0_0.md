---
apiName: "youzan.salesman.saleschannel.query.order.1.0.0"
version: "1.0.0"
appName: "salesman-makani"
apiGroup: "分销与供货"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3186"
---

# youzan.salesman.saleschannel.query.order.1.0.0

> **所属分组**: 分销与供货

---

## 1. 场景说明

该API是提供给渠道商查询分佣的订单使用
备注：渠道商是一种销售员的高级身份其来源于云分销业务。当商家在分销员的基础上购买云分销插件后会提供代理商和订货商两种角色的团队分销能力，这两种角色也统称为渠道商；订购地址：https://yingyong.youzan.com/cloud-app-detail/78764

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.salesman.saleschannel.query.order/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.salesman.saleschannel.query.order/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.salesman.saleschannel.query.order/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3186)*