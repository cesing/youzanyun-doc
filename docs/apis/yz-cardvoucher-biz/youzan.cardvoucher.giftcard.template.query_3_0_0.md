---
apiName: "youzan.cardvoucher.giftcard.template.query.3.0.0"
version: "3.0.0"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "gift_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.giftcard.GiftCardService"
method: "queryCardInfoByTemplateNo"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail]
deprecated: false
since: "2019-09-02"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=607"
---
# youzan.cardvoucher.giftcard.template.query.3.0.0
> **所属分组**: gift_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
根据卡模板号分页查询卡信息列表
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.template.query/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": ""
    },
    "template_no": {
      "type": "string",
      "description": "礼品卡模板号",
      "example": "110101052959023"
    },
    "status": {
      "type": "string",
      "description": "礼品卡状态，未兑换：UNCONVERTED 已兑换：CONVERTED 已激活：ACTIVATED 不可用：UNAVAILABLE",
      "example": "UNCONVERTED"
    },
    "page": {
      "type": "string",
      "description": "页码，从1开始正整数",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页条数。默认20条，最大不能超过50，建议使用默认分页",
      "example": "20"
    }
  },
  "required": [
    "template_no",
    "page",
    "page_size"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` |  |
| `template_no` | `string` | ✅ 是 | `110101052959023` | 礼品卡模板号 |
| `status` | `string` | ❌ 否 | `UNCONVERTED` | 礼品卡状态，未兑换：UNCONVERTED 已兑换：CONVERTED 已激活：ACTIVATED 不可用：UNAVAI |
| `page` | `string` | ✅ 是 | `1` | 页码，从1开始正整数 |
| `page_size` | `string` | ✅ 是 | `20` | 每页条数。默认20条，最大不能超过50，建议使用默认分页 |
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
      "description": "每页条数。默认20条",
      "example": "10"
    },
    "total_count": {
      "type": "string",
      "description": "查询数据总条数",
      "example": "100"
    },
    "items": {
      "type": "array",
      "description": "数据实体"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "310100029297523"
    },
    "template_no": {
      "type": "string",
      "description": "模板号",
      "example": "1101001241004"
    },
    "status": {
      "type": "string",
      "description": "礼品卡状态，未兑换：UNCONVERTED 已兑换：CONVERTED 已激活：ACTIVATED 不可用：UNAVAILABLE",
      "example": "UNAVAILABLE"
    },
    "owner_uid": {
      "type": "integer",
      "description": "卡片拥有人Id",
      "example": "677009"
    },
    "source": {
      "type": "integer",
      "description": "来源：1-通过批量制卡生成的礼品卡，2-通过推广链接购买的礼品卡",
      "example": "1"
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
  "card_no": "310100029297523",
  "template_no": "1101001241004"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `integer` | ❌ 否 | `` |  |
| `paginator` | `integer` | ❌ 否 | `` | 分页模型 |
| `page` | `string` | ❌ 否 | `1` | 页码，从1开始正整数 |
| `page_size` | `string` | ❌ 否 | `10` | 每页条数。默认20条 |
| `total_count` | `string` | ❌ 否 | `100` | 查询数据总条数 |
| `items` | `array` | ❌ 否 | `` | 数据实体 |
| `card_no` | `string` | ❌ 否 | `310100029297523` | 卡号 |
| `template_no` | `string` | ❌ 否 | `1101001241004` | 模板号 |
| `status` | `string` | ❌ 否 | `UNAVAILABLE` | 礼品卡状态，未兑换：UNCONVERTED 已兑换：CONVERTED 已激活：ACTIVATED 不可用：UNAVAI |
| `owner_uid` | `integer` | ❌ 否 | `677009` | 卡片拥有人Id |
| `source` | `integer` | ❌ 否 | `1` | 来源：1-通过批量制卡生成的礼品卡，2-通过推广链接购买的礼品卡 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=607

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "template_no": "110101052959023",
  "page": "1",
  "page_size": "20"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.template.query/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "template_no": "110101052959023",
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.giftcard.GiftCardService` |
| 方法名称 | `queryCardInfoByTemplateNo` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=607)_