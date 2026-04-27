---
apiName: "youzan.bifrost.service.security.code.validate.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "test"
apiGroup: "customized_api"
serviceName: "com.youzan.bifrost.service.api.service.AppSecurityRemoteCodeService"
method: "validate"
timeout: "5000"
protocol: "dubbo"
authType: "OAuth"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2020-07-08"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1071"
---
# youzan.bifrost.service.security.code.validate.1.0.0
> **所属分组**: customized_api　**所属应用**: test　**状态**: 已上线/变更中
---
## 1. 场景说明
校验app开店安全码
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bifrost.service.security.code.validate/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `OAuth`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "client_id": {
      "type": "string",
      "description": "应用的client_id",
      "example": "2"
    },
    "type": {
      "type": "integer",
      "description": "-1:未知,1:安卓,2:IOS",
      "example": "2"
    },
    "unique_key": {
      "type": "string",
      "description": "唯一标示",
      "example": "2"
    },
    "security_code": {
      "type": "string",
      "description": "安全码,安卓为SHA1,IOS为BundleID",
      "example": "2"
    },
    "extra_code": {
      "type": "string",
      "description": "扩展编码,安卓为包名,IOS暂无",
      "example": "2"
    }
  },
  "required": [
    "client_id",
    "type",
    "unique_key",
    "security_code"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `client_id` | `string` | ✅ 是 | `2` | 应用的client_id |
| `type` | `integer` | ✅ 是 | `2` | -1:未知,1:安卓,2:IOS |
| `unique_key` | `string` | ✅ 是 | `2` | 唯一标示 |
| `security_code` | `string` | ✅ 是 | `2` | 安全码,安卓为SHA1,IOS为BundleID |
| `extra_code` | `string` | ❌ 否 | `2` | 扩展编码,安卓为包名,IOS暂无 |
---
## 3. 响应
**响应参数 Schema**（7 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "",
      "example": "2"
    },
    "success": {
      "type": "string",
      "description": "",
      "example": "2"
    },
    "code": {
      "type": "string",
      "description": "",
      "example": "2"
    },
    "message": {
      "type": "string",
      "description": "",
      "example": "2"
    },
    "request_id": {
      "type": "string",
      "description": "",
      "example": "3"
    },
    "error_data": {
      "type": "string",
      "description": "",
      "example": "2"
    },
    "test": {
      "type": "string",
      "description": "",
      "example": "2"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "2",
  "success": "2",
  "code": "2",
  "message": "2",
  "request_id": "3",
  "error_data": "2",
  "test": "2"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `string` | ❌ 否 | `2` |  |
| `success` | `string` | ❌ 否 | `2` |  |
| `code` | `string` | ❌ 否 | `2` |  |
| `message` | `string` | ❌ 否 | `2` |  |
| `request_id` | `string` | ❌ 否 | `3` |  |
| `error_data` | `string` | ❌ 否 | `2` |  |
| `test` | `string` | ❌ 否 | `2` |  |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1071

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "client_id": "2",
  "type": "2",
  "unique_key": "2",
  "security_code": "2"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bifrost.service.security.code.validate/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "client_id": "2",
  "type": "2",
  "unique_key": "2",
  "security_code": "2"
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
| 服务名称 | `com.youzan.bifrost.service.api.service.AppSecurityRemoteCodeService` |
| 方法名称 | `validate` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1071)_