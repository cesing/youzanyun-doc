---
apiName: "youzan.cardvoucher.datasync.import.cardfundchangeresultquery.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3996"
---

# youzan.cardvoucher.datasync.import.cardfundchangeresultquery.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

搭配youzan.cardvoucher.datasync.import.cardfundchange使用；回流接口响应成功后可通过本接口查询结果，通常5s内能返回明确的结果，如果返回的是PROCRSSING处理中，一般是未能正确被处理(比如关联流水还未写入会尝试等待)，内部会进行补偿处理，3次补偿仍未成功当做失败处理，因此建议轮询查询时间间隔为：回流后的2s,回流后的5s,回流后的35s,回流后的65s...后续间隔30s查询一次至明确成功或失败

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchangeresultquery/1.0.0`

**认证方式**: 凭证式

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.request.OpenQuerySyncCardFundChangeRequest",
      "description": "",
      "example": ""
    },
    "root_kdt_id": {
      "type": "java.lang.Long",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "out_uniq_water_no": {
      "type": "java.lang.String",
      "description": "外部系统储值卡流水号，必填说明：储值卡流水的唯一标识",
      "example": "1111"
    }
  },
  "required": [
    "root_kdt_id",
    "out_uniq_water_no"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenQuerySyncCardFundChangeResultDTO",
      "description": "",
      "example": ""
    },
    "process_status": {
      "type": "java.lang.String",
      "description": "流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败",
      "example": "FAIL"
    },
    "extra": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "扩展信息",
      "example": "{\"\":\"\"}"
    },
    "root_kdt_id": {
      "type": "java.lang.Long",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "out_water_no": {
      "type": "java.lang.String",
      "description": "外部唯一流水号",
      "example": "1111"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "储值卡号",
      "example": "aaaaa"
    },
    "fail_reason": {
      "type": "java.lang.String",
      "description": "处理失败原因",
      "example": "开卡失败，本流水仅允许充值类型开卡"
    },
    "success": {
      "type": "boolean",
      "description": "true",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "200",
      "example": "118711202"
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
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "process_status": "FAIL",
  "extra": "{\"\":\"\"}",
  "root_kdt_id": "232423",
  "out_water_no": "1111",
  "card_no": "aaaaa",
  "fail_reason": "开卡失败，本流水仅允许充值类型开卡",
  "success": "true"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchangeresultquery/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchangeresultquery/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3996)*