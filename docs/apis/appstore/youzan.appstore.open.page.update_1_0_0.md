---
apiName: "youzan.appstore.open.page.update.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "其它"
method: "updateMicroPage"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/358"
---

# youzan.appstore.open.page.update.1.0.0

> **所属分组**: 其它  **所属应用**: appstore

---

## 1. 场景说明

更新模板

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.page.update/1.0.0`

**请求参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "micropage_update_request": {
      "type": "com.youzan.cloud.appstore.api.dto.request.open.MicropageUpdateRequest",
      "description": "",
      "example": ""
    },
    "page_id": {
      "type": "java.lang.Long",
      "description": "页面id",
      "example": ""
    },
    "user_id": {
      "type": "java.lang.Long",
      "description": "用户id",
      "example": ""
    },
    "inner_item_id": {
      "type": "java.lang.Long",
      "description": "内购项id（备用字段，不填）",
      "example": ""
    },
    "out_item_id": {
      "type": "java.lang.String",
      "description": "（内购项）外部商品编码",
      "example": ""
    },
    "page_name": {
      "type": "java.lang.String",
      "description": "页面名称",
      "example": ""
    },
    "page_desc": {
      "type": "java.lang.String",
      "description": "页面描述",
      "example": ""
    },
    "view_url": {
      "type": "java.lang.String",
      "description": "预览地址",
      "example": ""
    },
    "re_edit_url": {
      "type": "java.lang.String",
      "description": "重编辑地址",
      "example": ""
    },
    "category_id": {
      "type": "java.lang.Long",
      "description": "页面分类(非必填)",
      "example": ""
    }
  },
  "required": [
    "micropage_update_request",
    "page_id",
    "user_id",
    "out_item_id"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.cloud.appstore.api.dto.response.open.MicroPageResponse",
      "description": "",
      "example": ""
    },
    "id": {
      "type": "java.lang.Long",
      "description": "",
      "example": ""
    },
    "page_id": {
      "type": "java.lang.Long",
      "description": "页面id",
      "example": ""
    },
    "inner_item_id": {
      "type": "java.lang.Long",
      "description": "内购项id(模板id)",
      "example": ""
    },
    "page_name": {
      "type": "java.lang.String",
      "description": "页面名称",
      "example": ""
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺id",
      "example": ""
    },
    "user_id": {
      "type": "java.lang.Long",
      "description": "用户id",
      "example": ""
    },
    "view_url": {
      "type": "java.lang.String",
      "description": "预览地址",
      "example": ""
    },
    "re_edit_url": {
      "type": "java.lang.String",
      "description": "编辑地址",
      "example": ""
    },
    "category_id": {
      "type": "java.lang.Long",
      "description": "分类id",
      "example": ""
    },
    "page_desc": {
      "type": "java.lang.String",
      "description": "页面描述",
      "example": ""
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "id": "",
  "page_id": "",
  "inner_item_id": "",
  "page_name": "",
  "kdt_id": "",
  "user_id": "",
  "view_url": ""
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.open.page.update/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.appstore.open.page.update/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/358)*