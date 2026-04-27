---
apiName: "youzan.bigdata.datacenter.psmanage.get.psorder.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
method: "fetchAttrPsOrderInfo"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-12-14"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3486"
---
# youzan.bigdata.datacenter.psmanage.get.psorder.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter
---
## 1. 场景说明
按天获取某个推广分析下的订单，仅支持离线，不支持今日实时
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psorder/1.0.0`
**请求参数 Schema**（8 个参数）:
```json
{
  "type": "object",
  "properties": {
    "attribution_period": {
      "type": "integer",
      "description": "归因周期。当天:1,七天:7,15天:15,30天:30",
      "example": "1"
    },
    "statistical_scope": {
      "type": "integer",
      "description": "统计范围 。 全部转化数据：不传、 推广页直接转化数据：2、连带销售：3",
      "example": "1"
    },
    "attribution_type": {
      "type": "integer",
      "description": "归因方式 。 首次1、末次2",
      "example": "1"
    },
    "dcps": {
      "type": "string",
      "description": "推广监控标识",
      "example": "2956668732916707328.200001"
    },
    "current_day": {
      "type": "integer",
      "description": "导出日期",
      "example": "20211201"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用店铺管理员id",
      "example": "LnhGm4rh576452722916618240"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页条数。默认100条",
      "example": "100"
    }
  },
  "required": [
    "attribution_period",
    "attribution_type",
    "dcps",
    "current_day",
    "yz_open_id",
    "page_no",
    "page_size"
  ]
}
```
**请求参数明细**（8 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `attribution_period` | `integer` | ✅ | `1` | 归因周期。当天:1,七天:7,15天:15,30天:30 |
| `statistical_scope` | `integer` | ❌ | `1` | 统计范围 。 全部转化数据：不传、 推广页直接转化数据：2、连带销售：3 |
| `attribution_type` | `integer` | ✅ | `1` | 归因方式 。 首次1、末次2 |
| `dcps` | `string` | ✅ | `2956668732916707328.200001` | 推广监控标识 |
| `current_day` | `integer` | ✅ | `20211201` | 导出日期 |
| `yz_open_id` | `integer` | ✅ | `LnhGm4rh576452722916618240` | 有赞用户id，用户在有赞的唯一id。推荐使用店铺管理员id |
| `page_no` | `integer` | ✅ | `1` | 页码 |
| `page_size` | `integer` | ✅ | `100` | 每页条数。默认100条 |
---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "返回结果"
    },
    "paginator": {
      "type": "string",
      "description": "分页结果信息"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "条数",
      "example": "100"
    },
    "total_count": {
      "type": "integer",
      "description": "分页查询的总条数",
      "example": "1000"
    },
    "items": {
      "type": "array",
      "description": "订单集合",
      "example": "['E10001','E1002']"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "参数缺失"
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
  "page_size": "100",
  "total_count": "1000",
  "items": "['E10001','E1002']",
  "success": "true",
  "code": "200"
}
```
**响应参数明细**（9 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 返回结果 |
| `paginator` | `string` | ❌ | `` | 分页结果信息 |
| `page_no` | `integer` | ❌ | `1` | 页码 |
| `page_size` | `integer` | ❌ | `100` | 条数 |
| `total_count` | `integer` | ❌ | `1000` | 分页查询的总条数 |
| `items` | `array` | ❌ | `['E10001','E1002']` | 订单集合 |
| `success` | `boolean` | ❌ | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `integer` | ❌ | `200` | 网关返回码，表示本次请求是否成功。200 :成功。 |
| `message` | `string` | ❌ | `参数缺失` | 网关返回码描述 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psorder/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "attribution_period": "1",\n  "statistical_scope": "1",\n  "attribution_type": "1",\n  "dcps": "2956668732916707328.200001",\n  "current_day": "20211201",\n  "yz_open_id": "LnhGm4rh576452722916618240",\n  "page_no": "1",\n  "page_size": "100"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psorder/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "attribution_period": "1",
    "statistical_scope": "1",
    "attribution_type": "1",
    "dcps": "2956668732916707328.200001",
    "current_day": "20211201",
    "yz_open_id": "LnhGm4rh576452722916618240",
    "page_no": "1",
    "page_size": "100"
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