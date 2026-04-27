---
apiName: "youzan.appstore.sevicedemand.upload.status.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "appstore"
apiGroup: "customized_api"
serviceName: "com.youzan.cloud.appstore.api.service.demand.ServiceDemandService"
method: "updateDemandStatus"
timeout: "5000"
protocol: "dubbo"
authType: "OAuth"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2021-05-07"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=2802"
---
# youzan.appstore.sevicedemand.upload.status.1.0.0
> **所属分组**: customized_api　**所属应用**: appstore　**状态**: 已上线/变更中
---
## 1. 场景说明
修改服务市场需求状态
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.sevicedemand.upload.status/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `OAuth`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "service_demand_status_update_request": {
      "type": "object",
      "description": "请求集"
    },
    "demand_no": {
      "type": "string",
      "description": "需求编号",
      "example": "864642465397448704"
    },
    "status": {
      "type": "integer",
      "description": "需求状态@seeServiceDemandStatusEnum",
      "example": "10"
    },
    "remark": {
      "type": "string",
      "description": "需求备注",
      "example": "需求状态变更备注"
    }
  },
  "required": [
    "demand_no",
    "status",
    "remark"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `service_demand_status_update_request` | `object` | ❌ 否 | `` | 请求集 |
| `demand_no` | `string` | ✅ 是 | `864642465397448704` | 需求编号 |
| `status` | `integer` | ✅ 是 | `10` | 需求状态@seeServiceDemandStatusEnum |
| `remark` | `string` | ✅ 是 | `需求状态变更备注` | 需求备注 |
---
## 3. 响应
**响应参数 Schema**（5 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "boolean",
      "description": "data",
      "example": "true"
    },
    "success": {
      "type": "string",
      "description": "是否成功",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "结果code",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "结果message",
      "example": "成功"
    },
    "request_id": {
      "type": "string",
      "description": "请求id",
      "example": "111111"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "true",
  "success": "true",
  "code": "200",
  "message": "成功",
  "request_id": "111111"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `boolean` | ❌ 否 | `true` | data |
| `success` | `string` | ❌ 否 | `true` | 是否成功 |
| `code` | `string` | ❌ 否 | `200` | 结果code |
| `message` | `string` | ❌ 否 | `成功` | 结果message |
| `request_id` | `string` | ❌ 否 | `111111` | 请求id |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=2802

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "demand_no": "864642465397448704",
  "status": "10",
  "remark": "需求状态变更备注"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.sevicedemand.upload.status/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "demand_no": "864642465397448704",
  "status": "10",
  "remark": "需求状态变更备注"
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
| 方法名称 | `updateDemandStatus` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=2802)_