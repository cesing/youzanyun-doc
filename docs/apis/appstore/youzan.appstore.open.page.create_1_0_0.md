---
apiName: "youzan.appstore.open.page.create.1.0.0"
version: "1.0.0"
status: "待上线"
appName: "appstore"
apiGroup: "open_market"
serviceName: "com.youzan.cloud.appstore.api.service.open.AppstoreMicroPageService"
method: "createMicroPage"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc]
deprecated: false
since: "2019-05-20"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=357"
---
# youzan.appstore.open.page.create.1.0.0
> **所属分组**: open_market　**所属应用**: appstore　**状态**: 待上线
---
## 1. 场景说明
创建微页面
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.page.create/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（9 个参数）:
```json
{
  "type": "object",
  "properties": {
    "micro_page_request": {
      "type": "object",
      "description": ""
    },
    "user_id": {
      "type": "integer",
      "description": "用户id"
    },
    "inner_item_id": {
      "type": "integer",
      "description": "（内购项）模板id"
    },
    "out_item_id": {
      "type": "string",
      "description": "（内购项）外部商品编码"
    },
    "page_name": {
      "type": "string",
      "description": "页面名称"
    },
    "page_desc": {
      "type": "string",
      "description": "页面描述"
    },
    "view_url": {
      "type": "string",
      "description": "预览地址"
    },
    "re_edit_url": {
      "type": "string",
      "description": "重编辑地址"
    },
    "category_id": {
      "type": "integer",
      "description": "页面分类(非必填)"
    }
  },
  "required": [
    "micro_page_request",
    "user_id",
    "out_item_id",
    "page_name",
    "page_desc",
    "view_url",
    "re_edit_url"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `micro_page_request` | `object` | ✅ 是 | `` |  |
| `user_id` | `integer` | ✅ 是 | `` | 用户id |
| `inner_item_id` | `integer` | ❌ 否 | `` | （内购项）模板id |
| `out_item_id` | `string` | ✅ 是 | `` | （内购项）外部商品编码 |
| `page_name` | `string` | ✅ 是 | `` | 页面名称 |
| `page_desc` | `string` | ✅ 是 | `` | 页面描述 |
| `view_url` | `string` | ✅ 是 | `` | 预览地址 |
| `re_edit_url` | `string` | ✅ 是 | `` | 重编辑地址 |
| `category_id` | `integer` | ❌ 否 | `` | 页面分类(非必填) |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": ""
    },
    "id": {
      "type": "integer",
      "description": ""
    },
    "page_id": {
      "type": "integer",
      "description": "页面id"
    },
    "inner_item_id": {
      "type": "integer",
      "description": "内购项id(模板id)"
    },
    "page_name": {
      "type": "string",
      "description": "页面名称"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺id"
    },
    "user_id": {
      "type": "integer",
      "description": "用户id"
    },
    "view_url": {
      "type": "string",
      "description": "预览地址"
    },
    "re_edit_url": {
      "type": "string",
      "description": "编辑地址"
    },
    "category_id": {
      "type": "integer",
      "description": "分类id"
    },
    "page_desc": {
      "type": "string",
      "description": "页面描述"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "id": 0,
  "page_id": 0,
  "inner_item_id": 0,
  "page_name": "",
  "kdt_id": 0,
  "user_id": 0,
  "view_url": ""
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `id` | `integer` | ❌ 否 | `` |  |
| `page_id` | `integer` | ❌ 否 | `` | 页面id |
| `inner_item_id` | `integer` | ❌ 否 | `` | 内购项id(模板id) |
| `page_name` | `string` | ❌ 否 | `` | 页面名称 |
| `kdt_id` | `integer` | ❌ 否 | `` | 店铺id |
| `user_id` | `integer` | ❌ 否 | `` | 用户id |
| `view_url` | `string` | ❌ 否 | `` | 预览地址 |
| `re_edit_url` | `string` | ❌ 否 | `` | 编辑地址 |
| `category_id` | `integer` | ❌ 否 | `` | 分类id |
| `page_desc` | `string` | ❌ 否 | `` | 页面描述 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=357

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "micro_page_request": "<micro_page_request>",
  "user_id": "<user_id>",
  "out_item_id": "<out_item_id>",
  "page_name": "<page_name>",
  "page_desc": "<page_desc>"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.page.create/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "micro_page_request": "<micro_page_request>",
  "user_id": "<user_id>",
  "out_item_id": "<out_item_id>",
  "page_name": "<page_name>",
  "page_desc": "<page_desc>"
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
| 服务名称 | `com.youzan.cloud.appstore.api.service.open.AppstoreMicroPageService` |
| 方法名称 | `createMicroPage` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=357)_