---
apiName: "com.youzan.sogo.token.generate.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "bifrost-developer"
apiGroup: "test"
serviceName: "com.youzan.bifrost.developer.api.service.SogoRemoteService"
method: "generateSogoToken"
timeout: "5000"
protocol: "dubbo"
authType: "OAuth"
type: "查询/写入"
kdtTypes: [wsc]
deprecated: false
since: "2019-12-09"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=759"
---
# com.youzan.sogo.token.generate.1.0.0
> **所属分组**: test　**所属应用**: bifrost-developer　**状态**: 已上线/变更中
---
## 1. 场景说明
搜狗输入法回调方法生成token
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/com.youzan.sogo.token.generate/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `OAuth`
**请求参数 Schema**（1 个参数）:
```json
{
  "type": "object",
  "properties": {
    "code": {
      "type": "string",
      "description": ""
    }
  },
  "required": [
    "code"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `code` | `string` | ✅ 是 | `` |  |
---
## 3. 响应
**响应参数 Schema**（6 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": ""
    },
    "success": {
      "type": "string",
      "description": ""
    },
    "code": {
      "type": "string",
      "description": ""
    },
    "message": {
      "type": "string",
      "description": ""
    },
    "request_id": {
      "type": "string",
      "description": ""
    },
    "error_data": {
      "type": "string",
      "description": ""
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "success": "",
  "code": "",
  "message": "",
  "request_id": "",
  "error_data": ""
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `string` | ❌ 否 | `` |  |
| `success` | `string` | ❌ 否 | `` |  |
| `code` | `string` | ❌ 否 | `` |  |
| `message` | `string` | ❌ 否 | `` |  |
| `request_id` | `string` | ❌ 否 | `` |  |
| `error_data` | `string` | ❌ 否 | `` |  |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=759

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "code": "<code>"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/com.youzan.sogo.token.generate/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "code": "<code>"
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
| 服务名称 | `com.youzan.bifrost.developer.api.service.SogoRemoteService` |
| 方法名称 | `generateSogoToken` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=759)_