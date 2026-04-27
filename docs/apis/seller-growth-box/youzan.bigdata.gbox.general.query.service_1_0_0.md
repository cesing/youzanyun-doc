---
apiName: "youzan.bigdata.gbox.general.query.service.1.0.0"
version: "1.0.0"
appName: "seller-growth-box"
apiGroup: "大客CRM"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1557"
---

# youzan.bigdata.gbox.general.query.service.1.0.0

> **所属分组**: 大客CRM

---

## 1. 场景说明

增长工具箱专用接口，只用于增长工具箱应用。
返回结构为有赞common组件，PlainResult, ListResult等，data为各个实际接口返回的数据，实际接口同入参的serviceName保持一致。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.gbox.general.query.service/1.0.0`

**认证方式**: 凭证式

**请求参数**（6 个）:

```json
{
  "type": "object",
  "properties": {
    "general_param": {
      "type": "com.youzan.bigdata.seller.growth.box.api.GeneralParam",
      "description": "服务请求映射",
      "example": ""
    },
    "service": {
      "type": "java.lang.String",
      "description": "服务名",
      "example": "com.youzan.bigdata.seller.growth.box.api.service.darwin.ArticleService"
    },
    "method": {
      "type": "java.lang.String",
      "description": "方法名",
      "example": "listArticlePage"
    },
    "params": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "参数列表",
      "example": "{\"articlePageQueryParam\":{\"page\":1, \"pageSize\":10, \"kdtId\": 63077}}"
    },
    "operator_param": {
      "type": "com.youzan.bigdata.seller.growth.box.api.OperatorParam",
      "description": "操作者信息",
      "example": ""
    },
    "user_id": {
      "type": "java.lang.Long",
      "description": "操作用户id",
      "example": "1"
    }
  },
  "required": [
    "service",
    "method",
    "params"
  ]
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
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.gbox.general.query.service/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.gbox.general.query.service/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1557)*