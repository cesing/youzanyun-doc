---
apiName: "youzan.cardvoucher.product.card.query.info.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService"
method: "pageQueryProductCardList"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2021-05-12"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=2830"
---
# youzan.cardvoucher.product.card.query.info.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
分页查询主卡下的子卡信息，默认查询处于正常状态下的子卡信息
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.product.card.query.info/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "group_no": {
      "type": "string",
      "description": "主卡号",
      "example": "310200462159949"
    },
    "status": {
      "type": "integer",
      "description": "子卡状态：0-初始化；1-正常；2-已回收（失效）；3-已核销；4-被冻结（改状态暂没有使用）；5-激活失败；6-无效卡（作废），默认取值1",
      "example": "1"
    },
    "page_no": {
      "type": "integer",
      "description": "页号，默认取1，取值区间是[1,200]",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "分页大小，默认取10，取值区间是[1,50]",
      "example": "10"
    }
  },
  "required": [
    "group_no"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `group_no` | `string` | ✅ 是 | `310200462159949` | 主卡号 |
| `status` | `integer` | ❌ 否 | `1` | 子卡状态：0-初始化；1-正常；2-已回收（失效）；3-已核销；4-被冻结（改状态暂没有使用）；5-激活失败；6-无效卡 |
| `page_no` | `integer` | ❌ 否 | `1` | 页号，默认取1，取值区间是[1,200] |
| `page_size` | `integer` | ❌ 否 | `10` | 分页大小，默认取10，取值区间是[1,50] |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "integer",
      "description": "返回结果"
    },
    "paginator": {
      "type": "integer",
      "description": "分页信息"
    },
    "page_no": {
      "type": "string",
      "description": "页号",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "分页大小",
      "example": "10"
    },
    "total_count": {
      "type": "string",
      "description": "数据总数",
      "example": "1"
    },
    "items": {
      "type": "array",
      "description": "数据"
    },
    "card_no": {
      "type": "string",
      "description": "子卡号",
      "example": "210200462162308"
    },
    "create_time": {
      "type": "string",
      "description": "创建时间",
      "example": "1620791833000"
    },
    "balance": {
      "type": "number",
      "description": "余额（元）",
      "example": "10.0"
    },
    "success": {
      "type": "string",
      "description": "接口调用是否成功",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "接口调用结果码",
      "example": "200"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": 0,
  "paginator": 0,
  "page_no": "1",
  "page_size": "10",
  "total_count": "1",
  "items": [],
  "card_no": "210200462162308",
  "create_time": "1620791833000"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `integer` | ❌ 否 | `` | 返回结果 |
| `paginator` | `integer` | ❌ 否 | `` | 分页信息 |
| `page_no` | `string` | ❌ 否 | `1` | 页号 |
| `page_size` | `string` | ❌ 否 | `10` | 分页大小 |
| `total_count` | `string` | ❌ 否 | `1` | 数据总数 |
| `items` | `array` | ❌ 否 | `` | 数据 |
| `card_no` | `string` | ❌ 否 | `210200462162308` | 子卡号 |
| `create_time` | `string` | ❌ 否 | `1620791833000` | 创建时间 |
| `balance` | `number` | ❌ 否 | `10.0` | 余额（元） |
| `success` | `string` | ❌ 否 | `true` | 接口调用是否成功 |
| `code` | `string` | ❌ 否 | `200` | 接口调用结果码 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=2830

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "group_no": "310200462159949"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.product.card.query.info/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "group_no": "310200462159949"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundQueryOpenService` |
| 方法名称 | `pageQueryProductCardList` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=2830)_