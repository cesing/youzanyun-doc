---
apiName: "youzan.bifrost.service.security.code.validate.1.0.0"
version: "1.0.0"
appName: "test"
apiGroup: "大客CRM"
method: "validate"
timeout: 5000
authType: "无认证"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1071"
---

# youzan.bifrost.service.security.code.validate.1.0.0

> **所属分组**: 大客CRM  **所属应用**: test

---

## 1. 场景说明

校验app开店安全码

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bifrost.service.security.code.validate/1.0.0`

**请求参数**（5 个）:

```json
{
  "type": "object",
  "properties": {
    "client_id": {
      "type": "java.lang.String",
      "description": "应用的client_id",
      "example": "2"
    },
    "type": {
      "type": "java.lang.Integer",
      "description": "-1:未知,1:安卓,2:IOS",
      "example": "2"
    },
    "unique_key": {
      "type": "java.lang.String",
      "description": "唯一标示",
      "example": "2"
    },
    "security_code": {
      "type": "java.lang.String",
      "description": "安全码,安卓为SHA1,IOS为BundleID",
      "example": "2"
    },
    "extra_code": {
      "type": "java.lang.String",
      "description": "扩展编码,安卓为包名,IOS暂无",
      "example": "2"
    }
  },
  "required": [
    "client_id",
    "type",
    "unique_key",
    "security_code"
  ]
}
```

**响应参数**（7 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.lang.Void",
      "description": "",
      "example": "2"
    },
    "success": {
      "type": "boolean",
      "description": "",
      "example": "2"
    },
    "code": {
      "type": "int",
      "description": "",
      "example": "2"
    },
    "message": {
      "type": "java.lang.String",
      "description": "",
      "example": "2"
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "",
      "example": "3"
    },
    "error_data": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "",
      "example": "2"
    },
    "test": {
      "type": "int",
      "description": "",
      "example": "2"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "2",
  "success": "2",
  "code": "2",
  "message": "2",
  "request_id": "3",
  "error_data": "2",
  "test": "2"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bifrost.service.security.code.validate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bifrost.service.security.code.validate/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1071)*