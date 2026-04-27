---
apiName: "youzan.bigdata.consumer.text.get.descriptiontext.1.0.0"
version: "1.0.0"
appName: "consumer-datacenter"
apiGroup: "数据分析"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3076"
---

# youzan.bigdata.consumer.text.get.descriptiontext.1.0.0

> **所属分组**: 数据分析

---

## 1. 场景说明

商品文本类接口。输入一个带产品词的query或商品标题，返回一段如诗般优雅的商品描述文案。文案可以用于B端店铺-选择一个商品（点击创建或编辑）在-分享描述中使用。 

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.consumer.text.get.descriptiontext/1.0.0`

**认证方式**: 凭证式

**请求参数**（2 个）:

```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "用户ID",
      "example": "joPykG3E620676084475629568"
    },
    "query": {
      "type": "java.lang.String",
      "description": "查询词，必传",
      "example": "碎花连衣裙"
    }
  },
  "required": [
    "query"
  ]
}
```

**响应参数**（5 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.consumer.api.response.DescriptionTextDTO",
      "description": "调用返回的数据",
      "example": ""
    },
    "description_text": {
      "type": "java.lang.String",
      "description": "描述文案",
      "example": "碎花连衣裙，秋日里的清新小碎花"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true：成功，false：失败。",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "网关返回码描述",
      "example": "successful"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "description_text": "碎花连衣裙，秋日里的清新小碎花",
  "success": "true",
  "code": "200",
  "message": "successful"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.consumer.text.get.descriptiontext/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.consumer.text.get.descriptiontext/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3076)*