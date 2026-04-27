---
apiName: "youzan.agent.gatewaytest.run.preworkflow.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "gateway-test"
apiGroup: "网关测试分组"
serviceName: "/api/youzan.agent.gatewaytest.run.preworkflow/1.0.0"
method: "POST"
timeout: "60000"
protocol: "http"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc]
deprecated: false
since: "2025-05-22"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4816"
---
# youzan.agent.gatewaytest.run.preworkflow.1.0.0
> **所属分组**: 网关测试分组　**所属应用**: gateway-test　**状态**: 已上线/变更中
---
## 1. 场景说明
aaa
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.agent.gatewaytest.run.preworkflow/1.0.0`
**超时时间**: `60000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（1 个参数）:
```json
{
  "type": "object",
  "properties": {
    "test": {
      "type": "string",
      "description": "test",
      "example": "test"
    }
  },
  "required": [
    "test"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `test` | `string` | ✅ 是 | `test` | test |
---
## 3. 响应
**响应参数 Schema**（6 个字段）:
```json
{
  "type": "object",
  "properties": {
    "response": {
      "type": "object",
      "description": "test"
    },
    "code": {
      "type": "integer",
      "description": "test",
      "example": "200"
    },
    "data": {
      "type": "object",
      "description": "test"
    },
    "message": {
      "type": "string",
      "description": "test",
      "example": "message"
    },
    "statusCode": {
      "type": "string",
      "description": "test",
      "example": "statusCode"
    },
    "success": {
      "type": "integer",
      "description": "test",
      "example": "true"
    }
  }
}
```
**成功响应示例**:
```json
{
  "response": "",
  "code": "200",
  "data": "",
  "message": "message",
  "statusCode": "statusCode",
  "success": "true"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `response` | `object` | ❌ 否 | `` | test |
| `code` | `integer` | ❌ 否 | `200` | test |
| `data` | `object` | ❌ 否 | `` | test |
| `message` | `string` | ❌ 否 | `message` | test |
| `statusCode` | `string` | ❌ 否 | `statusCode` | test |
| `success` | `integer` | ❌ 否 | `true` | test |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4816

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "test": "test"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.agent.gatewaytest.run.preworkflow/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "test": "test"
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
| 协议类型 | http |
| 服务名称 | `/api/youzan.agent.gatewaytest.run.preworkflow/1.0.0` |
| 方法名称 | `POST` |
| 超时时间 | 60000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4816)_