---
apiName: "youzan.appstore.open.data.page.pvuv.get.1.0.0"
version: "1.0.0"
status: "待上线"
appName: "data-sync"
apiGroup: "open_market"
serviceName: "com.youzan.cloud.data.sync.api.service.DataAnalysisService"
method: "getPagePVUV"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc]
deprecated: false
since: "2019-07-29"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=574"
---
# youzan.appstore.open.data.page.pvuv.get.1.0.0
> **所属分组**: open_market　**所属应用**: data-sync　**状态**: 待上线
---
## 1. 场景说明
查询微页面pvuv数据，只支持3个月内的数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.data.page.pvuv.get/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": ""
    },
    "app_name": {
      "type": "string",
      "description": "应用名称",
      "example": "tuzhan"
    },
    "page_id": {
      "type": "string",
      "description": "页面id",
      "example": "229101"
    },
    "date": {
      "type": "string",
      "description": "查询日期,格式\"2019-07-01\"",
      "example": "2019-07-25"
    }
  },
  "required": [
    "request",
    "page_id",
    "date"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ✅ 是 | `` |  |
| `app_name` | `string` | ❌ 否 | `tuzhan` | 应用名称 |
| `page_id` | `string` | ✅ 是 | `229101` | 页面id |
| `date` | `string` | ✅ 是 | `2019-07-25` | 查询日期,格式"2019-07-01" |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": ""
    },
    "pv_uv_data": {
      "type": "object",
      "description": "浏览数据"
    },
    "uv": {
      "type": "integer",
      "description": "今日UV",
      "example": "1"
    },
    "pv": {
      "type": "integer",
      "description": "今日PV",
      "example": "2"
    },
    "page_id": {
      "type": "string",
      "description": "微页面id",
      "example": "229101"
    },
    "date": {
      "type": "string",
      "description": "日期",
      "example": "2019-07-25"
    },
    "success": {
      "type": "string",
      "description": "调用结果",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "返回码",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "返回信息",
      "example": "success"
    },
    "request_id": {
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
  "pv_uv_data": "",
  "uv": "1",
  "pv": "2",
  "page_id": "229101",
  "date": "2019-07-25",
  "success": "true",
  "code": "200"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `pv_uv_data` | `object` | ❌ 否 | `` | 浏览数据 |
| `uv` | `integer` | ❌ 否 | `1` | 今日UV |
| `pv` | `integer` | ❌ 否 | `2` | 今日PV |
| `page_id` | `string` | ❌ 否 | `229101` | 微页面id |
| `date` | `string` | ❌ 否 | `2019-07-25` | 日期 |
| `success` | `string` | ❌ 否 | `true` | 调用结果 |
| `code` | `string` | ❌ 否 | `200` | 返回码 |
| `message` | `string` | ❌ 否 | `success` | 返回信息 |
| `request_id` | `string` | ❌ 否 | `` |  |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=574

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "request": "<request>",
  "page_id": "229101",
  "date": "2019-07-25"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.data.page.pvuv.get/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "request": "<request>",
  "page_id": "229101",
  "date": "2019-07-25"
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
| 服务名称 | `com.youzan.cloud.data.sync.api.service.DataAnalysisService` |
| 方法名称 | `getPagePVUV` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=574)_