---
apiName: "youzan.cardvoucher.datasync.import.cardfundchange.1.0.1"
version: "1.0.1"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "syncCardFundChange"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-02-24"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3673"
---
# youzan.cardvoucher.datasync.import.cardfundchange.1.0.1
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
同步储值卡资金变动流水信息至有赞，仅限连接器项目使用
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.1`
**请求参数 Schema**（11 个参数）:
```json
{
  "type": "object",
  "properties": {
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "60102804"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "总部机构店铺号",
      "example": "60102626"
    },
    "out_uniq_water_no": {
      "type": "string",
      "description": "外部系统储值卡流水号，必填说明：储值卡流水的唯一标识",
      "example": "HBYTESTIMPORT0103"
    },
    "client_source": {
      "type": "string",
      "description": "请求来源业务方标识，必填",
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
      "description": "储值卡号，必填",
      "example": "1234567891271"
    },
    "card_type": {
      "type": "string",
      "description": "卡类型：1001余额卡 1002 储值卡 默认余额卡",
      "example": "1001"
    }
  },
  "required": [
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
**请求参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `kdt_id` | `integer` | ✅ | `60102804` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `root_kdt_id` | `integer` | ✅ | `60102626` | 总部机构店铺号 |
| `out_uniq_water_no` | `string` | ✅ | `HBYTESTIMPORT0103` | 外部系统储值卡流水号，必填说明：储值卡流水的唯一标识 |
| `client_source` | `string` | ✅ | `open` | 请求来源业务方标识，必填 |
| `user_info` | `string` | ✅ | `` | 用户信息 |
| `mobile_no` | `string` | ✅ | `13186972611` | 手机号 |
| `yz_open_id` | `integer` | ✅ | `7j3Gi1UH732330877366837248` | 用户id |
| `user_name` | `string` | ✅ | `木七` | 用户名称 |
| `user_nick_name` | `string` | ✅ | `木七` | 用户昵称 |
| `card_no` | `string` | ✅ | `1234567891271` | 储值卡号，必填 |
| `card_type` | `string` | ✅ | `1001` | 卡类型：1001余额卡 1002 储值卡 默认余额卡 |
---
## 3. 响应
**响应参数 Schema**（5 个字段）:
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
  "success": "true",
  "code": "001",
  "message": "success"
}
```
**响应参数明细**（5 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 同步储值卡资金变动流水信息至有赞接口响应参数 |
| `extra` | `object` | ❌ | `{"":""}` | 扩展信息 |
| `success` | `boolean` | ❌ | `true` | true |
| `code` | `integer` | ❌ | `001` | 180001 |
| `message` | `string` | ❌ | `success` | SUCCESS |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "kdt_id": "60102804",\n  "root_kdt_id": "60102626",\n  "out_uniq_water_no": "HBYTESTIMPORT0103",\n  "client_source": "open",\n  "user_info": "示例值",\n  "mobile_no": "13186972611",\n  "yz_open_id": "7j3Gi1UH732330877366837248",\n  "user_name": "木七",\n  "user_nick_name": "木七",\n  "card_no": "1234567891271",\n  "card_type": "1001"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.1"
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