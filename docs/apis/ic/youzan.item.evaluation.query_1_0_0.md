---
apiName: "youzan.item.evaluation.query.1.0.0"
version: "1.0.0"
appName: "ic"
apiGroup: "其它"
method: "queryEvaluationComment"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1070"
---

# youzan.item.evaluation.query.1.0.0

> **所属分组**: 其它  **所属应用**: ic

---

## 1. 场景说明

商品评价和评论，复合条件查询接口。支持普通商品、分销商品、海淘商品、酒店商品、蛋糕烘焙、电子卡券。
1）当start_created没有值时，默认只查询6个月内的评价。2）仅支持查询客户主动评价记录，默认评价的记录不支持查询

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.evaluation.query/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.item.evaluation.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.evaluation.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1070)*