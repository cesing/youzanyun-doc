---
apiName: "youzan.cardvoucher.datasync.import.cardcreate.1.0.1"
version: "1.0.1"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "openCard"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3913"
---

# youzan.cardvoucher.datasync.import.cardcreate.1.0.1

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

用于外部储值根据外部卡号，进行开卡

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.1`

**请求参数**（12 个）:

```json
{
  "type": "object",
  "properties": {
    "open": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.request.OpenSyncOpenCardRequest",
      "description": "request",
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
    "client_source": {
      "type": "java.lang.String",
      "description": "请求来源业务方标识，必填",
      "example": "clientSource"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用",
      "example": "LnhGm4rh576452722916618240"
    },
    "out_card_no": {
      "type": "java.lang.String",
      "description": "外部储值卡号，必填",
      "example": "OUT2022111"
    },
    "card_type": {
      "type": "java.lang.String",
      "description": "储值卡类型，不填默认为余额卡，储值卡类型时extra中的卡模板号templateNo，必填1001余额卡，仅支持余额卡",
      "example": "1001"
    },
    "out_biz_no": {
      "type": "java.lang.String",
      "description": "外部系统业务单号，非必填说明：可做幂等等逻辑判断",
      "example": "OUTBIZsss222"
    },
    "open_time": {
      "type": "java.lang.Long",
      "description": "三方卡账单业务发生时间格式：毫秒时间戳",
      "example": "160000000"
    },
    "amount": {
      "type": "java.lang.Long",
      "description": "开卡总金额，单位：分，非必填",
      "example": "0"
    },
    "bonus_amt": {
      "type": "java.lang.Long",
      "description": "开卡赠送金额，单位:分，非必填",
      "example": "0"
    },
    "desc": {
      "type": "java.lang.String",
      "description": "流水描述，非必填",
      "example": "地方的"
    }
  },
  "required": [
    "kdt_id",
    "root_kdt_id",
    "client_source",
    "yz_open_id",
    "out_card_no",
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
      "description": "返回数据",
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
      "example": "ddd1111"
    },
    "extra": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "扩展信息",
      "example": "{\"\"}"
    },
    "success": {
      "type": "boolean",
      "description": "是否成功",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "状态码",
      "example": "0"
    },
    "message": {
      "type": "java.lang.String",
      "description": "错误信息",
      "example": "error"
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
  "card_no": "ddd1111",
  "extra": "{\"\"}",
  "success": "true",
  "code": "0",
  "message": "error"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3913)*