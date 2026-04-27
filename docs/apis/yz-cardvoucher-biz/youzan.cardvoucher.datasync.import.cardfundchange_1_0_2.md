---
apiName: "youzan.cardvoucher.datasync.import.cardfundchange.1.0.2"
version: "1.0.2"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "syncCardFundChange"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-02-13"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3990"
---
# youzan.cardvoucher.datasync.import.cardfundchange.1.0.2
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
接入前请阅读调用注意事项：https://doc.youzanyun.com/resource/doc/3404/5593
本接口需配合
youzan.cardvoucher.datasync.import.cardfundchangeresultquery进行同步结果查询使用
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.2`
**请求参数 Schema**（11 个参数）:
```json
{
  "type": "object",
  "properties": {
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，为发生交易的门网店",
      "example": "60102804"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "总部店铺id",
      "example": "60102626"
    },
    "out_uniq_water_no": {
      "type": "string",
      "description": "外部系统储值卡流水号，必填。说明：储值卡流水的唯一标识,如请求明确失败重试需换单号",
      "example": "HBYTESTIMPORT0103"
    },
    "client_source": {
      "type": "string",
      "description": "请求来源业务方标识，必填，比如烘焙云：HONGBEIYUN",
      "example": "open"
    },
    "user_info": {
      "type": "string",
      "description": "用户信息"
    },
    "mobile_no": {
      "type": "string",
      "description": "手机号",
      "example": "13186972611"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "用户id",
      "example": "7j3Gi1UH732330877366837248"
    },
    "user_name": {
      "type": "string",
      "description": "用户名称",
      "example": "木七"
    },
    "user_nick_name": {
      "type": "string",
      "description": "用户昵称",
      "example": "木七"
    },
    "card_no": {
      "type": "string",
      "description": "卡号，必填",
      "example": "1234567891271"
    },
    "card_type": {
      "type": "string",
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
**请求参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `kdt_id` | `integer` | ✅ | `60102804` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，为发生交易的门网店 |
| `root_kdt_id` | `integer` | ✅ | `60102626` | 总部店铺id |
| `out_uniq_water_no` | `string` | ✅ | `HBYTESTIMPORT0103` | 外部系统储值卡流水号，必填。说明：储值卡流水的唯一标识,如请求明确失败重试需换单号 |
| `client_source` | `string` | ✅ | `open` | 请求来源业务方标识，必填，比如烘焙云：HONGBEIYUN |
| `user_info` | `string` | ✅ | `` | 用户信息 |
| `mobile_no` | `string` | ❌ | `13186972611` | 手机号 |
| `yz_open_id` | `integer` | ✅ | `7j3Gi1UH732330877366837248` | 用户id |
| `user_name` | `string` | ❌ | `木七` | 用户名称 |
| `user_nick_name` | `string` | ❌ | `木七` | 用户昵称 |
| `card_no` | `string` | ✅ | `1234567891271` | 卡号，必填 |
| `card_type` | `string` | ✅ | `1001` | 卡类型：1001储值余额卡 1002 储值卡(即礼品卡) 默认为余额卡 |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "同步储值卡资金变动流水信息至有赞接口响应参数"
    },
    "extra": {
      "type": "object",
      "description": "扩展信息",
      "example": "{\"\":\"\"}"
    },
    "process_status": {
      "type": "string",
      "description": "流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败",
      "example": "SUCCESS"
    },
    "fail_reason": {
      "type": "string",
      "description": "处理失败原因",
      "example": "开卡失败，本流水仅允许充值类型开卡"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "总部kdtid",
      "example": "60102626"
    },
    "out_water_no": {
      "type": "string",
      "description": "外部系统储值卡唯一流水号",
      "example": "HBYTESTIMPORT0103"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "1234567891271"
    },
    "success": {
      "type": "boolean",
      "description": "true",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "180001",
      "example": "001"
    },
    "message": {
      "type": "string",
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
**响应参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 同步储值卡资金变动流水信息至有赞接口响应参数 |
| `extra` | `object` | ❌ | `{"":""}` | 扩展信息 |
| `process_status` | `string` | ❌ | `SUCCESS` | 流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败 |
| `fail_reason` | `string` | ❌ | `开卡失败，本流水仅允许充值类型开卡` | 处理失败原因 |
| `root_kdt_id` | `integer` | ❌ | `60102626` | 总部kdtid |
| `out_water_no` | `string` | ❌ | `HBYTESTIMPORT0103` | 外部系统储值卡唯一流水号 |
| `card_no` | `string` | ❌ | `1234567891271` | 卡号 |
| `success` | `boolean` | ❌ | `true` | true |
| `code` | `integer` | ❌ | `001` | 180001 |
| `message` | `string` | ❌ | `success` | SUCCESS |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "kdt_id": "60102804",\n  "root_kdt_id": "60102626",\n  "out_uniq_water_no": "HBYTESTIMPORT0103",\n  "client_source": "open",\n  "user_info": "示例值",\n  "mobile_no": "13186972611",\n  "yz_open_id": "7j3Gi1UH732330877366837248",\n  "user_name": "木七",\n  "user_nick_name": "木七",\n  "card_no": "1234567891271",\n  "card_type": "1001"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.2"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "kdt_id": "60102804",
    "root_kdt_id": "60102626",
    "out_uniq_water_no": "HBYTESTIMPORT0103",
    "client_source": "open",
    "user_info": "示例值",
    "mobile_no": "13186972611",
    "yz_open_id": "7j3Gi1UH732330877366837248",
    "user_name": "木七",
    "user_nick_name": "木七",
    "card_no": "1234567891271",
    "card_type": "1001"
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