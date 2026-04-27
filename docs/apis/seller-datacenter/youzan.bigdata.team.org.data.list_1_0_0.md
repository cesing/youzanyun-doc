---
apiName: "youzan.bigdata.team.org.data.list.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "trade"
serviceName: "com.youzan.bigdata.datacenter.proxy.api.service.retailreport.ShopDataReportService"
method: "getSpecialFacadeShopReportData"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offline, retail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_head, edu_branch, hotel, wecom_assistant]
deprecated: false
since: "2022-06-06"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3785"
---
# youzan.bigdata.team.org.data.list.1.0.0
> **所属分组**: trade　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
云上专柜定制交易数据报表
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.team.org.data.list/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `team_org_ids` | `integer` | ✅ 是 | `[111,222]` | 专柜id列表 |
| `start_date` | `string` | ✅ 是 | `2022-05-01` | 开始时间 |
| `end_date` | `string` | ✅ 是 | `2022-07-01` | 结束时间 |
| `page` | `integer` | ✅ 是 | `1` | 查询页 |
| `page_size` | `integer` | ✅ 是 | `20` | 每页条目数 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "调用返回的异步结果数据,"
    },
    "response_id": {
      "type": "string",
      "description": "请求返回标识，用于当status=0时，轮询查询",
      "example": "1111111"
    },
    "result": {
      "type": "object",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 调用返回的异步结果数据, |
| `response_id` | `string` | ❌ 否 | `1111111` | 请求返回标识，用于当status=0时，轮询查询 |
| `result` | `object` | ❌ 否 | `` | 请求结果，当status=1时，有结果， |
| `special_facade_report_detail_models` | `array` | ❌ 否 | `` | 数据对象 |
| `parent_org_id` | `string` | ❌ 否 | `父专柜id` | 父专柜id，通过"_"拼接 |
| `parent_team_org_name` | `string` | ❌ 否 | `父机构名称（区域名称）` | 父专柜id名称，多级拼接 |
| `team_org_id` | `string` | ❌ 否 | `专柜id` | 专柜id |
| `team_org_name` | `string` | ❌ 否 | `专柜名称` | 专柜名称 |
| `per_customer_price` | `integer` | ❌ 否 | `客单价` | 客单价 |
| `book_customer_num` | `integer` | ❌ 否 | `下单人数` | 下单人数 |
| `book_order_num` | `integer` | ❌ 否 | `下单笔数` | 下单笔数 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3785

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "team_org_ids": "[111,222]",
  "start_date": "2022-05-01",
  "end_date": "2022-07-01",
  "page": "1",
  "page_size": "20"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.team.org.data.list/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "team_org_ids": "[111,222]",
  "start_date": "2022-05-01",
  "end_date": "2022-07-01",
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
| 服务名称 | `com.youzan.bigdata.datacenter.proxy.api.service.retailreport.ShopDataReportService` |
| 方法名称 | `getSpecialFacadeShopReportData` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3785)_