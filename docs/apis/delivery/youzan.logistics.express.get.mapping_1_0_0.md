---
apiName: "youzan.logistics.express.get.mapping.1.0.0"
version: "1.0.0"
appName: "delivery"
apiGroup: "物流配送"
method: "getExpressMappingsByQueryType"
timeout: 5000
authType: "无认证"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3463"
---

# youzan.logistics.express.get.mapping.1.0.0

> **所属分组**: 物流配送  **所属应用**: delivery

---

## 1. 场景说明

查询有赞与外部渠道的快递id映射关系，用于将快递公司在有赞的id转化成外部id或者将快递公司在外部的id转化成有赞id

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.logistics.express.get.mapping/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.logistics.express.get.mapping/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.logistics.express.get.mapping/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3463)*