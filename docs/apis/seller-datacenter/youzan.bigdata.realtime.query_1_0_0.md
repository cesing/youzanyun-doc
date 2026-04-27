---
apiName: "youzan.bigdata.realtime.query.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "shop"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.realtime.RealTimeServiceV2"
method: "getRealTimeOverView"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, retail, wsc_online, 1]
deprecated: false
since: "2025-06-11"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4839"
---
# youzan.bigdata.realtime.query.1.0.0
> **所属分组**: shop　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
实时分析的实时概况数据，主要包括浏览访问、成交转化、客户会员
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.realtime.query/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（10 个参数）:
```json
{
  "type": "object",
  "properties": {
    "basic_param": {
      "type": "object",
      "description": "请求体"
    },
    "current_day": {
      "type": "integer",
      "description": "不填则为今日实时format:yyyyMMdd",
      "example": "20250611"
    },
    "canal_type": {
      "type": "integer",
      "description": "线上线下：0线上；1线下；10全部",
      "example": "0"
    },
    "page_no": {
      "type": "integer",
      "description": "分页参数",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页数据量大小",
      "example": "10"
    },
    "team_level": {
      "type": "integer",
      "description": "店铺等级：0-总店或者管理单元;1-子店;",
      "example": "1"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺id",
      "example": "88888"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用",
      "example": "123456"
    },
    "request_id": {
      "type": "string",
      "description": "UUID",
      "example": "sadsadafdafdsfsd"
    },
    "operator": {
      "type": "string",
      "description": "操作人名字",
      "example": "zhangsan"
    }
  },
  "required": [
    "current_day",
    "yz_open_id"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `basic_param` | `object` | ❌ 否 | `` | 请求体 |
| `current_day` | `integer` | ✅ 是 | `20250611` | 不填则为今日实时format:yyyyMMdd |
| `canal_type` | `integer` | ❌ 否 | `0` | 线上线下：0线上；1线下；10全部 |
| `page_no` | `integer` | ❌ 否 | `1` | 分页参数 |
| `page_size` | `integer` | ❌ 否 | `10` | 每页数据量大小 |
| `team_level` | `integer` | ❌ 否 | `1` | 店铺等级：0-总店或者管理单元;1-子店; |
| `kdt_id` | `integer` | ❌ 否 | `88888` | 店铺id |
| `yz_open_id` | `integer` | ✅ 是 | `123456` | 有赞用户id，用户在有赞的唯一id。推荐使用 |
| `request_id` | `string` | ❌ 否 | `sadsadafdafdsfsd` | UUID |
| `operator` | `string` | ❌ 否 | `zhangsan` | 操作人名字 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "数据"
    },
    "current_day": {
      "type": "integer",
      "description": "日期，如：20250611",
      "example": "20250611"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "uv": {
      "type": "integer",
      "description": "访客数",
      "example": "11"
    },
    "pv": {
      "type": "integer",
      "description": "浏览量",
      "example": "11"
    },
    "new_member_uv": {
      "type": "integer",
      "description": "新增会员数",
      "example": "11"
    },
    "hour": {
      "type": "integer",
      "description": "小时，如：10",
      "example": "12"
    },
    "yester_day": {
      "type": "object",
      "description": "昨天"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "current_day": "20250611",
  "kdt_id": "88888",
  "uv": "11",
  "pv": "11",
  "new_member_uv": "11",
  "hour": "12"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 数据 |
| `current_day` | `object` | ❌ 否 | `` | 当前时间，如：20250611 |
| `kdt_id` | `integer` | ❌ 否 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `uv` | `integer` | ❌ 否 | `11` | 访客数 |
| `pv` | `integer` | ❌ 否 | `11` | 浏览量 |
| `new_member_uv` | `integer` | ❌ 否 | `11` | 新增会员数 |
| `current_day` | `integer` | ❌ 否 | `20250611` | 日期，如：20250611 |
| `hour` | `integer` | ❌ 否 | `12` | 小时，如：10 |
| `yester_day` | `object` | ❌ 否 | `` | 昨天 |
| `kdt_id` | `integer` | ❌ 否 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `uv` | `integer` | ❌ 否 | `11` | 访客数 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4839

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "current_day": "20250611",
  "yz_open_id": "123456"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.realtime.query/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "current_day": "20250611",
  "yz_open_id": "123456"
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
| 服务名称 | `com.youzan.bigdata.datacenter.base.api.service.realtime.RealTimeServiceV2` |
| 方法名称 | `getRealTimeOverView` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4839)_