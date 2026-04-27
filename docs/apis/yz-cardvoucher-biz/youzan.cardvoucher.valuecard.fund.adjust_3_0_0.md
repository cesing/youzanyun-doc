---
apiName: "youzan.cardvoucher.valuecard.fund.adjust.3.0.0"
version: "3.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "adjust"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2019-03-22"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/199"
---
# youzan.cardvoucher.valuecard.fund.adjust.3.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
连锁门店网店模式的总部，没有经营权限的，不能使用该接口。
如发生下述任一情况而导致服务中断及开发者损失的，有赞不承担责任：
（1）发生不可抗力情形的；
（2）黑客攻击、计算机病毒侵入或发作的；
（3）计算机系统遭到破坏、瘫痪或无法正常使用的；
（4）电信部门技术调整的；
（5）因政府管制而造成暂时性关闭的；
（6）其它非因有赞的过错而引起的。
此为老版，推荐使用3.0.1新版本

---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.adjust/3.0.0`
**请求参数 Schema**（11 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "string",
      "description": ""
    },
    "request_no": {
      "type": "string",
      "description": "请求号，请确保唯一（长度不超过24个字符）",
      "example": "weixiao20190730001"
    },
    "mobile": {
      "type": "string",
      "description": "客户手机号码（mobile或者buyer_id二选一）",
      "example": "18972515558"
    },
    "buyer_id": {
      "type": "integer",
      "description": "客户Id（mobile或者buyer_id二选一）",
      "example": "1441668074"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "310201043501229"
    },
    "adjust_principal": {
      "type": "integer",
      "description": "调整本金金额，单位：分",
      "example": "100"
    },
    "adjust_bonus": {
      "type": "integer",
      "description": "调整赠送金金额，单位：分",
      "example": "20"
    },
    "adjust_type": {
      "type": "integer",
      "description": "调账类型；1：调增，2：调减",
      "example": "1"
    },
    "remark": {
      "type": "string",
      "description": "描述",
      "example": "描述TEST"
    },
    "operator_name": {
      "type": "string",
      "description": "操作员姓名",
      "example": "卫潇"
    },
    "operator_mobile": {
      "type": "string",
      "description": "操作员手机号",
      "example": "13209******"
    }
  },
  "required": [
    "request_no",
    "card_no",
    "adjust_type",
    "operator_name",
    "operator_mobile"
  ]
}
```
**请求参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `request` | `string` | ❌ | `` |  |
| `request_no` | `string` | ✅ | `weixiao20190730001` | 请求号，请确保唯一（长度不超过24个字符） |
| `mobile` | `string` | ❌ | `18972515558` | 客户手机号码（mobile或者buyer_id二选一） |
| `buyer_id` | `integer` | ❌ | `1441668074` | 客户Id（mobile或者buyer_id二选一） |
| `card_no` | `string` | ✅ | `310201043501229` | 卡号 |
| `adjust_principal` | `integer` | ❌ | `100` | 调整本金金额，单位：分 |
| `adjust_bonus` | `integer` | ❌ | `20` | 调整赠送金金额，单位：分 |
| `adjust_type` | `integer` | ✅ | `1` | 调账类型；1：调增，2：调减 |
| `remark` | `string` | ❌ | `描述TEST` | 描述 |
| `operator_name` | `string` | ✅ | `卫潇` | 操作员姓名 |
| `operator_mobile` | `string` | ✅ | `13209******` | 操作员手机号 |
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
    "request_no": {
      "type": "string",
      "description": "请求号",
      "example": "weixiao20190730001"
    },
    "adjust_no": {
      "type": "string",
      "description": "调账单号",
      "example": "CDA190730041652000092"
    },
    "status": {
      "type": "string",
      "description": "调账状态；SUCCESS：成功，FAIL：失败，ING：处理中",
      "example": "SUCCESS"
    },
    "code": {
      "type": "integer",
      "description": "网关返回码，表示本次请求是否成功。200:成功",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "调账成功"
    },
    "inner_adjust_no": {
      "type": "string",
      "description": "内部调账单号",
      "example": "SGCDA190730041652000092"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。true:成功,false:失败",
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
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "request_no": "weixiao20190730001",
  "adjust_no": "CDA190730041652000092",
  "status": "SUCCESS",
  "code": "200",
  "msg": "调账成功",
  "inner_adjust_no": "SGCDA190730041652000092",
  "success": "true"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` |  |
| `request_no` | `string` | ❌ | `weixiao20190730001` | 请求号 |
| `adjust_no` | `string` | ❌ | `CDA190730041652000092` | 调账单号 |
| `status` | `string` | ❌ | `SUCCESS` | 调账状态；SUCCESS：成功，FAIL：失败，ING：处理中 |
| `code` | `string` | ❌ | `200` | 结果码；200：调账成功，1001：调账处理失败，1002：调账失败,卡号不存在，1003：调账失败,本金余额不足，1004：调账失败,赠送金余额不足 |
| `msg` | `string` | ❌ | `调账成功` | 状态描述 |
| `inner_adjust_no` | `string` | ❌ | `SGCDA190730041652000092` | 内部调账单号 |
| `success` | `boolean` | ❌ | `true` | 表示本次请求是否成功。true:成功,false:失败 |
| `code` | `integer` | ❌ | `200` | 网关返回码，表示本次请求是否成功。200:成功 |
| `message` | `string` | ❌ | `successful` | 网关返回码描述 |
| `request_id` | `string` | ❌ | `` |  |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.adjust/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "request_no": "weixiao20190730001",\n  "mobile": "18972515558",\n  "buyer_id": "1441668074",\n  "card_no": "310201043501229",\n  "adjust_principal": "100",\n  "adjust_bonus": "20",\n  "adjust_type": "1",\n  "remark": "描述TEST",\n  "operator_name": "卫潇",\n  "operator_mobile": "13209******"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.adjust/3.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "request_no": "weixiao20190730001",
    "mobile": "18972515558",
    "buyer_id": "1441668074",
    "card_no": "310201043501229",
    "adjust_principal": "100",
    "adjust_bonus": "20",
    "adjust_type": "1",
    "remark": "描述TEST",
    "operator_name": "卫潇",
    "operator_mobile": "13209******"
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