---
apiName: "youzan.cardvoucher.giftcard.operate.exchange.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "exchangeCard"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-04-07"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4029"
---
# youzan.cardvoucher.giftcard.operate.exchange.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
礼品卡兑换：支持卡密兑换和扫码兑换，仅进行兑换，不会自动触发激活。可通过商家后台批量制卡后生成的兑换信息进行调用，支持电子卡和实体卡兑换。
备注：如扩展点兑换流程中衔接本接口，返回的电子卡号不可直接作为用户的卡号返回，否则选择此卡号支付时会走到标品，可通过自定义卡号映射或加固定前/后缀解决，非扩展点流程对接无需关注本备注。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.operate.exchange/1.0.0`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】",
      "example": "MVJ5w0uy585097513770430464"
    },
    "card_no_or_serial_num": {
      "type": "string",
      "description": "卡密兑换时必填：可填批量制卡后的电子卡的序列号或实体卡的卡号进行兑换序列号",
      "example": "aaaaaaa"
    },
    "check_code": {
      "type": "string",
      "description": "卡密兑换时必填：兑换码",
      "example": "1111111"
    },
    "card_random": {
      "type": "string",
      "description": "扫码兑换时必填：卡号随机数"
    },
    "exchange_type": {
      "type": "integer",
      "description": "兑换类型：0(卡密兑换) 1(扫码兑换)",
      "example": "0"
    }
  },
  "required": [
    "yz_open_id",
    "card_no_or_serial_num",
    "exchange_type"
  ]
}
```
**请求参数明细**（5 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `yz_open_id` | `integer` | ✅ | `MVJ5w0uy585097513770430464` | 有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】 |
| `card_no_or_serial_num` | `string` | ✅ | `aaaaaaa` | 卡密兑换时必填：可填批量制卡后的电子卡的序列号或实体卡的卡号进行兑换序列号 |
| `check_code` | `string` | ❌ | `1111111` | 卡密兑换时必填：兑换码 |
| `card_random` | `string` | ❌ | `` | 扫码兑换时必填：卡号随机数 |
| `exchange_type` | `integer` | ✅ | `0` | 兑换类型：0(卡密兑换) 1(扫码兑换) |
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
    "card_no": {
      "type": "string",
      "description": "电子卡卡号",
      "example": "1234567890"
    },
    "exchange_status": {
      "type": "integer",
      "description": "兑换状态：2(兑换成功，且是首次被兑换成功) 3(卡已经被兑换过，且是当前用户兑换的) 4(卡已经被兑换过，且是被他人兑换的) 5(卡已被失效，无法兑换)",
      "example": "2"
    },
    "exchange_date": {
      "type": "string",
      "description": "兑换时间-毫秒级时间戳",
      "example": "1680863031000"
    },
    "template_no": {
      "type": "string",
      "description": "卡模板号",
      "example": "1234567899"
    },
    "template_name": {
      "type": "string",
      "description": "卡模板名称",
      "example": "测试卡模板"
    },
    "denomination": {
      "type": "integer",
      "description": "卡面额-分",
      "example": "100"
    },
    "principal": {
      "type": "integer",
      "description": "卡内本金-分",
      "example": "60"
    },
    "bonus": {
      "type": "integer",
      "description": "卡内赠送金-分",
      "example": "40"
    },
    "expired_date": {
      "type": "string",
      "description": "批量制卡时卡的有效期截止日期-毫秒时间戳",
      "example": "1680863031"
    },
    "support_give": {
      "type": "boolean",
      "description": "卡模板配置的礼品卡是否支持赠送：true支持，false不支持",
      "example": "true"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "card_no": "1234567890",
  "exchange_status": "2",
  "exchange_date": "1680863031000",
  "template_no": "1234567899",
  "template_name": "测试卡模板",
  "denomination": "100",
  "principal": "60"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` |  |
| `card_no` | `string` | ❌ | `1234567890` | 电子卡卡号 |
| `exchange_status` | `integer` | ❌ | `2` | 兑换状态：2(兑换成功，且是首次被兑换成功) 3(卡已经被兑换过，且是当前用户兑换的) 4(卡已经被兑换过，且是被他人兑换的) 5(卡已被失效，无法兑换) |
| `exchange_date` | `string` | ❌ | `1680863031000` | 兑换时间-毫秒级时间戳 |
| `template_no` | `string` | ❌ | `1234567899` | 卡模板号 |
| `template_name` | `string` | ❌ | `测试卡模板` | 卡模板名称 |
| `denomination` | `integer` | ❌ | `100` | 卡面额-分 |
| `principal` | `integer` | ❌ | `60` | 卡内本金-分 |
| `bonus` | `integer` | ❌ | `40` | 卡内赠送金-分 |
| `expired_date` | `string` | ❌ | `1680863031` | 批量制卡时卡的有效期截止日期-毫秒时间戳 |
| `support_give` | `boolean` | ❌ | `true` | 卡模板配置的礼品卡是否支持赠送：true支持，false不支持 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.operate.exchange/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "yz_open_id": "MVJ5w0uy585097513770430464",\n  "card_no_or_serial_num": "aaaaaaa",\n  "check_code": "1111111",\n  "exchange_type": "0"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.operate.exchange/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "yz_open_id": "MVJ5w0uy585097513770430464",
    "card_no_or_serial_num": "aaaaaaa",
    "check_code": "1111111",
    "exchange_type": "0"
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