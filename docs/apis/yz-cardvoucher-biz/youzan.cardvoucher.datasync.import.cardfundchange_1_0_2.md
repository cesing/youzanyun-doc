---
apiName: "youzan.cardvoucher.datasync.import.cardfundchange.1.0.2"
version: "1.0.2"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "syncCardFundChange"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3990"
---

# youzan.cardvoucher.datasync.import.cardfundchange.1.0.2

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

接入前请阅读调用注意事项：https://doc.youzanyun.com/resource/doc/3404/5593
本接口需配合
youzan.cardvoucher.datasync.import.cardfundchangeresultquery进行同步结果查询使用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.2`

**请求参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，为发生交易的门网店",
      "example": "60102804"
    },
    "root_kdt_id": {
      "type": "java.lang.Long",
      "description": "总部店铺id",
      "example": "60102626"
    },
    "out_uniq_water_no": {
      "type": "java.lang.String",
      "description": "外部系统储值卡流水号，必填。说明：储值卡流水的唯一标识,如请求明确失败重试需换单号",
      "example": "HBYTESTIMPORT0103"
    },
    "client_source": {
      "type": "java.lang.String",
      "description": "请求来源业务方标识，必填，比如烘焙云：HONGBEIYUN",
      "example": "open"
    },
    "user_info": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.request.OpenSyncCardFundChangeRequest.UserInfoDTO",
      "description": "用户信息",
      "example": ""
    },
    "mobile_no": {
      "type": "java.lang.String",
      "description": "手机号",
      "example": "13186972611"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "用户id",
      "example": "7j3Gi1UH732330877366837248"
    },
    "user_name": {
      "type": "java.lang.String",
      "description": "用户名称",
      "example": "木七"
    },
    "user_nick_name": {
      "type": "java.lang.String",
      "description": "用户昵称",
      "example": "木七"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "卡号，必填",
      "example": "1234567891271"
    },
    "card_type": {
      "type": "java.lang.String",
      "description": "卡类型：1001储值余额卡 1002 储值卡(即礼品卡) 默认为余额卡",
      "example": "1001"
    }
  },
  "required": [
    "kdt_id",
    "root_kdt_id",
    "out_uniq_water_no",
    "client_source",
    "user_info",
    "yz_open_id",
    "card_no",
    "card_type"
  ]
}
```

**响应参数**（10 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenSyncCardFundChangeResultDTO",
      "description": "同步储值卡资金变动流水信息至有赞接口响应参数",
      "example": ""
    },
    "extra": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "扩展信息",
      "example": "{\"\":\"\"}"
    },
    "process_status": {
      "type": "java.lang.String",
      "description": "流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败",
      "example": "SUCCESS"
    },
    "fail_reason": {
      "type": "java.lang.String",
      "description": "处理失败原因",
      "example": "开卡失败，本流水仅允许充值类型开卡"
    },
    "root_kdt_id": {
      "type": "java.lang.Long",
      "description": "总部kdtid",
      "example": "60102626"
    },
    "out_water_no": {
      "type": "java.lang.String",
      "description": "外部系统储值卡唯一流水号",
      "example": "HBYTESTIMPORT0103"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "卡号",
      "example": "1234567891271"
    },
    "success": {
      "type": "boolean",
      "description": "true",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "180001",
      "example": "001"
    },
    "message": {
      "type": "java.lang.String",
      "description": "SUCCESS",
      "example": "success"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "extra": "{\"\":\"\"}",
  "process_status": "SUCCESS",
  "fail_reason": "开卡失败，本流水仅允许充值类型开卡",
  "root_kdt_id": "60102626",
  "out_water_no": "HBYTESTIMPORT0103",
  "card_no": "1234567891271",
  "success": "true"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.2"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3990)*