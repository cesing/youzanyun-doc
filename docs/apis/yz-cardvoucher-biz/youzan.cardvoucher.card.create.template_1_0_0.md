---
apiName: "youzan.cardvoucher.card.create.template.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundOpenService"
method: "create"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, retail_head_high, retail]
deprecated: false
since: "2022-01-17"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3588"
---
# youzan.cardvoucher.card.create.template.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
地址：商家后台-会员-储值规则，创建余额模板或储值卡模板
一个店铺只能创建一个余额模板，可创建多个储值卡模板，储值卡的名字不能重复
仅限连接器项目使用，此接口生成的卡模板部分属性储值内部已写死
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.create.template/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
      "type": "string",
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `kdt_id` | `string` | ✅ 是 | `102129885` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `operator_uid` | `string` | ✅ 是 | `18758285476` | 操作人id，传入注册过有赞的手机号，会自动转换成有赞体系内的id |
| `template_type` | `integer` | ✅ 是 | `1002` | 模板类型：1001 余额模板 1002 储值卡模板 |
| `operator_name` | `string` | ❌ 否 | `fairy` | 操作人名称 |
| `template_name` | `string` | ✅ 是 | `fairy测试储值卡` | 模版名称， |
| `limit_type` | `integer` | ✅ 是 | `0` | 卡模板适用店铺类型：0 所有店铺 1 部分店铺适用 2 部分店铺不适应 |
| `kdt_ids` | `string` | ❌ 否 | `["102129885"]` | 当卡模板适用店铺类型为1/2时必填 |
---
## 3. 响应
**响应参数 Schema**（7 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "创建卡模板接口响应参数"
    },
    "template_no": {
      "type": "string",
      "description": "模版编号",
      "example": "6534123450"
    },
    "success": {
      "type": "string",
      "description": "请求是否成功",
      "example": "true"
    },
    "code": {
      "type": "string",
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
      "type": "string",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 创建卡模板接口响应参数 |
| `template_no` | `string` | ❌ 否 | `6534123450` | 模版编号 |
| `success` | `string` | ❌ 否 | `true` | 请求是否成功 |
| `code` | `string` | ❌ 否 | `200` | 响应码 |
| `message` | `string` | ❌ 否 | `成功` | 响应信息 |
| `request_id` | `string` | ❌ 否 | `0000000000000` | 请求id |
| `error_data` | `string` | ❌ 否 | `错误` | 错误信息 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3588

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "kdt_id": "102129885",
  "operator_uid": "18758285476",
  "template_type": "1002",
  "template_name": "fairy测试储值卡",
  "limit_type": "0"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.create.template/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "kdt_id": "102129885",
  "operator_uid": "18758285476",
  "template_type": "1002",
  "template_name": "fairy测试储值卡",
  "limit_type": "0"
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
| 方法名称 | `create` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3588)_