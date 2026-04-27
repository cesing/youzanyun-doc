---
apiName: "youzan.cardvoucher.giftcard.query.buyercenter.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "pageQueryBuyCenter"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-05-08"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4058"
---
# youzan.cardvoucher.giftcard.query.buyercenter.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
礼品卡分页查询：可分页查询礼品卡列表。与个人中心->余额->礼品卡->购买礼品卡页面中的查询效果一致。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buyercenter/1.0.0`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "page": {
      "type": "integer",
      "description": "页码，从1开始",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "页数。默认10条，最大不能超过50，建议使用默认分页",
      "example": "10"
    }
  },
  "required": []
}
```
**请求参数明细**（2 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `page` | `integer` | ❌ | `1` | 页码，从1开始 |
| `page_size` | `integer` | ❌ | `10` | 页数。默认10条，最大不能超过50，建议使用默认分页 |
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
      "type": "integer",
      "description": "页码，从1开始正整数",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "页数。默认10条",
      "example": "10"
    },
    "total_count": {
      "type": "integer",
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
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `integer` | ❌ | `` | 数据 |
| `paginator` | `integer` | ❌ | `` | 分页信息 |
| `page` | `integer` | ❌ | `1` | 页码，从1开始正整数 |
| `page_size` | `integer` | ❌ | `10` | 页数。默认10条 |
| `total_count` | `integer` | ❌ | `2` | 查询获得数据总条数 |
| `items` | `array` | ❌ | `` | 卡信息 |
| `template_name` | `string` | ❌ | `礼品卡` | 卡名称 |
| `template_img` | `string` | ❌ | `https://img01.yzcdn.cn/upload_files/2023` | 封面图片 |
| `max_original_price` | `integer` | ❌ | `100000` | 卡最高面额(单位:分) |
| `min_original_price` | `integer` | ❌ | `100000` | 卡最低面额(单位:分) |
| `template_no` | `string` | ❌ | `110200549443060` | 卡模板Id |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buyercenter/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "page": "1",\n  "page_size": "10"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.query.buyercenter/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "page": "1",
    "page_size": "10"
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