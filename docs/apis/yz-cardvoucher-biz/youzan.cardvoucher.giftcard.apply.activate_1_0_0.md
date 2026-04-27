---
apiName: "youzan.cardvoucher.giftcard.apply.activate.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "activate"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-03-14"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3706"
---
# youzan.cardvoucher.giftcard.apply.activate.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
储值礼品卡激活接口，（如实现储值卡激活扩展点https://doc.youzanyun.com/detail/EXT/20001可触发扩展点；如礼品卡已经激活会返回成功）
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.apply.activate/1.0.0`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。",
      "example": "Kce872bU658955584007081984"
    },
    "card_alias": {
      "type": "string",
      "description": "礼品卡别名（扩展点场景无需传入）",
      "example": "3XYALEPnOrAxJiB6DMZ"
    },
    "group_no": {
      "type": "string",
      "description": "礼品卡组号",
      "example": "310201391527990"
    }
  },
  "required": [
    "yz_open_id",
    "card_alias",
    "group_no"
  ]
}
```
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `yz_open_id` | `integer` | ✅ | `Kce872bU658955584007081984` | 有赞用户id，用户在有赞的唯一id。 |
| `card_alias` | `string` | ✅ | `3XYALEPnOrAxJiB6DMZ` | 礼品卡别名（扩展点场景无需传入） |
| `group_no` | `string` | ✅ | `310201391527990` | 礼品卡组号 |
---
## 3. 响应
**响应参数 Schema**（4 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "boolean",
      "description": "是否激活成功",
      "example": "true"
    },
    "success": {
      "type": "boolean",
      "description": "请求是否成功",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "网关响应码",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "网关响应描述",
      "example": "successful"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "true",
  "success": "true",
  "code": "200",
  "message": "successful"
}
```
**响应参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `boolean` | ❌ | `true` | 是否激活成功 |
| `success` | `boolean` | ❌ | `true` | 请求是否成功 |
| `code` | `integer` | ❌ | `200` | 网关响应码 |
| `message` | `string` | ❌ | `successful` | 网关响应描述 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.apply.activate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "yz_open_id": "Kce872bU658955584007081984",\n  "card_alias": "3XYALEPnOrAxJiB6DMZ",\n  "group_no": "310201391527990"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.apply.activate/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "yz_open_id": "Kce872bU658955584007081984",
    "card_alias": "3XYALEPnOrAxJiB6DMZ",
    "group_no": "310201391527990"
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