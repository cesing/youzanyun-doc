---
apiName: "youzan.bigdata.datacenter.psmanage.search.pagesourcedetail.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.yunapi.ManagePageSourceYunService"
method: "fetchPsPageSourceList"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2021-12-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3483"
---
# youzan.bigdata.datacenter.psmanage.search.pagesourcedetail.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
获取推广监控列表基本数据,不包含效果数据。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagesourcedetail/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "ps_name": {
      "type": "string",
      "description": "推广监控名称",
      "example": "推广1"
    },
    "dcps_list": {
      "type": "string",
      "description": "dcps列表",
      "example": "[\"2118722746287589378.200001\"]"
    },
    "ps_status": {
      "type": "integer",
      "description": "推广监控状态1:推广中;2:推广结束",
      "example": "1"
    },
    "start_day": {
      "type": "string",
      "description": "查询开始时间",
      "example": "2021-12-01"
    },
    "end_day": {
      "type": "string",
      "description": "查询结束时间",
      "example": "2021-12-01"
    },
    "page_no": {
      "type": "integer",
      "description": "分页信息",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "分页信息",
      "example": "100"
    }
  },
  "required": [
    "page_no",
    "page_size"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `ps_name` | `string` | ❌ 否 | `推广1` | 推广监控名称 |
| `dcps_list` | `string` | ❌ 否 | `["2118722746287589378.200001"]` | dcps列表 |
| `ps_status` | `integer` | ❌ 否 | `1` | 推广监控状态1:推广中;2:推广结束 |
| `start_day` | `string` | ❌ 否 | `2021-12-01` | 查询开始时间 |
| `end_day` | `string` | ❌ 否 | `2021-12-01` | 查询结束时间 |
| `page_no` | `integer` | ✅ 是 | `1` | 分页信息 |
| `page_size` | `integer` | ✅ 是 | `100` | 分页信息 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "结果"
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
      "description": "每页条数。最大不能超过200",
      "example": "100"
    },
    "total_count": {
      "type": "string",
      "description": "总数",
      "example": "1000"
    },
    "items": {
      "type": "array",
      "description": "推广监控列表"
    },
    "id": {
      "type": "integer",
      "description": "自增id",
      "example": "1"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "dcps": {
      "type": "string",
      "description": "dcps",
      "example": "2118722746287589378.200001"
    },
    "ps_name": {
      "type": "string",
      "description": "推广名称",
      "example": "推广1"
    },
    "source_id": {
      "type": "integer",
      "description": "推广渠道id,ps_sourceid",
      "example": "1"
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
  "page_size": "100",
  "total_count": "1000",
  "items": [],
  "id": "1",
  "kdt_id": "88888"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 结果 |
| `paginator` | `object` | ❌ 否 | `` | 分页信息 |
| `page_no` | `string` | ❌ 否 | `1` | 页码 |
| `page_size` | `string` | ❌ 否 | `100` | 每页条数。最大不能超过200 |
| `total_count` | `string` | ❌ 否 | `1000` | 总数 |
| `items` | `array` | ❌ 否 | `` | 推广监控列表 |
| `id` | `integer` | ❌ 否 | `1` | 自增id |
| `kdt_id` | `integer` | ❌ 否 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `dcps` | `string` | ❌ 否 | `2118722746287589378.200001` | dcps |
| `ps_name` | `string` | ❌ 否 | `推广1` | 推广名称 |
| `source_id` | `integer` | ❌ 否 | `1` | 推广渠道id,ps_sourceid |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3483

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "page_no": "1",
  "page_size": "100"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.search.pagesourcedetail/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "page_no": "1",
  "page_size": "100"
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
| 方法名称 | `fetchPsPageSourceList` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3483)_