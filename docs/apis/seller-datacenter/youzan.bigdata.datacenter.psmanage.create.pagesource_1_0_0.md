---
apiName: "youzan.bigdata.datacenter.psmanage.create.pagesource.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.yunapi.ManagePageSourceYunService"
method: "createPageSource"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2021-12-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3481"
---
# youzan.bigdata.datacenter.psmanage.create.pagesource.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
创建推广分析, 生成可跟踪数据的推广链接，支持连锁模型
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.create.pagesource/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（9 个参数）:
```json
{
  "type": "object",
  "properties": {
    "ps_name": {
      "type": "string",
      "description": "推广名称创建时不能为空",
      "example": "微信推广名称"
    },
    "source_name": {
      "type": "string",
      "description": "推广渠道名称",
      "example": "微信渠道"
    },
    "ps_location": {
      "type": "string",
      "description": "推广位置",
      "example": "微信"
    },
    "ps_cost": {
      "type": "integer",
      "description": "推广花费",
      "example": "1000"
    },
    "tag_name": {
      "type": "string",
      "description": "推广标签名称",
      "example": "微信推广标签"
    },
    "url": {
      "type": "string",
      "description": "推广链接",
      "example": "https://shop255245.m.youzan.com/wscgoods/detail/3nsvrpkem6t45"
    },
    "origin": {
      "type": "string",
      "description": "推广来源",
      "example": "dc"
    },
    "visit_fans_tag_name": {
      "type": "string",
      "description": "访问客户打标签",
      "example": "微信推广客户标签"
    },
    "note": {
      "type": "string",
      "description": "备注",
      "example": "备注信息"
    }
  },
  "required": [
    "ps_name",
    "source_name",
    "url"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `ps_name` | `string` | ✅ 是 | `微信推广名称` | 推广名称创建时不能为空 |
| `source_name` | `string` | ✅ 是 | `微信渠道` | 推广渠道名称 |
| `ps_location` | `string` | ❌ 否 | `微信` | 推广位置 |
| `ps_cost` | `integer` | ❌ 否 | `1000` | 推广花费 |
| `tag_name` | `string` | ❌ 否 | `微信推广标签` | 推广标签名称 |
| `url` | `string` | ✅ 是 | `https://shop255245.m.youzan.co` | 推广链接 |
| `origin` | `string` | ❌ 否 | `dc` | 推广来源 |
| `visit_fans_tag_name` | `string` | ❌ 否 | `微信推广客户标签` | 访问客户打标签 |
| `note` | `string` | ❌ 否 | `备注信息` | 备注 |
---
## 3. 响应
**响应参数 Schema**（8 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "结果"
    },
    "id": {
      "type": "integer",
      "description": "自增id",
      "example": "7788"
    },
    "dcps": {
      "type": "string",
      "description": "dcps",
      "example": "2474438270512040960.200001"
    },
    "ps_name": {
      "type": "string",
      "description": "推广名称",
      "example": "测试推广名称"
    },
    "success": {
      "type": "string",
      "description": "是否成功 true表示成功 false表示失败",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "成功失败码 200 表示成功",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "成功错误消息",
      "example": "参数缺失"
    },
    "request_id": {
      "type": "string",
      "description": "调用链",
      "example": "1111"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "id": "7788",
  "dcps": "2474438270512040960.200001",
  "ps_name": "测试推广名称",
  "success": "true",
  "code": "200",
  "message": "参数缺失",
  "request_id": "1111"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 结果 |
| `id` | `integer` | ❌ 否 | `7788` | 自增id |
| `dcps` | `string` | ❌ 否 | `2474438270512040960.200001` | dcps |
| `ps_name` | `string` | ❌ 否 | `测试推广名称` | 推广名称 |
| `success` | `string` | ❌ 否 | `true` | 是否成功 true表示成功 false表示失败 |
| `code` | `string` | ❌ 否 | `200` | 成功失败码 200 表示成功 |
| `message` | `string` | ❌ 否 | `参数缺失` | 成功错误消息 |
| `request_id` | `string` | ❌ 否 | `1111` | 调用链 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3481

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "ps_name": "微信推广名称",
  "source_name": "微信渠道",
  "url": "https://shop255245.m.youzan.com/wscgoods/detail/3nsvrpkem6t45"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.create.pagesource/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "ps_name": "微信推广名称",
  "source_name": "微信渠道",
  "url": "https://shop255245.m.youzan.com/wscgoods/detail/3nsvrpkem6t45"
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
| 方法名称 | `createPageSource` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3481)_