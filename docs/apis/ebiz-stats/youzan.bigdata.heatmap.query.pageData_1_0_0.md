---
apiName: "youzan.bigdata.heatmap.query.pageData.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "ebiz-stats"
apiGroup: "data_center"
serviceName: "com.youzan.ebiz.stats.biz.heatmap.dubboapi.HeatMapNewService"
method: "getStatsNew"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc]
deprecated: false
since: "2023-05-18"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4078"
---
# youzan.bigdata.heatmap.query.pageData.1.0.0
> **所属分组**: data_center　**所属应用**: ebiz-stats　**状态**: 已上线/变更中
---
## 1. 场景说明
根据热力图id获取页面级别统计信息：点击人数、点击次数、浏览量、访客数等
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.pageData/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "description": "定制页面id，而非页面id",
      "example": "1"
    },
    "start_time": {
      "type": "integer",
      "description": "开始时间，格式YYYYMMdd",
      "example": "20230511"
    },
    "end_time": {
      "type": "integer",
      "description": "结束时间，格式YYYYMMdd",
      "example": "20230511"
    },
    "sdk_type": {
      "type": "string",
      "description": "渠道筛选条件。枚举值小程序：weapp、 其他：js",
      "example": "weapp"
    }
  },
  "required": [
    "sdk_type"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `id` | `integer` | ❌ 否 | `1` | 定制页面id，而非页面id |
| `start_time` | `integer` | ❌ 否 | `20230511` | 开始时间，格式YYYYMMdd |
| `end_time` | `integer` | ❌ 否 | `20230511` | 结束时间，格式YYYYMMdd |
| `sdk_type` | `string` | ✅ 是 | `weapp` | 渠道筛选条件。枚举值小程序：weapp、 其他：js |
---
## 3. 响应
**响应参数 Schema**（6 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "业务数据内容"
    },
    "total_stats": {
      "type": "object",
      "description": "汇总值"
    },
    "total_uv": {
      "type": "integer",
      "description": "访客数",
      "example": "1"
    },
    "total_pv": {
      "type": "integer",
      "description": "浏览量",
      "example": "1"
    },
    "click_pv": {
      "type": "integer",
      "description": "点击次数",
      "example": "1"
    },
    "click_uv": {
      "type": "integer",
      "description": "点击人数",
      "example": "1"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "total_stats": "",
  "total_uv": "1",
  "total_pv": "1",
  "click_pv": "1",
  "click_uv": "1"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 业务数据内容 |
| `total_stats` | `object` | ❌ 否 | `` | 汇总值 |
| `total_uv` | `integer` | ❌ 否 | `1` | 访客数 |
| `total_pv` | `integer` | ❌ 否 | `1` | 浏览量 |
| `click_pv` | `integer` | ❌ 否 | `1` | 点击次数 |
| `click_uv` | `integer` | ❌ 否 | `1` | 点击人数 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4078

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "sdk_type": "weapp"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.heatmap.query.pageData/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "sdk_type": "weapp"
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
| 服务名称 | `com.youzan.ebiz.stats.biz.heatmap.dubboapi.HeatMapNewService` |
| 方法名称 | `getStatsNew` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4078)_