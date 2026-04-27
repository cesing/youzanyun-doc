---
apiName: "youzan.cardvoucher.datasync.import.cardfundchangeresultquery.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "querySyncCardFundChangeResult"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-02-14"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3996"
---
# youzan.cardvoucher.datasync.import.cardfundchangeresultquery.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
搭配youzan.cardvoucher.datasync.import.cardfundchange使用；回流接口响应成功后可通过本接口查询结果，通常5s内能返回明确的结果，如果返回的是PROCRSSING处理中，一般是未能正确被处理(比如关联流水还未写入会尝试等待)，内部会进行补偿处理，3次补偿仍未成功当做失败处理，因此建议轮询查询时间间隔为：回流后的2s,回流后的5s,回流后的35s,回流后的65s...后续间隔30s查询一次至明确成功或失败
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchangeresultquery/1.0.0`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "string",
      "description": ""
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "out_uniq_water_no": {
      "type": "string",
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
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `request` | `string` | ❌ | `` |  |
| `root_kdt_id` | `integer` | ✅ | `232423` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `out_uniq_water_no` | `string` | ✅ | `1111` | 外部系统储值卡流水号，必填说明：储值卡流水的唯一标识 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": ""
    },
    "process_status": {
      "type": "string",
      "description": "流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败",
      "example": "FAIL"
    },
    "extra": {
      "type": "object",
      "description": "扩展信息",
      "example": "{\"\":\"\"}"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "out_water_no": {
      "type": "string",
      "description": "外部唯一流水号",
      "example": "1111"
    },
    "card_no": {
      "type": "string",
      "description": "储值卡号",
      "example": "aaaaa"
    },
    "fail_reason": {
      "type": "string",
      "description": "处理失败原因",
      "example": "开卡失败，本流水仅允许充值类型开卡"
    },
    "success": {
      "type": "boolean",
      "description": "true",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "200",
      "example": "118711202"
    },
    "message": {
      "type": "string",
      "description": ""
    },
    "request_id": {
      "type": "string",
      "description": ""
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
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` |  |
| `process_status` | `string` | ❌ | `FAIL` | 流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败 |
| `extra` | `object` | ❌ | `{"":""}` | 扩展信息 |
| `root_kdt_id` | `integer` | ❌ | `232423` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `out_water_no` | `string` | ❌ | `1111` | 外部唯一流水号 |
| `card_no` | `string` | ❌ | `aaaaa` | 储值卡号 |
| `fail_reason` | `string` | ❌ | `开卡失败，本流水仅允许充值类型开卡` | 处理失败原因 |
| `success` | `boolean` | ❌ | `true` | true |
| `code` | `integer` | ❌ | `118711202` | 200 |
| `message` | `string` | ❌ | `` |  |
| `request_id` | `string` | ❌ | `` |  |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchangeresultquery/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "root_kdt_id": "232423",\n  "out_uniq_water_no": "1111"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchangeresultquery/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "root_kdt_id": "232423",
    "out_uniq_water_no": "1111"
}

resp = requests.post(url, json=payload, headers=headers)
print(resp.json())
```
---
## 5. 错误码
| 错误码 | 类型 | 说明 |
|--------|------|------|
| 10001 | `SYSTEM_ERROR` | 系统内部错误 |
| 10002 | `INVALID_PARAMETER` | 参数错误 |
| 10003 | `UNAUTHORIZED` | 未授权或授权已过期 |
| 10004 | `PERMISSION_DENIED` | 无权限调用此接口 |
| 10005 | `RESOURCE_NOT_FOUND` | 请求的资源不存在 |
| 20001 | `RATE_LIMIT_EXCEEDED` | 调用频率超限 |
| 20002 | `QUOTA_EXCEEDED` | 接口配额已用完 |
---
## 6. 权限与计费

**接口计费状态：未知（请以官网实际披露为准）。**

**拥有此API的能力包：** 暂无数据（请以官网实际披露为准）。

---
## 7. 权限说明

**应用类目 → 权限类型：**

| 应用类目 | 权限类型 |
|----------|----------|
| 有赞微商城、有赞零售、有赞教育、有赞美业 | 普通自研商家（基础权益） |
| 大客户定制接口、美业大客户定制、零售大客户定制、收款二维码-大客专用 | 大客定制接口（需购买大客套餐） |
| 客户关系CRM、门店POS | iPaaS 套餐权益（需购买 iPaaS 套餐） |

> 权限数据来源：[有赞云能力包说明](https://doc.youzanyun.com/detail/content/API/0/120)