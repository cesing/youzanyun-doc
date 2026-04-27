---
apiName: "youzan.datacenter.goodsSku.data.1.0.0"
version: "1.0.0"
appName: "dc-daemon"
apiGroup: "数据分析"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1044"
---

# youzan.datacenter.goodsSku.data.1.0.0

> **所属分组**: 数据分析

---

## 1. 场景说明

根据商品下的每个sku，通过关联hbase表取出在每一天的成交金额和成交数量。用于报表导出，非实时查询。最大支持31天的查询。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.datacenter.goodsSku.data/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.datacenter.goodsSku.data/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.datacenter.goodsSku.data/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1044)*