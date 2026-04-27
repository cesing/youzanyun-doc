---
apiName: "youzan.cardvoucher.valuecard.fund.adjust.3.0.0"
version: "3.0.0"
status: "已上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundOpenService"
method: "adjust"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail]
deprecated: false
since: "2019-03-22"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=199"
---
# youzan.cardvoucher.valuecard.fund.adjust.3.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线
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
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（11 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` |  |
| `request_no` | `string` | ✅ 是 | `weixiao20190730001` | 请求号，请确保唯一（长度不超过24个字符） |
| `mobile` | `string` | ❌ 否 | `18972515558` | 客户手机号码（mobile或者buyer_id二选一） |
| `buyer_id` | `integer` | ❌ 否 | `1441668074` | 客户Id（mobile或者buyer_id二选一） |
| `card_no` | `string` | ✅ 是 | `310201043501229` | 卡号 |
| `adjust_principal` | `integer` | ❌ 否 | `100` | 调整本金金额，单位：分 |
| `adjust_bonus` | `integer` | ❌ 否 | `20` | 调整赠送金金额，单位：分 |
| `adjust_type` | `integer` | ✅ 是 | `1` | 调账类型；1：调增，2：调减 |
| `remark` | `string` | ❌ 否 | `描述TEST` | 描述 |
| `operator_name` | `string` | ✅ 是 | `卫潇` | 操作员姓名 |
| `operator_mobile` | `string` | ✅ 是 | `13209******` | 操作员手机号 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
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
      "type": "string",
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
      "type": "string",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `request_no` | `string` | ❌ 否 | `weixiao20190730001` | 请求号 |
| `adjust_no` | `string` | ❌ 否 | `CDA190730041652000092` | 调账单号 |
| `status` | `string` | ❌ 否 | `SUCCESS` | 调账状态；SUCCESS：成功，FAIL：失败，ING：处理中 |
| `code` | `string` | ❌ 否 | `200` | 结果码；200：调账成功，1001：调账处理失败，1002：调账失败,卡号不存在，1003：调账失败,本金余额不足，10 |
| `msg` | `string` | ❌ 否 | `调账成功` | 状态描述 |
| `inner_adjust_no` | `string` | ❌ 否 | `SGCDA190730041652000092` | 内部调账单号 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。true:成功,false:失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200:成功 |
| `message` | `string` | ❌ 否 | `successful` | 网关返回码描述 |
| `request_id` | `string` | ❌ 否 | `` |  |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=199

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "request_no": "weixiao20190730001",
  "card_no": "310201043501229",
  "adjust_type": "1",
  "operator_name": "卫潇",
  "operator_mobile": "13209******"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.adjust/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "request_no": "weixiao20190730001",
  "card_no": "310201043501229",
  "adjust_type": "1",
  "operator_name": "卫潇",
  "operator_mobile": "13209******"
}

response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

> ⚠️ **注意**：以上为示例代码，`access_token` 需要通过 OAuth2.0 流程获取。
> 真实调用地址和参数请以管理后台详情页为准。

---
## 5. 错误码
## 错误码

| 错误码 | 说明 | 处理建议 |
|--------|------|----------|
| 1000 | 系统内部错误 | 稍后重试或联系技术支持 |
| 1001 | 鉴权失败 | 检查 access_token 是否有效 |
| 1002 | 参数校验失败 | 检查必填参数是否完整 |
| 1003 | 权限不足 | 确认应用已开通对应接口权限 |
| 1004 | 频率超限 | 降低请求频率或申请更高配额 |
| 1005 | 资源不存在 | 检查请求的业务 ID 是否正确 |
| 1006 | 请求超时 | 增加超时时间或稍后重试 |
| 1007 | 账户欠费 | 完成账户充值后重试 |

> 更多错误码请参考：[有赞云错误码文档](https://doc.youzanyun.com) |

---
## 6. 内部服务信息
| 字段 | 值 |
|------|---|
| 协议类型 | dubbo |
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundOpenService` |
| 方法名称 | `adjust` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=199)_