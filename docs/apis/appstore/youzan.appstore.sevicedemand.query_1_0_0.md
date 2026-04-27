---
apiName: "youzan.appstore.sevicedemand.query.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "appstore"
apiGroup: "customized_api"
serviceName: "com.youzan.cloud.appstore.api.service.demand.ServiceDemandService"
method: "getDemandListByTime"
timeout: "5000"
protocol: "dubbo"
authType: "OAuth"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2021-05-12"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=2829"
---
# youzan.appstore.sevicedemand.query.1.0.0
> **所属分组**: customized_api　**所属应用**: appstore　**状态**: 已上线/变更中
---
## 1. 场景说明
根据时间获取需求列表(连接器调用)
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.sevicedemand.query/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `OAuth`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "start_time": {
      "type": "string",
      "description": "开始时间筛选条件，默认1970-01-01 08:00:00",
      "example": "2021-05-07 00:00:00"
    },
    "end_time": {
      "type": "string",
      "description": "结束时间筛选条件，默认当前时间",
      "example": "2021-05-07 00:00:00"
    },
    "page_no": {
      "type": "integer",
      "description": "查询时当前的页数（分页查询接口必填）",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页展示的行数（分页查询接口必填）",
      "example": "10"
    }
  },
  "required": [
    "start_time"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `start_time` | `string` | ✅ 是 | `2021-05-07 00:00:00` | 开始时间筛选条件，默认1970-01-01 08:00:00 |
| `end_time` | `string` | ❌ 否 | `2021-05-07 00:00:00` | 结束时间筛选条件，默认当前时间 |
| `page_no` | `integer` | ❌ 否 | `1` | 查询时当前的页数（分页查询接口必填） |
| `page_size` | `integer` | ❌ 否 | `10` | 每页展示的行数（分页查询接口必填） |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "data"
    },
    "paginator": {
      "type": "object",
      "description": "分页"
    },
    "page": {
      "type": "string",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "页数",
      "example": "10"
    },
    "total_count": {
      "type": "string",
      "description": "总数",
      "example": "10"
    },
    "items": {
      "type": "array",
      "description": "需求列表"
    },
    "id": {
      "type": "integer",
      "description": "主键id",
      "example": "1"
    },
    "demand_no": {
      "type": "string",
      "description": "需求编号",
      "example": "864642465397448704"
    },
    "demand_detail": {
      "type": "string",
      "description": "需求信息",
      "example": "我需要10人的客服团队"
    },
    "mobile": {
      "type": "string",
      "description": "联系人手机号码",
      "example": "13000000000"
    },
    "status": {
      "type": "integer",
      "description": "需求状态",
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
  "page": "1",
  "page_size": "10",
  "total_count": "10",
  "items": [],
  "id": "1",
  "demand_no": "864642465397448704"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | data |
| `paginator` | `object` | ❌ 否 | `` | 分页 |
| `page` | `string` | ❌ 否 | `1` | 页码 |
| `page_size` | `string` | ❌ 否 | `10` | 页数 |
| `total_count` | `string` | ❌ 否 | `10` | 总数 |
| `items` | `array` | ❌ 否 | `` | 需求列表 |
| `id` | `integer` | ❌ 否 | `1` | 主键id |
| `demand_no` | `string` | ❌ 否 | `864642465397448704` | 需求编号 |
| `demand_detail` | `string` | ❌ 否 | `我需要10人的客服团队` | 需求信息 |
| `mobile` | `string` | ❌ 否 | `13000000000` | 联系人手机号码 |
| `status` | `integer` | ❌ 否 | `10` | 需求状态 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=2829

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "start_time": "2021-05-07 00:00:00"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.sevicedemand.query/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "start_time": "2021-05-07 00:00:00"
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
| 服务名称 | `com.youzan.cloud.appstore.api.service.demand.ServiceDemandService` |
| 方法名称 | `getDemandListByTime` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=2829)_