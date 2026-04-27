---
apiName: "youzan.cardvoucher.giftcard.group.upimgname.3.0.0"
version: "3.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/368"
---

# youzan.cardvoucher.giftcard.group.upimgname.3.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

根据卡号修改礼品卡图片、卡名称

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.group.upimgname/3.0.0`

**认证方式**: 凭证式

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "com.youzan.pay.cardvoucher.biz.api.giftcard.request.UpdateCardGroupCoverUrlRequest",
      "description": "",
      "example": ""
    },
    "group_no": {
      "type": "java.lang.String",
      "description": "卡号，必填",
      "example": "310100029297523"
    },
    "cover_url": {
      "type": "java.lang.String",
      "description": "卡片图片链接，与卡片名称字段二选一必传",
      "example": "https://b.yzcdn.cn/assets/static/weapp/prepaid/card_bg.png"
    },
    "name": {
      "type": "java.lang.String",
      "description": "卡片名称，与卡片图片链接字段二选一必传",
      "example": "万物本草储值卡"
    }
  },
  "required": [
    "group_no"
  ]
}
```

**响应参数**（6 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.lang.Boolean",
      "description": "更新是否成功，true成功，false失败",
      "example": "true"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "网关返回码，表示本次请求是否成功。200 :成功",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "网关返回码描述",
      "example": "successful"
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
  "data": "true",
  "success": "true",
  "code": "200",
  "message": "successful",
  "request_id": "",
  "error_data": ""
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.group.upimgname/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.group.upimgname/3.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/368)*