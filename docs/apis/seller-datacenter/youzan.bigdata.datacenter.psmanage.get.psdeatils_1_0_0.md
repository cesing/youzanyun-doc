---
apiName: "youzan.bigdata.datacenter.psmanage.get.psdeatils.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
method: "getPsDetailData"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-12-14"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3485"
---
# youzan.bigdata.datacenter.psmanage.get.psdeatils.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter
---
## 1. 场景说明
获取单个推广监控数据详情(包含明细和汇总)
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psdeatils/1.0.0`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "ps_code": {
      "type": "string",
      "description": "dcps号",
      "example": "2118722746287589378.200001"
    },
    "attribution_period": {
      "type": "integer",
      "description": "归因周期当天:1,七天:7,15天:15,30天:30@seePsAttributionPeriodEnum",
      "example": "1"
    },
    "statistical_scope": {
      "type": "integer",
      "description": "统计范围全部转化数据：空，推广页直接转化数据：2，连带销售：3@seePsStatisticalScopeTypeEnum",
      "example": "1"
    },
    "attribution_type": {
      "type": "integer",
      "description": "归因方式首次1，末次2@seePsAttributionTypeEnum",
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
    },
    "node_kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。连锁总部查询汇总数据不传该字段",
      "example": "88888"
    }
  },
  "required": [
    "ps_code",
    "attribution_period",
    "attribution_type",
    "start_day",
    "end_day"
  ]
}
```
**请求参数明细**（7 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `ps_code` | `string` | ✅ | `2118722746287589378.200001` | dcps号 |
| `attribution_period` | `integer` | ✅ | `1` | 归因周期当天:1,七天:7,15天:15,30天:30@seePsAttributionPeriodEnum |
| `statistical_scope` | `integer` | ❌ | `1` | 统计范围全部转化数据：空，推广页直接转化数据：2，连带销售：3@seePsStatisticalScopeTypeEnum |
| `attribution_type` | `integer` | ✅ | `1` | 归因方式首次1，末次2@seePsAttributionTypeEnum |
| `start_day` | `string` | ✅ | `2021-12-01` | 开始时间yyyy-MM-dd |
| `end_day` | `string` | ✅ | `2021-12-02` | 结束时间yyyy-MM-dd |
| `node_kdt_id` | `integer` | ❌ | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。连锁总部查询汇总数据不传该字段 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "结果"
    },
    "summary_data": {
      "type": "string",
      "description": "汇总数据这里会给算一遍,实时数据的UV之类要去重，并不是明细数据相加"
    },
    "time": {
      "type": "string",
      "description": "按日期维度的详细数据，如果是今日实时，则小时展示为0,1……,22,23如果是天，则key为2018-01-01",
      "example": "all"
    },
    "pv": {
      "type": "integer",
      "description": "浏览量",
      "example": "1"
    },
    "uv": {
      "type": "integer",
      "description": "访客数",
      "example": "1"
    },
    "landing_pv": {
      "type": "integer",
      "description": "到达浏览量",
      "example": "1"
    },
    "landing_uv": {
      "type": "integer",
      "description": "到达访客数",
      "example": "1"
    },
    "new_uv": {
      "type": "integer",
      "description": "到达新访客数",
      "example": "1"
    },
    "share_pv": {
      "type": "integer",
      "description": "分享浏览量",
      "example": "1"
    },
    "share_uv": {
      "type": "integer",
      "description": "分享访客数",
      "example": "1"
    },
    "click_pv": {
      "type": "integer",
      "description": "二跳浏览量",
      "example": "1"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "summary_data": "",
  "time": "all",
  "pv": "1",
  "uv": "1",
  "landing_pv": "1",
  "landing_uv": "1",
  "new_uv": "1"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 结果 |
| `summary_data` | `string` | ❌ | `` | 汇总数据这里会给算一遍,实时数据的UV之类要去重，并不是明细数据相加 |
| `time` | `string` | ❌ | `all` | 按日期维度的详细数据，如果是今日实时，则小时展示为0,1……,22,23如果是天，则key为2018-01-01 |
| `pv` | `integer` | ❌ | `1` | 浏览量 |
| `uv` | `integer` | ❌ | `1` | 访客数 |
| `landing_pv` | `integer` | ❌ | `1` | 到达浏览量 |
| `landing_uv` | `integer` | ❌ | `1` | 到达访客数 |
| `new_uv` | `integer` | ❌ | `1` | 到达新访客数 |
| `share_pv` | `integer` | ❌ | `1` | 分享浏览量 |
| `share_uv` | `integer` | ❌ | `1` | 分享访客数 |
| `click_pv` | `integer` | ❌ | `1` | 二跳浏览量 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psdeatils/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "ps_code": "2118722746287589378.200001",\n  "attribution_period": "1",\n  "statistical_scope": "1",\n  "attribution_type": "1",\n  "start_day": "2021-12-01",\n  "end_day": "2021-12-02",\n  "node_kdt_id": "88888"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psdeatils/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "ps_code": "2118722746287589378.200001",
    "attribution_period": "1",
    "statistical_scope": "1",
    "attribution_type": "1",
    "start_day": "2021-12-01",
    "end_day": "2021-12-02",
    "node_kdt_id": "88888"
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