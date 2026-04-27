---
apiName: "api-test.1.0.1"
version: "1.0.1"
status: "已上线/变更中"
appName: "gateway-test"
apiGroup: "网关测试分组"
serviceName: "com.youzan.platform.gateway.test.api.GatewayPressureTestOneService"
method: "invoke"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner]
deprecated: false
since: "2020-08-28"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1243"
---
# api-test.1.0.1
> **所属分组**: 网关测试分组　**所属应用**: gateway-test　**状态**: 已上线/变更中
---
## 1. 场景说明
test
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/api-test/1.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "add_test": {
      "type": "string",
      "description": "add_test",
      "example": "demo"
    },
    "count": {
      "type": "integer",
      "description": "返回的item个数",
      "example": "demo"
    },
    "process_time": {
      "type": "integer",
      "description": "模拟业务逻辑处理时间测试",
      "example": "demo"
    },
    "factor": {
      "type": "integer",
      "description": "随机因子，用来随机时间因子最大值为100，当100时，程序每次处理时间都等于processTime当因子小于100时，有百分之因子的概率执行时间等于processTime其他时候立即返回因子最小值为0，为0时processTime不生效",
      "example": "demo"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `add_test` | `string` | ❌ 否 | `demo` | add_test |
| `count` | `integer` | ❌ 否 | `demo` | 返回的item个数 |
| `process_time` | `integer` | ❌ 否 | `demo` | 模拟业务逻辑处理时间测试 |
| `factor` | `integer` | ❌ 否 | `demo` | 随机因子，用来随机时间因子最大值为100，当100时，程序每次处理时间都等于processTime当因子小于100时，有 |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "paginator": {
      "type": "object",
      "description": "1"
    },
    "page": {
      "type": "string",
      "description": "1",
      "example": "demo"
    },
    "page_size": {
      "type": "string",
      "description": "1",
      "example": "demo"
    },
    "total_count": {
      "type": "string",
      "description": "1",
      "example": "demo"
    },
    "items": {
      "type": "array",
      "description": "1"
    },
    "kdt_id": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "group_id": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "count": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "weight": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "index": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    }
  }
}
```
**成功响应示例**:
```json
{
  "paginator": "",
  "page": "demo",
  "page_size": "demo",
  "total_count": "demo",
  "items": [],
  "kdt_id": "demo",
  "group_id": "demo",
  "count": "demo"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `paginator` | `object` | ❌ 否 | `` | 1 |
| `page` | `string` | ❌ 否 | `demo` | 1 |
| `page_size` | `string` | ❌ 否 | `demo` | 1 |
| `total_count` | `string` | ❌ 否 | `demo` | 1 |
| `items` | `array` | ❌ 否 | `` | 1 |
| `kdt_id` | `integer` | ❌ 否 | `demo` | 1 |
| `group_id` | `integer` | ❌ 否 | `demo` | 1 |
| `count` | `integer` | ❌ 否 | `demo` | 1 |
| `weight` | `integer` | ❌ 否 | `demo` | 1 |
| `index` | `integer` | ❌ 否 | `demo` | 1 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1243

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/api-test/1.0.1"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {}

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
| 服务名称 | `com.youzan.platform.gateway.test.api.GatewayPressureTestOneService` |
| 方法名称 | `invoke` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1243)_