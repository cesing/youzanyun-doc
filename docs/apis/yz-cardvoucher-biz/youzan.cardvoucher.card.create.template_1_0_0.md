---
apiName: "youzan.cardvoucher.card.create.template.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "create"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-01-17"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3588"
---
# youzan.cardvoucher.card.create.template.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
地址：商家后台-会员-储值规则，创建余额模板或储值卡模板
一个店铺只能创建一个余额模板，可创建多个储值卡模板，储值卡的名字不能重复
仅限连接器项目使用，此接口生成的卡模板部分属性储值内部已写死
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.create.template/1.0.0`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "kdt_id": {
      "type": "string",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "102129885"
    },
    "operator_uid": {
      "type": "string",
      "description": "操作人id，传入注册过有赞的手机号，会自动转换成有赞体系内的id",
      "example": "18758285476"
    },
    "template_type": {
      "type": "integer",
      "description": "模板类型：1001 余额模板 1002 储值卡模板",
      "example": "1002"
    },
    "operator_name": {
      "type": "string",
      "description": "操作人名称",
      "example": "fairy"
    },
    "template_name": {
      "type": "string",
      "description": "模版名称，",
      "example": "fairy测试储值卡"
    },
    "limit_type": {
      "type": "integer",
      "description": "卡模板适用店铺类型：0 所有店铺 1 部分店铺适用 2 部分店铺不适应",
      "example": "0"
    },
    "kdt_ids": {
      "type": "array",
      "description": "当卡模板适用店铺类型为1/2时必填",
      "example": "[\"102129885\"]"
    }
  },
  "required": [
    "kdt_id",
    "operator_uid",
    "template_type",
    "template_name",
    "limit_type"
  ]
}
```
**请求参数明细**（7 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `kdt_id` | `string` | ✅ | `102129885` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `operator_uid` | `string` | ✅ | `18758285476` | 操作人id，传入注册过有赞的手机号，会自动转换成有赞体系内的id |
| `template_type` | `integer` | ✅ | `1002` | 模板类型：1001 余额模板 1002 储值卡模板 |
| `operator_name` | `string` | ❌ | `fairy` | 操作人名称 |
| `template_name` | `string` | ✅ | `fairy测试储值卡` | 模版名称， |
| `limit_type` | `integer` | ✅ | `0` | 卡模板适用店铺类型：0 所有店铺 1 部分店铺适用 2 部分店铺不适应 |
| `kdt_ids` | `array` | ❌ | `["102129885"]` | 当卡模板适用店铺类型为1/2时必填 |
---
## 3. 响应
**响应参数 Schema**（7 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "创建卡模板接口响应参数"
    },
    "template_no": {
      "type": "string",
      "description": "模版编号",
      "example": "6534123450"
    },
    "success": {
      "type": "boolean",
      "description": "请求是否成功",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "响应码",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "响应信息",
      "example": "成功"
    },
    "request_id": {
      "type": "string",
      "description": "请求id",
      "example": "0000000000000"
    },
    "error_data": {
      "type": "object",
      "description": "错误信息",
      "example": "错误"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "template_no": "6534123450",
  "success": "true",
  "code": "200",
  "message": "成功",
  "request_id": "0000000000000",
  "error_data": "错误"
}
```
**响应参数明细**（7 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 创建卡模板接口响应参数 |
| `template_no` | `string` | ❌ | `6534123450` | 模版编号 |
| `success` | `boolean` | ❌ | `true` | 请求是否成功 |
| `code` | `integer` | ❌ | `200` | 响应码 |
| `message` | `string` | ❌ | `成功` | 响应信息 |
| `request_id` | `string` | ❌ | `0000000000000` | 请求id |
| `error_data` | `object` | ❌ | `错误` | 错误信息 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.card.create.template/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "kdt_id": "102129885",\n  "operator_uid": "18758285476",\n  "template_type": "1002",\n  "operator_name": "fairy",\n  "template_name": "fairy测试储值卡",\n  "limit_type": "0",\n  "kdt_ids": "[\"102129885\"]"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.create.template/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "kdt_id": "102129885",
    "operator_uid": "18758285476",
    "template_type": "1002",
    "operator_name": "fairy",
    "template_name": "fairy测试储值卡",
    "limit_type": "0",
    "kdt_ids": "[\"102129885\"]"
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