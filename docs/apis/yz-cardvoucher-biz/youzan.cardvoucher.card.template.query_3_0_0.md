---
apiName: "youzan.cardvoucher.card.template.query.3.0.0"
version: "3.0.0"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.card.TemplateService"
method: "pageQueryTemplateInfo"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail]
deprecated: false
since: "2019-10-28"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=678"
---
# youzan.cardvoucher.card.template.query.3.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
分页查询查询某店铺下的所有未被删除的卡模板信息列表
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.template.query/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "template_type": {
      "type": "integer",
      "description": "模版类型:1001-储值余额模板;1002-储值卡模板",
      "example": "1002"
    },
    "page": {
      "type": "integer",
      "description": "页码，从1开始正整数",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页条数。默认20条，最大不能超过100，建议使用默认分页",
      "example": "10"
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
| `template_type` | `integer` | ❌ 否 | `1002` | 模版类型:1001-储值余额模板;1002-储值卡模板 |
| `page` | `integer` | ✅ 是 | `1` | 页码，从1开始正整数 |
| `page_size` | `integer` | ✅ 是 | `10` | 每页条数。默认20条，最大不能超过100，建议使用默认分页 |
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
      "description": "分页模型"
    },
    "page": {
      "type": "string",
      "description": "页码，从1开始正整数",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页条数。默认20条，最大不能超过100",
      "example": "10"
    },
    "total_count": {
      "type": "string",
      "description": "数据总数",
      "example": "100"
    },
    "items": {
      "type": "array",
      "description": "数据实体"
    },
    "template_no": {
      "type": "string",
      "description": "模版编号",
      "example": "1102009763593"
    },
    "template_type": {
      "type": "integer",
      "description": "模版类型",
      "example": "1001"
    },
    "template_name": {
      "type": "string",
      "description": "模版名称",
      "example": "万物本草"
    },
    "product_total_stock": {
      "type": "integer",
      "description": "模版下商品总库存",
      "example": "100"
    },
    "valid_time_rule": {
      "type": "object",
      "description": "有效期限制"
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
  "page_size": "10",
  "total_count": "100",
  "items": [],
  "template_no": "1102009763593",
  "template_type": "1001"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `integer` | ❌ 否 | `` |  |
| `paginator` | `integer` | ❌ 否 | `` | 分页模型 |
| `page` | `string` | ❌ 否 | `1` | 页码，从1开始正整数 |
| `page_size` | `string` | ❌ 否 | `10` | 每页条数。默认20条，最大不能超过100 |
| `total_count` | `string` | ❌ 否 | `100` | 数据总数 |
| `items` | `array` | ❌ 否 | `` | 数据实体 |
| `template_no` | `string` | ❌ 否 | `1102009763593` | 模版编号 |
| `template_type` | `integer` | ❌ 否 | `1001` | 模版类型 |
| `template_name` | `string` | ❌ 否 | `万物本草` | 模版名称 |
| `product_total_stock` | `integer` | ❌ 否 | `100` | 模版下商品总库存 |
| `valid_time_rule` | `object` | ❌ 否 | `` | 有效期限制 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=678

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "page": "1",
  "page_size": "10"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.template.query/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "page": "1",
  "page_size": "10"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.card.TemplateService` |
| 方法名称 | `pageQueryTemplateInfo` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=678)_