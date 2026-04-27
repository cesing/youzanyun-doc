---
apiName: "youzan.bigdata.gbox.general.query.service.1.0.0"
version: "1.0.0"
appName: "seller-growth-box"
apiGroup: "customized_api"
method: "invoke"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2020-11-18"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1557"
---
# youzan.bigdata.gbox.general.query.service.1.0.0
> **所属分组**: customized_api　**所属应用**: seller-growth-box
---
## 1. 场景说明
增长工具箱专用接口，只用于增长工具箱应用。
返回结构为有赞common组件，PlainResult, ListResult等，data为各个实际接口返回的数据，实际接口同入参的serviceName保持一致。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.gbox.general.query.service/1.0.0`
**请求参数 Schema**（6 个参数）:
```json
{
  "type": "object",
  "properties": {
    "general_param": {
      "type": "string",
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
      "type": "object",
      "description": "参数列表",
      "example": "{\"articlePageQueryParam\":{\"page\":1, \"pageSize\":10, \"kdtId\": 63077}}"
    },
    "operator_param": {
      "type": "string",
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
**请求参数明细**（6 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `general_param` | `string` | ❌ | `` | 服务请求映射 |
| `service` | `string` | ✅ | `com.youzan.bigdata.seller.growth.box.api` | 服务名 |
| `method` | `string` | ✅ | `listArticlePage` | 方法名 |
| `params` | `object` | ✅ | `{"articlePageQueryParam":{"page":1, "pag` | 参数列表 |
| `operator_param` | `string` | ❌ | `` | 操作者信息 |
| `user_id` | `integer` | ❌ | `1` | 操作用户id |
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
**响应参数明细**：暂无数据

---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.gbox.general.query.service/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "service": "com.youzan.bigdata.seller.growth.box.api.service.darwin.ArticleService",\n  "method": "listArticlePage",\n  "params": "{\"articlePageQueryParam\":{\"page\":1, \"pageSize\":10, \"kdtId\": 63077}}",\n  "user_id": "1"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.gbox.general.query.service/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "service": "com.youzan.bigdata.seller.growth.box.api.service.darwin.ArticleService",
    "method": "listArticlePage",
    "params": "{\"articlePageQueryParam\":{\"page\":1, \"pageSize\":10, \"kdtId\": 63077}}",
    "user_id": "1"
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