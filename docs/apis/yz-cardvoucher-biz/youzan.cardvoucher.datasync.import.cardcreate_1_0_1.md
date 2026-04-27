---
apiName: "youzan.cardvoucher.datasync.import.cardcreate.1.0.1"
version: "1.0.1"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "openCard"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-10-28"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3913"
---
# youzan.cardvoucher.datasync.import.cardcreate.1.0.1
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
用于外部储值根据外部卡号，进行开卡
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.1`
**请求参数 Schema**（12 个参数）:
```json
{
  "type": "object",
  "properties": {
    "open": {
      "type": "string",
      "description": "request"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "client_source": {
      "type": "string",
      "description": "请求来源业务方标识，必填",
      "example": "clientSource"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用",
      "example": "LnhGm4rh576452722916618240"
    },
    "out_card_no": {
      "type": "string",
      "description": "外部储值卡号，必填",
      "example": "OUT2022111"
    },
    "card_type": {
      "type": "string",
      "description": "储值卡类型，不填默认为余额卡，储值卡类型时extra中的卡模板号templateNo，必填1001余额卡，仅支持余额卡",
      "example": "1001"
    },
    "out_biz_no": {
      "type": "string",
      "description": "外部系统业务单号，非必填说明：可做幂等等逻辑判断",
      "example": "OUTBIZsss222"
    },
    "open_time": {
      "type": "integer",
      "description": "三方卡账单业务发生时间格式：毫秒时间戳",
      "example": "160000000"
    },
    "amount": {
      "type": "integer",
      "description": "开卡总金额，单位：分，非必填",
      "example": "0"
    },
    "bonus_amt": {
      "type": "integer",
      "description": "开卡赠送金额，单位:分，非必填",
      "example": "0"
    },
    "desc": {
      "type": "string",
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
**请求参数明细**（12 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `open` | `string` | ❌ | `` | request |
| `kdt_id` | `integer` | ✅ | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `root_kdt_id` | `integer` | ✅ | `232423` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `client_source` | `string` | ✅ | `clientSource` | 请求来源业务方标识，必填 |
| `yz_open_id` | `integer` | ✅ | `LnhGm4rh576452722916618240` | 有赞用户id，用户在有赞的唯一id。推荐使用 |
| `out_card_no` | `string` | ✅ | `OUT2022111` | 外部储值卡号，必填 |
| `card_type` | `string` | ✅ | `1001` | 储值卡类型，不填默认为余额卡，储值卡类型时extra中的卡模板号templateNo，必填1001余额卡，仅支持余额卡 |
| `out_biz_no` | `string` | ❌ | `OUTBIZsss222` | 外部系统业务单号，非必填说明：可做幂等等逻辑判断 |
| `open_time` | `integer` | ❌ | `160000000` | 三方卡账单业务发生时间格式：毫秒时间戳 |
| `amount` | `integer` | ❌ | `0` | 开卡总金额，单位：分，非必填 |
| `bonus_amt` | `integer` | ❌ | `0` | 开卡赠送金额，单位:分，非必填 |
| `desc` | `string` | ❌ | `地方的` | 流水描述，非必填 |
---
## 3. 响应
**响应参数 Schema**（8 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "返回数据"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "card_no": {
      "type": "string",
      "description": "储值卡号",
      "example": "ddd1111"
    },
    "extra": {
      "type": "object",
      "description": "扩展信息",
      "example": "{\"\"}"
    },
    "success": {
      "type": "boolean",
      "description": "是否成功",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "状态码",
      "example": "0"
    },
    "message": {
      "type": "string",
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
**响应参数明细**（8 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 返回数据 |
| `kdt_id` | `integer` | ❌ | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `root_kdt_id` | `integer` | ❌ | `232423` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `card_no` | `string` | ❌ | `ddd1111` | 储值卡号 |
| `extra` | `object` | ❌ | `{""}` | 扩展信息 |
| `success` | `boolean` | ❌ | `true` | 是否成功 |
| `code` | `integer` | ❌ | `0` | 状态码 |
| `message` | `string` | ❌ | `error` | 错误信息 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "kdt_id": "88888",\n  "root_kdt_id": "232423",\n  "client_source": "clientSource",\n  "yz_open_id": "LnhGm4rh576452722916618240",\n  "out_card_no": "OUT2022111",\n  "card_type": "1001",\n  "out_biz_no": "OUTBIZsss222",\n  "open_time": "160000000",\n  "amount": "0",\n  "bonus_amt": "0",\n  "desc": "地方的"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.1"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "kdt_id": "88888",
    "root_kdt_id": "232423",
    "client_source": "clientSource",
    "yz_open_id": "LnhGm4rh576452722916618240",
    "out_card_no": "OUT2022111",
    "card_type": "1001",
    "out_biz_no": "OUTBIZsss222",
    "open_time": "160000000",
    "amount": "0",
    "bonus_amt": "0",
    "desc": "地方的"
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