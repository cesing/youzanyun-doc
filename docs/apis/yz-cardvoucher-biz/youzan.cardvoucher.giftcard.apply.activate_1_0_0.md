---
apiName: "youzan.cardvoucher.giftcard.apply.activate.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3706"
---

# youzan.cardvoucher.giftcard.apply.activate.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

储值礼品卡激活接口，（如实现储值卡激活扩展点https://doc.youzanyun.com/detail/EXT/20001可触发扩展点；如礼品卡已经激活会返回成功）

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.apply.activate/1.0.0`

**认证方式**: 凭证式

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "long",
      "description": "有赞用户id，用户在有赞的唯一id。",
      "example": "Kce872bU658955584007081984"
    },
    "card_alias": {
      "type": "java.lang.String",
      "description": "礼品卡别名（扩展点场景无需传入）",
      "example": "3XYALEPnOrAxJiB6DMZ"
    },
    "group_no": {
      "type": "java.lang.String",
      "description": "礼品卡组号",
      "example": "310201391527990"
    }
  },
  "required": [
    "yz_open_id",
    "card_alias",
    "group_no"
  ]
}
```

**响应参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.lang.Boolean",
      "description": "是否激活成功",
      "example": "true"
    },
    "success": {
      "type": "boolean",
      "description": "请求是否成功",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "网关响应码",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "网关响应描述",
      "example": "successful"
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
  "message": "successful"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.apply.activate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.apply.activate/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3706)*