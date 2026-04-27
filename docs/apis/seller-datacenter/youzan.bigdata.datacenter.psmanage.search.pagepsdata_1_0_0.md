---
apiName: "youzan.bigdata.datacenter.psmanage.search.pagepsdata.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.yunapi.ManagePageSourceYunService"
method: "fetchPsPageSourceDetail"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2022-01-06"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3570"
---
# youzan.bigdata.datacenter.psmanage.search.pagepsdata.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
分页获取多个人推广监控效果数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagepsdata/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（8 个参数）:
```json
{
  "type": "object",
  "properties": {
    "dcps_list": {
      "type": "string",
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `dcps_list` | `string` | ❌ 否 | `["2118722746287589378.200001"]` | dcps号 |
| `page_no` | `integer` | ✅ 是 | `1` | 页码 |
| `page_size` | `integer` | ✅ 是 | `1` | 每页条数。最大不能超过200 |
| `attribution_period` | `integer` | ✅ 是 | `1` | 归因周期当天:1,七天:7,15天:15,30天:30 |
| `statistical_scope` | `integer` | ❌ 否 | `2` | 统计范围全部转化数据：空，推广页直接转化数据：2，连带销售：3 |
| `attribution_type` | `integer` | ✅ 是 | `1` | 归因方式首次1，末次2 |
| `start_day` | `string` | ✅ 是 | `2021-12-01` | 开始时间yyyy-MM-dd |
| `end_day` | `string` | ✅ 是 | `2021-12-02` | 结束时间yyyy-MM-dd |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "结果数据"
    },
    "paginator": {
      "type": "object",
      "description": "分页信息"
    },
    "page_no": {
      "type": "string",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页条数",
      "example": "10"
    },
    "total_count": {
      "type": "string",
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
  "data": "",
  "paginator": "",
  "page_no": "1",
  "page_size": "10",
  "total_count": "100",
  "items": [],
  "dcps": "2118722746287589378.200001",
  "ps_name": "微信推广"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 结果数据 |
| `paginator` | `object` | ❌ 否 | `` | 分页信息 |
| `page_no` | `string` | ❌ 否 | `1` | 页码 |
| `page_size` | `string` | ❌ 否 | `10` | 每页条数 |
| `total_count` | `string` | ❌ 否 | `100` | 总条数 |
| `items` | `array` | ❌ 否 | `` | 结果列表 |
| `dcps` | `string` | ❌ 否 | `2118722746287589378.200001` | 推广监控唯一标识 |
| `ps_name` | `string` | ❌ 否 | `微信推广` | 推广监控名称 |
| `channel_name` | `string` | ❌ 否 | `微信` | 所属渠道名称 |
| `tag_name` | `string` | ❌ 否 | `推广标签` | 所属标签名称 |
| `ps_cost` | `integer` | ❌ 否 | `10` | 推广花费 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3570

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "page_no": "1",
  "page_size": "1",
  "attribution_period": "1",
  "attribution_type": "1",
  "start_day": "2021-12-01"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagepsdata/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "page_no": "1",
  "page_size": "1",
  "attribution_period": "1",
  "attribution_type": "1",
  "start_day": "2021-12-01"
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
| 服务名称 | `com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.yunapi.ManagePageSourceYunService` |
| 方法名称 | `fetchPsPageSourceDetail` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3570)_