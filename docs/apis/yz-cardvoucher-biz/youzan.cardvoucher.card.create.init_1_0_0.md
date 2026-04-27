---
apiName: "youzan.cardvoucher.card.create.init.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.open.GiftCardOpenService"
method: "createCard"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, retail_head_high, retail_head, edu, edu_head, 1]
deprecated: false
since: "2022-11-16"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3926"
---
# youzan.cardvoucher.card.create.init.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
储值礼品卡制卡接口，会创建未激活的礼品卡且没有归属人，该礼品卡可以在商家后台 储值查询-卡查询中根据返回的卡号查询信息
一般配合youzan.cardvoucher.giftcard.marketing.issue接口进行后续的发卡使用
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.create.init/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` | 请求参数 |
| `request_no` | `string` | ✅ 是 | `Unique123456` | 请求单号，是幂等单号要求唯一 |
| `template_no` | `string` | ✅ 是 | `11111111` | 卡模板号 |
| `img_url_no` | `integer` | ❌ 否 | `1` | 制卡卡模板选择第几个封面，从1开始计数，可不填，不填默认取第一个封面图片 |
| `price` | `integer` | ❌ 否 | `100` | 制卡卡模板选择的面额，单位分，不传默认取最小的面额 |
| `operator_name` | `string` | ✅ 是 | `aaa` | 操作员姓名 |
| `operator_mobile` | `string` | ✅ 是 | `12345678901` | 操作员手机号 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
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
      "type": "string",
      "description": "网关返回码，表示本次请求是否成功。200 成功",
      "example": "200"
    },
    "msg": {
      "type": "string",
      "description": "状态描述",
      "example": "制卡成功"
    },
    "success": {
      "type": "string",
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
  "request_no": "Unique123456",
  "card_no": "987654321",
  "status": "SUCCESS",
  "code": "200",
  "msg": "制卡成功",
  "success": "true"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 接口返回数据 |
| `request_no` | `string` | ❌ 否 | `Unique123456` | 请求单号 |
| `card_no` | `string` | ❌ 否 | `987654321` | 制成的卡号 |
| `status` | `string` | ❌ 否 | `SUCCESS` | 制卡状态SUCCESS:成功FAIL:失败ING:制卡中 |
| `code` | `string` | ❌ 否 | `200` | 结果码 |
| `msg` | `string` | ❌ 否 | `制卡成功` | 状态描述 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200 成功 |
| `message` | `string` | ❌ 否 | `successful` | 网关返回码描述 |
| `request_id` | `string` | ❌ 否 | `` |  |
| `error_data` | `string` | ❌ 否 | `` |  |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3926

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "request_no": "Unique123456",
  "template_no": "11111111",
  "operator_name": "aaa",
  "operator_mobile": "12345678901"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.create.init/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "request_no": "Unique123456",
  "template_no": "11111111",
  "operator_name": "aaa",
  "operator_mobile": "12345678901"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.open.GiftCardOpenService` |
| 方法名称 | `createCard` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3926)_