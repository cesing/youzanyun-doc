---
apiName: "youzan.bigdata.datacenter.psmanage.search.pagepsdata.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
method: "fetchPsPageSourceDetail"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-01-06"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3570"
---
# youzan.bigdata.datacenter.psmanage.search.pagepsdata.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter
---
## 1. 场景说明
分页获取多个人推广监控效果数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagepsdata/1.0.0`
**请求参数 Schema**（8 个参数）:
```json
{
  "type": "object",
  "properties": {
    "dcps_list": {
      "type": "array",
      "description": "dcps号",
      "example": "[\"2118722746287589378.200001\"]"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页条数。最大不能超过200",
      "example": "1"
    },
    "attribution_period": {
      "type": "integer",
      "description": "归因周期当天:1,七天:7,15天:15,30天:30",
      "example": "1"
    },
    "statistical_scope": {
      "type": "integer",
      "description": "统计范围全部转化数据：空，推广页直接转化数据：2，连带销售：3",
      "example": "2"
    },
    "attribution_type": {
      "type": "integer",
      "description": "归因方式首次1，末次2",
      "example": "1"
    },
    "start_day": {
      "type": "string",
      "description": "开始时间yyyy-MM-dd",
      "example": "2021-12-01"
    },
    "end_day": {
      "type": "string",
      "description": "结束时间yyyy-MM-dd",
      "example": "2021-12-02"
    }
  },
  "required": [
    "page_no",
    "page_size",
    "attribution_period",
    "attribution_type",
    "start_day",
    "end_day"
  ]
}
```
**请求参数明细**（8 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `dcps_list` | `array` | ❌ | `["2118722746287589378.200001"]` | dcps号 |
| `page_no` | `integer` | ✅ | `1` | 页码 |
| `page_size` | `integer` | ✅ | `1` | 每页条数。最大不能超过200 |
| `attribution_period` | `integer` | ✅ | `1` | 归因周期当天:1,七天:7,15天:15,30天:30 |
| `statistical_scope` | `integer` | ❌ | `2` | 统计范围全部转化数据：空，推广页直接转化数据：2，连带销售：3 |
| `attribution_type` | `integer` | ✅ | `1` | 归因方式首次1，末次2 |
| `start_day` | `string` | ✅ | `2021-12-01` | 开始时间yyyy-MM-dd |
| `end_day` | `string` | ✅ | `2021-12-02` | 结束时间yyyy-MM-dd |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "结果数据"
    },
    "paginator": {
      "type": "string",
      "description": "分页信息"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页条数",
      "example": "10"
    },
    "total_count": {
      "type": "integer",
      "description": "总条数",
      "example": "100"
    },
    "items": {
      "type": "array",
      "description": "结果列表"
    },
    "dcps": {
      "type": "string",
      "description": "推广监控唯一标识",
      "example": "2118722746287589378.200001"
    },
    "ps_name": {
      "type": "string",
      "description": "推广监控名称",
      "example": "微信推广"
    },
    "channel_name": {
      "type": "string",
      "description": "所属渠道名称",
      "example": "微信"
    },
    "tag_name": {
      "type": "string",
      "description": "所属标签名称",
      "example": "推广标签"
    },
    "ps_cost": {
      "type": "integer",
      "description": "推广花费",
      "example": "10"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "paginator": "",
  "page_no": "1",
  "page_size": "10",
  "total_count": "100",
  "items": [],
  "dcps": "2118722746287589378.200001",
  "ps_name": "微信推广"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 结果数据 |
| `paginator` | `string` | ❌ | `` | 分页信息 |
| `page_no` | `integer` | ❌ | `1` | 页码 |
| `page_size` | `integer` | ❌ | `10` | 每页条数 |
| `total_count` | `integer` | ❌ | `100` | 总条数 |
| `items` | `array` | ❌ | `` | 结果列表 |
| `dcps` | `string` | ❌ | `2118722746287589378.200001` | 推广监控唯一标识 |
| `ps_name` | `string` | ❌ | `微信推广` | 推广监控名称 |
| `channel_name` | `string` | ❌ | `微信` | 所属渠道名称 |
| `tag_name` | `string` | ❌ | `推广标签` | 所属标签名称 |
| `ps_cost` | `integer` | ❌ | `10` | 推广花费 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagepsdata/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "dcps_list": "[\"2118722746287589378.200001\"]",\n  "page_no": "1",\n  "page_size": "1",\n  "attribution_period": "1",\n  "statistical_scope": "2",\n  "attribution_type": "1",\n  "start_day": "2021-12-01",\n  "end_day": "2021-12-02"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagepsdata/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "dcps_list": "[\"2118722746287589378.200001\"]",
    "page_no": "1",
    "page_size": "1",
    "attribution_period": "1",
    "statistical_scope": "2",
    "attribution_type": "1",
    "start_day": "2021-12-01",
    "end_day": "2021-12-02"
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