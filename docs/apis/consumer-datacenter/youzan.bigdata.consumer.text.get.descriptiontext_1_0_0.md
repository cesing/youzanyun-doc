---
apiName: "youzan.bigdata.consumer.text.get.descriptiontext.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "consumer-datacenter"
apiGroup: "data_center"
serviceName: "com.youzan.bigdata.datacenter.consumer.api.service.TextOpenService"
method: "getDescriptionText"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2021-07-21"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3076"
---
# youzan.bigdata.consumer.text.get.descriptiontext.1.0.0
> **所属分组**: data_center　**所属应用**: consumer-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
商品文本类接口。输入一个带产品词的query或商品标题，返回一段如诗般优雅的商品描述文案。文案可以用于B端店铺-选择一个商品（点击创建或编辑）在-分享描述中使用。 
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.consumer.text.get.descriptiontext/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "用户ID",
      "example": "joPykG3E620676084475629568"
    },
    "query": {
      "type": "string",
      "description": "查询词，必传",
      "example": "碎花连衣裙"
    }
  },
  "required": [
    "query"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `yz_open_id` | `integer` | ❌ 否 | `joPykG3E620676084475629568` | 用户ID |
| `query` | `string` | ✅ 是 | `碎花连衣裙` | 查询词，必传 |
---
## 3. 响应
**响应参数 Schema**（5 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "调用返回的数据"
    },
    "description_text": {
      "type": "string",
      "description": "描述文案",
      "example": "碎花连衣裙，秋日里的清新小碎花"
    },
    "success": {
      "type": "string",
      "description": "表示本次请求是否成功。 true：成功，false：失败。",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "successful"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "description_text": "碎花连衣裙，秋日里的清新小碎花",
  "success": "true",
  "code": "200",
  "message": "successful"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 调用返回的数据 |
| `description_text` | `string` | ❌ 否 | `碎花连衣裙，秋日里的清新小碎花` | 描述文案 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。 true：成功，false：失败。 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200 :成功。 |
| `message` | `string` | ❌ 否 | `successful` | 网关返回码描述 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3076

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "query": "碎花连衣裙"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.consumer.text.get.descriptiontext/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "query": "碎花连衣裙"
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
| 服务名称 | `com.youzan.bigdata.datacenter.consumer.api.service.TextOpenService` |
| 方法名称 | `getDescriptionText` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3076)_