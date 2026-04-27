---
apiName: "youzan.bigdata.data.get.1.0.0"
version: "1.0.0"
status: "已上线"
appName: "seller-datacenter"
apiGroup: "item"
serviceName: "com.youzan.bigdata.datacenter.wsc.api.service.goods.AdCpsTeamSpuService"
method: "query"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc]
deprecated: false
since: "2020-11-12"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1544"
---
# youzan.bigdata.data.get.1.0.0
> **所属分组**: item　**所属应用**: seller-datacenter　**状态**: 已上线
---
## 1. 场景说明
该接口仅支持在快手直播产生的推广数据，查询时间间隔T+1，建议数据在第二天的10：00之后查询前一天的数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.data.get/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "ad_cps_team_spu_param": {
      "type": "object",
      "description": "入参"
    },
    "current_day": {
      "type": "string",
      "description": "查询日期",
      "example": "2020-11-10"
    },
    "item_id": {
      "type": "integer",
      "description": "直播商品id",
      "example": "23333"
    },
    "type": {
      "type": "string",
      "description": "渠道类型,默认快手",
      "example": "快手"
    }
  },
  "required": [
    "current_day",
    "item_id"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `ad_cps_team_spu_param` | `object` | ❌ 否 | `` | 入参 |
| `current_day` | `string` | ✅ 是 | `2020-11-10` | 查询日期 |
| `item_id` | `integer` | ✅ 是 | `23333` | 直播商品id |
| `type` | `string` | ❌ 否 | `快手` | 渠道类型,默认快手 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "直播数据"
    },
    "trade_num": {
      "type": "integer",
      "description": "支付人数",
      "example": "12"
    },
    "trade_count": {
      "type": "integer",
      "description": "支付笔数",
      "example": "121"
    },
    "trade_amount": {
      "type": "integer",
      "description": "支付金额（分）",
      "example": "2"
    },
    "pay_num": {
      "type": "integer",
      "description": "下单人数",
      "example": "12"
    },
    "pay_count": {
      "type": "integer",
      "description": "下单笔数",
      "example": "12"
    },
    "pay_amount": {
      "type": "integer",
      "description": "下单金额（分）",
      "example": "12"
    },
    "pv": {
      "type": "integer",
      "description": "浏览量",
      "example": "12"
    },
    "uv": {
      "type": "integer",
      "description": "访客数",
      "example": "12"
    },
    "success": {
      "type": "string",
      "description": "成功与否",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "返回码",
      "example": "200"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "trade_num": "12",
  "trade_count": "121",
  "trade_amount": "2",
  "pay_num": "12",
  "pay_count": "12",
  "pay_amount": "12",
  "pv": "12"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 直播数据 |
| `trade_num` | `integer` | ❌ 否 | `12` | 支付人数 |
| `trade_count` | `integer` | ❌ 否 | `121` | 支付笔数 |
| `trade_amount` | `integer` | ❌ 否 | `2` | 支付金额（分） |
| `pay_num` | `integer` | ❌ 否 | `12` | 下单人数 |
| `pay_count` | `integer` | ❌ 否 | `12` | 下单笔数 |
| `pay_amount` | `integer` | ❌ 否 | `12` | 下单金额（分） |
| `pv` | `integer` | ❌ 否 | `12` | 浏览量 |
| `uv` | `integer` | ❌ 否 | `12` | 访客数 |
| `success` | `string` | ❌ 否 | `true` | 成功与否 |
| `code` | `string` | ❌ 否 | `200` | 返回码 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1544

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "current_day": "2020-11-10",
  "item_id": "23333"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.data.get/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "current_day": "2020-11-10",
  "item_id": "23333"
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
| 服务名称 | `com.youzan.bigdata.datacenter.wsc.api.service.goods.AdCpsTeamSpuService` |
| 方法名称 | `query` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1544)_