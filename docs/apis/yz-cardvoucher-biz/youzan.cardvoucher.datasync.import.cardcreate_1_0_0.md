---
apiName: "youzan.cardvoucher.datasync.import.cardcreate.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3908"
---

# youzan.cardvoucher.datasync.import.cardcreate.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

供储值卡外部开卡

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.0`

**认证方式**: 凭证式

**请求参数**（12 个）:

```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.request.OpenSyncCardFundChangeRequest",
      "description": "入参request",
      "example": ""
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "60102804"
    },
    "root_kdt_id": {
      "type": "java.lang.Long",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "60102626"
    },
    "out_uniq_water_no": {
      "type": "java.lang.String",
      "description": "外部系统储值卡流水号，必填说明：储值卡流水的唯一标识",
      "example": "HBYTESTIMPORT0103"
    },
    "client_source": {
      "type": "java.lang.String",
      "description": "请求来源业务方标识，必填",
      "example": "open"
    },
    "user_info": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.request.OpenSyncCardFundChangeRequest.UserInfoDTO",
      "description": "用户信息，必填",
      "example": ""
    },
    "mobile_no": {
      "type": "java.lang.String",
      "description": "手机号",
      "example": "13186972611"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "有赞用户id因开放网关审核要求，必须命名为yzOpenUid，但实际赋值为yzUid",
      "example": "7j3Gi1UH732330877366837248"
    },
    "user_name": {
      "type": "java.lang.String",
      "description": "用户姓名",
      "example": "木七"
    },
    "user_nick_name": {
      "type": "java.lang.String",
      "description": "用户昵称",
      "example": "木七"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "储值卡号，必填",
      "example": "1234567891271"
    },
    "card_type": {
      "type": "java.lang.String",
      "description": "储值卡类型，不填默认为余额卡，储值卡类型时extra中的卡模板号templateNo必填1001余额卡1002储值卡",
      "example": "1001"
    }
  },
  "required": [
    "request",
    "kdt_id",
    "root_kdt_id",
    "out_uniq_water_no",
    "client_source",
    "user_info",
    "mobile_no",
    "yz_open_id",
    "user_name",
    "user_nick_name",
    "card_no",
    "card_type"
  ]
}
```

**响应参数**（8 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenSyncCardFundChangeResultDTO",
      "description": "返回信息",
      "example": ""
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "root_kdt_id": {
      "type": "java.lang.Long",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "储值卡号",
      "example": "ddddd"
    },
    "extra": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "扩展信息",
      "example": "{\"\":\"\"}"
    },
    "success": {
      "type": "boolean",
      "description": "是否成功",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "错误码",
      "example": "1"
    },
    "message": {
      "type": "java.lang.String",
      "description": "错误信息",
      "example": "sss"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "kdt_id": "88888",
  "root_kdt_id": "232423",
  "card_no": "ddddd",
  "extra": "{\"\":\"\"}",
  "success": "true",
  "code": "1",
  "message": "sss"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3908)*