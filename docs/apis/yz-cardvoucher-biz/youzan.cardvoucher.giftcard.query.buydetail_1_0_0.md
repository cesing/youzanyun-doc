---
apiName: "youzan.cardvoucher.giftcard.query.buydetail.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.open.DealOpenService"
method: "queryBuyDetail"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, retail, retail_head_high, retail_online, retail_online_lite, retail_offline, retail_head, 1]
deprecated: false
since: "2023-05-09"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4065"
---
# youzan.cardvoucher.giftcard.query.buydetail.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
礼品卡模板详情查询：可分页查询礼品卡模板详细信息。与个人中心->余额->礼品卡->购买礼品卡->礼品卡模板详细页面中的查询效果一致。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buydetail/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（1 个参数）:
```json
{
  "type": "object",
  "properties": {
    "template_no": {
      "type": "string",
      "description": "模版号",
      "example": "110204008016011"
    }
  },
  "required": [
    "template_no"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `template_no` | `string` | ✅ 是 | `110204008016011` | 模版号 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "数据"
    },
    "template_name": {
      "type": "string",
      "description": "模板名称",
      "example": "礼品卡"
    },
    "template_img": {
      "type": "string",
      "description": "模板背景图片",
      "example": "https://img01.yzcdn.cn/upload_files/2023/02/06/FmHkosO7YgMI7h1KdDM7QcnEr7gE.png"
    },
    "instructions": {
      "type": "string",
      "description": "使用须知",
      "example": "购卡成功后，你可选择自己使用或赠送给朋友"
    },
    "product_infos": {
      "type": "array",
      "description": "卡面对应商品详细信息"
    },
    "original_price": {
      "type": "integer",
      "description": "原始单价，单位：分",
      "example": "10000"
    },
    "sale_price": {
      "type": "integer",
      "description": "实际销售单价，单位：分",
      "example": "8000"
    },
    "stock": {
      "type": "integer",
      "description": "库存 ，单位：张",
      "example": "79"
    },
    "gift_packs": {
      "type": "array",
      "description": "礼包信息"
    },
    "rule_rights": {
      "type": "object",
      "description": "规则权益"
    },
    "coupon_rights": {
      "type": "array",
      "description": "优惠券权益列表"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "template_name": "礼品卡",
  "template_img": "https://img01.yzcdn.cn/upload_files/2023/02/06/FmHkosO7YgMI7h1KdDM7QcnEr7gE.png",
  "instructions": "购卡成功后，你可选择自己使用或赠送给朋友",
  "product_infos": [],
  "original_price": "10000",
  "sale_price": "8000",
  "stock": "79"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` | 数据 |
| `template_name` | `string` | ❌ 否 | `礼品卡` | 模板名称 |
| `template_img` | `string` | ❌ 否 | `https://img01.yzcdn.cn/upload_` | 模板背景图片 |
| `instructions` | `string` | ❌ 否 | `购卡成功后，你可选择自己使用或赠送给朋友` | 使用须知 |
| `product_infos` | `array` | ❌ 否 | `` | 卡面对应商品详细信息 |
| `original_price` | `integer` | ❌ 否 | `10000` | 原始单价，单位：分 |
| `sale_price` | `integer` | ❌ 否 | `8000` | 实际销售单价，单位：分 |
| `stock` | `integer` | ❌ 否 | `79` | 库存 ，单位：张 |
| `gift_packs` | `array` | ❌ 否 | `` | 礼包信息 |
| `rule_rights` | `object` | ❌ 否 | `` | 规则权益 |
| `coupon_rights` | `array` | ❌ 否 | `` | 优惠券权益列表 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4065

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "template_no": "110204008016011"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buydetail/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "template_no": "110204008016011"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.open.DealOpenService` |
| 方法名称 | `queryBuyDetail` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4065)_