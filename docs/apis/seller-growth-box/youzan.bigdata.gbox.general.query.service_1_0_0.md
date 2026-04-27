---
apiName: "youzan.bigdata.gbox.general.query.service.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-growth-box"
apiGroup: "customized_api"
serviceName: "com.youzan.bigdata.seller.growth.box.api.GeneralService"
method: "invoke"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail, beauty, edu_head]
deprecated: false
since: "2020-11-18"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1557"
---
# youzan.bigdata.gbox.general.query.service.1.0.0
> **所属分组**: customized_api　**所属应用**: seller-growth-box　**状态**: 已上线/变更中
---
## 1. 场景说明
增长工具箱专用接口，只用于增长工具箱应用。
返回结构为有赞common组件，PlainResult, ListResult等，data为各个实际接口返回的数据，实际接口同入参的serviceName保持一致。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.gbox.general.query.service/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（6 个参数）:
```json
{
  "type": "object",
  "properties": {
    "general_param": {
      "type": "object",
      "description": "服务请求映射"
    },
    "service": {
      "type": "string",
      "description": "服务名",
      "example": "com.youzan.bigdata.seller.growth.box.api.service.darwin.ArticleService"
    },
    "method": {
      "type": "string",
      "description": "方法名",
      "example": "listArticlePage"
    },
    "params": {
      "type": "string",
      "description": "参数列表",
      "example": "{\"articlePageQueryParam\":{\"page\":1, \"pageSize\":10, \"kdtId\": 63077}}"
    },
    "operator_param": {
      "type": "object",
      "description": "操作者信息"
    },
    "user_id": {
      "type": "integer",
      "description": "操作用户id",
      "example": "1"
    }
  },
  "required": [
    "service",
    "method",
    "params"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `general_param` | `object` | ❌ 否 | `` | 服务请求映射 |
| `service` | `string` | ✅ 是 | `com.youzan.bigdata.seller.grow` | 服务名 |
| `method` | `string` | ✅ 是 | `listArticlePage` | 方法名 |
| `params` | `string` | ✅ 是 | `{"articlePageQueryParam":{"pag` | 参数列表 |
| `operator_param` | `object` | ❌ 否 | `` | 操作者信息 |
| `user_id` | `integer` | ❌ 否 | `1` | 操作用户id |
---
## 3. 响应
**响应参数 Schema**（0 个字段）:
```json
{
  "type": "object",
  "properties": {}
}
```
**成功响应示例**:
```json
{}
```
**响应参数明细**  （详情页暂无数据）

无结构化参数信息
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1557

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "service": "com.youzan.bigdata.seller.growth.box.api.service.darwin.ArticleService",
  "method": "listArticlePage",
  "params": "{\"articlePageQueryParam\":{\"page\":1, \"pageSize\":10, \"kdtId\": 63077}}"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.gbox.general.query.service/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "service": "com.youzan.bigdata.seller.growth.box.api.service.darwin.ArticleService",
  "method": "listArticlePage",
  "params": "{\"articlePageQueryParam\":{\"page\":1, \"pageSize\":10, \"kdtId\": 63077}}"
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
| 服务名称 | `com.youzan.bigdata.seller.growth.box.api.GeneralService` |
| 方法名称 | `invoke` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1557)_