---
apiName: "youzan.cloud.label.add.1.0.0"
version: "1.0.0"
appName: "label-center"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/356"
---

# youzan.cloud.label.add.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

自定义业务标识打标接口支持开发者灵活的自定义业务身份维度，与业务流程配置绑定，对相同流程节点的不同业务逻辑做隔离并实现个性化定制。例如下单页流程中，可以自定义商品A和商品B走不同的下单流程。目前支持开发者自定义商品标识，店铺标识和订单标识。将实体id打上到已申请的标。仅限有容器应用使用，使用方案参考：https://doc.youzanyun.com/resource/solution/27031/28834

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cloud.label.add/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.label.add/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cloud.label.add/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/356)*