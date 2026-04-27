---
apiName: "youzan.cardvoucher.giftcard.query.buyercenter.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.open.ProductOpenService"
method: "pageQueryBuyCenter"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, retail, wsc, retail_head, retail_online, retail_head_high, retail_online_lite, retail_offline, 1]
deprecated: false
since: "2023-05-08"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4058"
---
# youzan.cardvoucher.giftcard.query.buyercenter.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
礼品卡分页查询：可分页查询礼品卡列表。与个人中心->余额->礼品卡->购买礼品卡页面中的查询效果一致。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buyercenter/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "page": {
      "type": "string",
      "description": "页码，从1开始",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "页数。默认10条，最大不能超过50，建议使用默认分页",
      "example": "10"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `page` | `string` | ❌ 否 | `1` | 页码，从1开始 |
| `page_size` | `string` | ❌ 否 | `10` | 页数。默认10条，最大不能超过50，建议使用默认分页 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "integer",
      "description": "数据"
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
      "description": "页数。默认10条",
      "example": "10"
    },
    "total_count": {
      "type": "string",
      "description": "查询获得数据总条数",
      "example": "2"
    },
    "items": {
      "type": "array",
      "description": "卡信息"
    },
    "template_name": {
      "type": "string",
      "description": "卡名称",
      "example": "礼品卡"
    },
    "template_img": {
      "type": "string",
      "description": "封面图片",
      "example": "https://img01.yzcdn.cn/upload_files/2023/02/16/Fkv8lU-C6PDnceu_RbmnPMGsLs5n.png"
    },
    "max_original_price": {
      "type": "integer",
      "description": "卡最高面额(单位:分)",
      "example": "100000"
    },
    "min_original_price": {
      "type": "integer",
      "description": "卡最低面额(单位:分)",
      "example": "100000"
    },
    "template_no": {
      "type": "string",
      "description": "卡模板Id",
      "example": "110200549443060"
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
  "total_count": "2",
  "items": [],
  "template_name": "礼品卡",
  "template_img": "https://img01.yzcdn.cn/upload_files/2023/02/16/Fkv8lU-C6PDnceu_RbmnPMGsLs5n.png"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `integer` | ❌ 否 | `` | 数据 |
| `paginator` | `integer` | ❌ 否 | `` | 分页信息 |
| `page` | `string` | ❌ 否 | `1` | 页码，从1开始正整数 |
| `page_size` | `string` | ❌ 否 | `10` | 页数。默认10条 |
| `total_count` | `string` | ❌ 否 | `2` | 查询获得数据总条数 |
| `items` | `array` | ❌ 否 | `` | 卡信息 |
| `template_name` | `string` | ❌ 否 | `礼品卡` | 卡名称 |
| `template_img` | `string` | ❌ 否 | `https://img01.yzcdn.cn/upload_` | 封面图片 |
| `max_original_price` | `integer` | ❌ 否 | `100000` | 卡最高面额(单位:分) |
| `min_original_price` | `integer` | ❌ 否 | `100000` | 卡最低面额(单位:分) |
| `template_no` | `string` | ❌ 否 | `110200549443060` | 卡模板Id |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4058

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buyercenter/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {}

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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.open.ProductOpenService` |
| 方法名称 | `pageQueryBuyCenter` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4058)_