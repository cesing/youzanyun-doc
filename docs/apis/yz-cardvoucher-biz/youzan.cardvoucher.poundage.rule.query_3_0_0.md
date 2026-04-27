---
apiName: "youzan.cardvoucher.poundage.rule.query.3.0.0"
version: "3.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "retail_valuecard"
method: "queryPoundageRule"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-07-15"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3057"
---
# youzan.cardvoucher.poundage.rule.query.3.0.0
> **所属分组**: retail_valuecard　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
储值卡退卡手续费规则查询，调用储值卡退卡申请API前置调用，用于计算退卡手续费
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.poundage.rule.query/3.0.0`
**请求参数 Schema**（0 个参数）:
```json
{
  "type": "object",
  "properties": {},
  "required": []
}
```
**请求参数明细**：暂无数据

---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "返回参数"
    },
    "scenes": {
      "type": "string",
      "description": "场景，RECEDE_CARD:退卡",
      "example": "RECEDE_CARD"
    },
    "type": {
      "type": "string",
      "description": "类型：FIX:固定手续费，PERCENT:百分比",
      "example": "PERCENT"
    },
    "poundage_value": {
      "type": "integer",
      "description": "手续费金额，type为FIX：则为具体金额,单位为分； type为PERCENT：返回值范围0~10000，单位：万分比 例如返回值为10即表示手续费比例是0.1%",
      "example": "1"
    },
    "format_poundage_value": {
      "type": "string",
      "description": "手续费金额，数值为保留2位小数后的格式化字符串，可以直接用于展示",
      "example": "0.01"
    },
    "limit_value": {
      "type": "integer",
      "description": "手续费门槛金额，退卡金额高于门槛金额，按上述规则收取手续费，单位为分",
      "example": "10"
    },
    "success": {
      "type": "boolean",
      "description": "处理结果",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "处理结果状态码",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "处理结果提示",
      "example": "执行成功"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "scenes": "RECEDE_CARD",
  "type": "PERCENT",
  "poundage_value": "1",
  "format_poundage_value": "0.01",
  "limit_value": "10",
  "success": "true",
  "code": "200"
}
```
**响应参数明细**（9 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 返回参数 |
| `scenes` | `string` | ❌ | `RECEDE_CARD` | 场景，RECEDE_CARD:退卡 |
| `type` | `string` | ❌ | `PERCENT` | 类型：FIX:固定手续费，PERCENT:百分比 |
| `poundage_value` | `integer` | ❌ | `1` | 手续费金额，type为FIX：则为具体金额,单位为分； type为PERCENT：返回值范围0~10000，单位：万分比 例如返回值为10即表示手续费比例是0. |
| `format_poundage_value` | `string` | ❌ | `0.01` | 手续费金额，数值为保留2位小数后的格式化字符串，可以直接用于展示 |
| `limit_value` | `integer` | ❌ | `10` | 手续费门槛金额，退卡金额高于门槛金额，按上述规则收取手续费，单位为分 |
| `success` | `boolean` | ❌ | `true` | 处理结果 |
| `code` | `integer` | ❌ | `200` | 处理结果状态码 |
| `message` | `string` | ❌ | `执行成功` | 处理结果提示 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.poundage.rule.query/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.poundage.rule.query/3.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {}

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