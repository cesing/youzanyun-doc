---
apiName: "youzan.bigdata.team.org.data.list.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "trade"
method: "getSpecialFacadeShopReportData"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-06-06"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3785"
---
# youzan.bigdata.team.org.data.list.1.0.0
> **所属分组**: trade　**所属应用**: seller-datacenter
---
## 1. 场景说明
云上专柜定制交易数据报表
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.team.org.data.list/1.0.0`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "team_org_ids": {
      "type": "integer",
      "description": "专柜id列表",
      "example": "[111,222]"
    },
    "start_date": {
      "type": "string",
      "description": "开始时间",
      "example": "2022-05-01"
    },
    "end_date": {
      "type": "string",
      "description": "结束时间",
      "example": "2022-07-01"
    },
    "page": {
      "type": "integer",
      "description": "查询页",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页条目数",
      "example": "20"
    }
  },
  "required": [
    "team_org_ids",
    "start_date",
    "end_date",
    "page",
    "page_size"
  ]
}
```
**请求参数明细**（5 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `team_org_ids` | `integer` | ✅ | `[111,222]` | 专柜id列表 |
| `start_date` | `string` | ✅ | `2022-05-01` | 开始时间 |
| `end_date` | `string` | ✅ | `2022-07-01` | 结束时间 |
| `page` | `integer` | ✅ | `1` | 查询页 |
| `page_size` | `integer` | ✅ | `20` | 每页条目数 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "调用返回的异步结果数据,"
    },
    "response_id": {
      "type": "string",
      "description": "请求返回标识，用于当status=0时，轮询查询",
      "example": "1111111"
    },
    "result": {
      "type": "string",
      "description": "请求结果，当status=1时，有结果，"
    },
    "special_facade_report_detail_models": {
      "type": "array",
      "description": "数据对象"
    },
    "parent_org_id": {
      "type": "string",
      "description": "父专柜id，通过\"_\"拼接",
      "example": "父专柜id"
    },
    "parent_team_org_name": {
      "type": "string",
      "description": "父专柜id名称，多级拼接",
      "example": "父机构名称（区域名称）"
    },
    "team_org_id": {
      "type": "string",
      "description": "专柜id",
      "example": "专柜id"
    },
    "team_org_name": {
      "type": "string",
      "description": "专柜名称",
      "example": "专柜名称"
    },
    "per_customer_price": {
      "type": "integer",
      "description": "客单价",
      "example": "客单价"
    },
    "book_customer_num": {
      "type": "integer",
      "description": "下单人数",
      "example": "下单人数"
    },
    "book_order_num": {
      "type": "integer",
      "description": "下单笔数",
      "example": "下单笔数"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "response_id": "1111111",
  "result": "",
  "special_facade_report_detail_models": [],
  "parent_org_id": "父专柜id",
  "parent_team_org_name": "父机构名称（区域名称）",
  "team_org_id": "专柜id",
  "team_org_name": "专柜名称"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 调用返回的异步结果数据, |
| `response_id` | `string` | ❌ | `1111111` | 请求返回标识，用于当status=0时，轮询查询 |
| `result` | `string` | ❌ | `` | 请求结果，当status=1时，有结果， |
| `special_facade_report_detail_models` | `array` | ❌ | `` | 数据对象 |
| `parent_org_id` | `string` | ❌ | `父专柜id` | 父专柜id，通过"_"拼接 |
| `parent_team_org_name` | `string` | ❌ | `父机构名称（区域名称）` | 父专柜id名称，多级拼接 |
| `team_org_id` | `string` | ❌ | `专柜id` | 专柜id |
| `team_org_name` | `string` | ❌ | `专柜名称` | 专柜名称 |
| `per_customer_price` | `integer` | ❌ | `客单价` | 客单价 |
| `book_customer_num` | `integer` | ❌ | `下单人数` | 下单人数 |
| `book_order_num` | `integer` | ❌ | `下单笔数` | 下单笔数 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.team.org.data.list/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "team_org_ids": "[111,222]",\n  "start_date": "2022-05-01",\n  "end_date": "2022-07-01",\n  "page": "1",\n  "page_size": "20"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.team.org.data.list/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "team_org_ids": "[111,222]",
    "start_date": "2022-05-01",
    "end_date": "2022-07-01",
    "page": "1",
    "page_size": "20"
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