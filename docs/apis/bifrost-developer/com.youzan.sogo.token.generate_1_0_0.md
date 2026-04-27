---
apiName: "com.youzan.sogo.token.generate.1.0.0"
version: "1.0.0"
appName: "bifrost-developer"
apiGroup: "其它"
authType: "无认证"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/759"
---

# com.youzan.sogo.token.generate.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

搜狗输入法回调方法生成token

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/com.youzan.sogo.token.generate/1.0.0`

**认证方式**: 无认证

**请求参数**（1 个）:

```json
{
  "type": "object",
  "properties": {
    "code": {
      "type": "java.lang.String",
      "description": "",
      "example": ""
    }
  },
  "required": [
    "code"
  ]
}
```

**响应参数**（6 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.lang.Void",
      "description": "",
      "example": ""
    },
    "success": {
      "type": "boolean",
      "description": "",
      "example": ""
    },
    "code": {
      "type": "int",
      "description": "",
      "example": ""
    },
    "message": {
      "type": "java.lang.String",
      "description": "",
      "example": ""
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "",
      "example": ""
    },
    "error_data": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "",
      "example": ""
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "success": "",
  "code": "",
  "message": "",
  "request_id": "",
  "error_data": ""
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/com.youzan.sogo.token.generate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/com.youzan.sogo.token.generate/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/759)*