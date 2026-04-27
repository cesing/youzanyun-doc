---
apiName: "youzan.bigdata.datacenter.psmanage.update.pagesource.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.yunapi.ManagePageSourceYunService"
method: "updatePageSource"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2021-12-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3482"
---
# youzan.bigdata.datacenter.psmanage.update.pagesource.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
更新推广监控名称
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.update.pagesource/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "description": "id更新时不能为空",
      "example": "id，推广监控id，可通过<获取推广监控列表>接口获取。"
    },
    "ps_name": {
      "type": "string",
      "description": "推广名称创建时不能为空",
      "example": "推广名称"
    }
  },
  "required": [
    "id",
    "ps_name"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `id` | `integer` | ✅ 是 | `id，推广监控id，可通过<获取推广监控列表>接口获取。` | id更新时不能为空 |
| `ps_name` | `string` | ✅ 是 | `推广名称` | 推广名称创建时不能为空 |
---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "数据"
    },
    "id": {
      "type": "integer",
      "description": "自增id",
      "example": "1"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "ps_code": {
      "type": "string",
      "description": "dcps",
      "example": "111111"
    },
    "ps_name": {
      "type": "string",
      "description": "推广名称",
      "example": "推广名称"
    },
    "source_id": {
      "type": "integer",
      "description": "推广渠道，ps_sourceid",
      "example": "1"
    },
    "source_name": {
      "type": "string",
      "description": "渠道名称",
      "example": "渠道"
    },
    "source_default_tag": {
      "type": "integer",
      "description": "是否默认渠道,0:默认渠道;1:自定义渠道",
      "example": "1"
    },
    "page_info_id": {
      "type": "integer",
      "description": "推广页面，ps_page_info主键id",
      "example": "1"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "id": "1",
  "kdt_id": "88888",
  "ps_code": "111111",
  "ps_name": "推广名称",
  "source_id": "1",
  "source_name": "渠道",
  "source_default_tag": "1"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 数据 |
| `id` | `integer` | ❌ 否 | `1` | 自增id |
| `kdt_id` | `integer` | ❌ 否 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `ps_code` | `string` | ❌ 否 | `111111` | dcps |
| `ps_name` | `string` | ❌ 否 | `推广名称` | 推广名称 |
| `source_id` | `integer` | ❌ 否 | `1` | 推广渠道，ps_sourceid |
| `source_name` | `string` | ❌ 否 | `渠道` | 渠道名称 |
| `source_default_tag` | `integer` | ❌ 否 | `1` | 是否默认渠道,0:默认渠道;1:自定义渠道 |
| `page_info_id` | `integer` | ❌ 否 | `1` | 推广页面，ps_page_info主键id |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3482

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "id": "id，推广监控id，可通过<获取推广监控列表>接口获取。",
  "ps_name": "推广名称"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.update.pagesource/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "id": "id，推广监控id，可通过<获取推广监控列表>接口获取。",
  "ps_name": "推广名称"
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
| 服务名称 | `com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.yunapi.ManagePageSourceYunService` |
| 方法名称 | `updatePageSource` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3482)_