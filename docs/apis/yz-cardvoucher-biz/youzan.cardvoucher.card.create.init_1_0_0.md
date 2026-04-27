---
apiName: "youzan.cardvoucher.card.create.init.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "createCard"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-11-16"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3926"
---
# youzan.cardvoucher.card.create.init.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
储值礼品卡制卡接口，会创建未激活的礼品卡且没有归属人，该礼品卡可以在商家后台 储值查询-卡查询中根据返回的卡号查询信息
一般配合youzan.cardvoucher.giftcard.marketing.issue接口进行后续的发卡使用
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.create.init/1.0.0`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "string",
      "description": "请求参数"
    },
    "request_no": {
      "type": "string",
      "description": "请求单号，是幂等单号要求唯一",
      "example": "Unique123456"
    },
    "template_no": {
      "type": "string",
      "description": "卡模板号",
      "example": "11111111"
    },
    "img_url_no": {
      "type": "integer",
      "description": "制卡卡模板选择第几个封面，从1开始计数，可不填，不填默认取第一个封面图片",
      "example": "1"
    },
    "price": {
      "type": "integer",
      "description": "制卡卡模板选择的面额，单位分，不传默认取最小的面额",
      "example": "100"
    },
    "operator_name": {
      "type": "string",
      "description": "操作员姓名",
      "example": "aaa"
    },
    "operator_mobile": {
      "type": "string",
      "description": "操作员手机号",
      "example": "12345678901"
    }
  },
  "required": [
    "request_no",
    "template_no",
    "operator_name",
    "operator_mobile"
  ]
}
```
**请求参数明细**（7 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `request` | `string` | ❌ | `` | 请求参数 |
| `request_no` | `string` | ✅ | `Unique123456` | 请求单号，是幂等单号要求唯一 |
| `template_no` | `string` | ✅ | `11111111` | 卡模板号 |
| `img_url_no` | `integer` | ❌ | `1` | 制卡卡模板选择第几个封面，从1开始计数，可不填，不填默认取第一个封面图片 |
| `price` | `integer` | ❌ | `100` | 制卡卡模板选择的面额，单位分，不传默认取最小的面额 |
| `operator_name` | `string` | ✅ | `aaa` | 操作员姓名 |
| `operator_mobile` | `string` | ✅ | `12345678901` | 操作员手机号 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "接口返回数据"
    },
    "request_no": {
      "type": "string",
      "description": "请求单号",
      "example": "Unique123456"
    },
    "card_no": {
      "type": "string",
      "description": "制成的卡号",
      "example": "987654321"
    },
    "status": {
      "type": "string",
      "description": "制卡状态SUCCESS:成功FAIL:失败ING:制卡中",
      "example": "SUCCESS"
    },
    "code": {
      "type": "integer",
      "description": "网关返回码，表示本次请求是否成功。200 成功",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "制卡成功"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "successful"
    },
    "request_id": {
      "type": "string",
      "description": ""
    },
    "error_data": {
      "type": "object",
      "description": ""
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "request_no": "Unique123456",
  "card_no": "987654321",
  "status": "SUCCESS",
  "code": "200",
  "msg": "制卡成功",
  "success": "true"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 接口返回数据 |
| `request_no` | `string` | ❌ | `Unique123456` | 请求单号 |
| `card_no` | `string` | ❌ | `987654321` | 制成的卡号 |
| `status` | `string` | ❌ | `SUCCESS` | 制卡状态SUCCESS:成功FAIL:失败ING:制卡中 |
| `code` | `string` | ❌ | `200` | 结果码 |
| `msg` | `string` | ❌ | `制卡成功` | 状态描述 |
| `success` | `boolean` | ❌ | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `integer` | ❌ | `200` | 网关返回码，表示本次请求是否成功。200 成功 |
| `message` | `string` | ❌ | `successful` | 网关返回码描述 |
| `request_id` | `string` | ❌ | `` |  |
| `error_data` | `object` | ❌ | `` |  |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.card.create.init/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "request_no": "Unique123456",\n  "template_no": "11111111",\n  "img_url_no": "1",\n  "price": "100",\n  "operator_name": "aaa",\n  "operator_mobile": "12345678901"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.create.init/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "request_no": "Unique123456",
    "template_no": "11111111",
    "img_url_no": "1",
    "price": "100",
    "operator_name": "aaa",
    "operator_mobile": "12345678901"
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