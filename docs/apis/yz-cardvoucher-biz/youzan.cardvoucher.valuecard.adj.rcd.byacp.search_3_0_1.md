---
apiName: "youzan.cardvoucher.valuecard.adj.rcd.byacp.search.3.0.1"
version: "3.0.1"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardQueryService"
method: "pageQueryAdjustLogByAcceptKdtId"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc]
deprecated: false
since: "2019-03-26"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=539"
---
# youzan.cardvoucher.valuecard.adj.rcd.byacp.search.3.0.1
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
按条件分页查询在该店铺发生的调账记录
版本新增：yz_open_id（有赞开放ID）参数

---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.adj.rcd.byacp.search/3.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（8 个参数）:
```json
{
  "type": "object",
  "properties": {
    "mobile": {
      "type": "string",
      "description": "客户手机号，仅支持国内手机号",
      "example": "18972515558"
    },
    "operator_name": {
      "type": "string",
      "description": "操作员姓名",
      "example": "有赞"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "310201043501229"
    },
    "begin_time": {
      "type": "string",
      "description": "调账时间范围，查询begin_time之后发生的记录，格式：yyyy-MM-dd HH:mm:ss",
      "example": "2019-07-01 00:00:00"
    },
    "end_time": {
      "type": "string",
      "description": "调账时间范围，查询end_time之前发生的记录，格式：yyyy-MM-dd HH:mm:ss",
      "example": "2019-07-31 00:00:00"
    },
    "page": {
      "type": "string",
      "description": "页码，从1开始正整数。如果记录较多请使用时间参数分割",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页条数。默认20条，最大不能超过50，建议使用默认分页。如果记录较多请使用时间参数分割",
      "example": "20"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】",
      "example": "MVJ5w0uy585097513770430464"
    }
  },
  "required": [
    "page",
    "page_size"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `mobile` | `string` | ❌ 否 | `18972515558` | 客户手机号，仅支持国内手机号 |
| `operator_name` | `string` | ❌ 否 | `有赞` | 操作员姓名 |
| `card_no` | `string` | ❌ 否 | `310201043501229` | 卡号 |
| `begin_time` | `string` | ❌ 否 | `2019-07-01 00:00:00` | 调账时间范围，查询begin_time之后发生的记录，格式：yyyy-MM-dd HH:mm:ss |
| `end_time` | `string` | ❌ 否 | `2019-07-31 00:00:00` | 调账时间范围，查询end_time之前发生的记录，格式：yyyy-MM-dd HH:mm:ss |
| `page` | `string` | ✅ 是 | `1` | 页码，从1开始正整数。如果记录较多请使用时间参数分割 |
| `page_size` | `string` | ✅ 是 | `20` | 每页条数。默认20条，最大不能超过50，建议使用默认分页。如果记录较多请使用时间参数分割 |
| `yz_open_id` | `integer` | ❌ 否 | `MVJ5w0uy585097513770430464` | 有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "integer",
      "description": ""
    },
    "paginator": {
      "type": "integer",
      "description": "分页信息"
    },
    "page": {
      "type": "string",
      "description": "页码，从1开始正整数",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页条数。默认20条",
      "example": "20"
    },
    "total_count": {
      "type": "string",
      "description": "查询获得数据总条数",
      "example": "2"
    },
    "items": {
      "type": "array",
      "description": "实体信息"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "18163424"
    },
    "mobile": {
      "type": "string",
      "description": "客户手机号码",
      "example": "18972515558"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "310201043501229"
    },
    "adjust_no": {
      "type": "string",
      "description": "调账单号",
      "example": "CDA190730154114000005"
    },
    "adjust_time": {
      "type": "string",
      "description": "调账时间",
      "example": "2019-07-30 16:14:48"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": 0,
  "paginator": 0,
  "page": "1",
  "page_size": "20",
  "total_count": "2",
  "items": [],
  "kdt_id": "18163424",
  "mobile": "18972515558"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `integer` | ❌ 否 | `` |  |
| `paginator` | `integer` | ❌ 否 | `` | 分页信息 |
| `page` | `string` | ❌ 否 | `1` | 页码，从1开始正整数 |
| `page_size` | `string` | ❌ 否 | `20` | 每页条数。默认20条 |
| `total_count` | `string` | ❌ 否 | `2` | 查询获得数据总条数 |
| `items` | `array` | ❌ 否 | `` | 实体信息 |
| `kdt_id` | `integer` | ❌ 否 | `18163424` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `mobile` | `string` | ❌ 否 | `18972515558` | 客户手机号码 |
| `card_no` | `string` | ❌ 否 | `310201043501229` | 卡号 |
| `adjust_no` | `string` | ❌ 否 | `CDA190730154114000005` | 调账单号 |
| `adjust_time` | `string` | ❌ 否 | `2019-07-30 16:14:48` | 调账时间 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=539

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "page": "1",
  "page_size": "20"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.adj.rcd.byacp.search/3.0.1"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "page": "1",
  "page_size": "20"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardQueryService` |
| 方法名称 | `pageQueryAdjustLogByAcceptKdtId` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=539)_