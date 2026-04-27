---
apiName: "youzan.bigdata.useropenbehavior.query.1.0.1"
version: "1.0.1"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "data_center"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.customer.UserOpenBehaviorService"
method: "scan"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail_head_high]
deprecated: false
since: "2021-07-13"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3033"
---
# youzan.bigdata.useropenbehavior.query.1.0.1
> **所属分组**: data_center　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
店铺用户行为数据接口（大客户专属），每天早上9点更新前一天的用户行为数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "current_day": {
      "type": "string",
      "description": "日期，日期的格式为：yyyy-MM-dd,只支持获取昨日数据",
      "example": "2021-07-08"
    },
    "page_no": {
      "type": "integer",
      "description": "分页信息_页数",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "分页信息_每页的条数，最小为1，最大为100",
      "example": "10"
    }
  },
  "required": [
    "current_day",
    "page_no",
    "page_size"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `current_day` | `string` | ✅ 是 | `2021-07-08` | 日期，日期的格式为：yyyy-MM-dd,只支持获取昨日数据 |
| `page_no` | `integer` | ✅ 是 | `1` | 分页信息_页数 |
| `page_size` | `integer` | ✅ 是 | `10` | 分页信息_每页的条数，最小为1，最大为100 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "业务数据"
    },
    "yz_open_id": {
      "type": "string",
      "description": "有赞客户id，客户在有赞的唯一id",
      "example": "LnhGm4rh576452722916618240"
    },
    "user_log_time": {
      "type": "integer",
      "description": "行为发生时间。13位时间戳。毫秒",
      "example": "1626056989619"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "888888"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "888888"
    },
    "current_day": {
      "type": "string",
      "description": "日期，格式：yyyyMMdd",
      "example": "20210708"
    },
    "page_url": {
      "type": "string",
      "description": "用户行为发生的页面地址",
      "example": "https://www.youzan.com/"
    },
    "page_title": {
      "type": "string",
      "description": "用户行为发生的页面标题",
      "example": "主页"
    },
    "event_sign": {
      "type": "string",
      "description": "用户行为的事件标识,枚举值过多，具体参见每个大客的大客文档",
      "example": "enterpage"
    },
    "scene_level1": {
      "type": "string",
      "description": "流量来源的一级分类：渠道",
      "example": "h5"
    },
    "scene_level2": {
      "type": "string",
      "description": "流量来源的二级分类：小程序下为wexin、alipay、baidu、qq等",
      "example": "weixin"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "yz_open_id": "LnhGm4rh576452722916618240",
  "user_log_time": "1626056989619",
  "kdt_id": "888888",
  "root_kdt_id": "888888",
  "current_day": "20210708",
  "page_url": "https://www.youzan.com/",
  "page_title": "主页"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` | 业务数据 |
| `yz_open_id` | `string` | ❌ 否 | `LnhGm4rh576452722916618240` | 有赞客户id，客户在有赞的唯一id |
| `user_log_time` | `integer` | ❌ 否 | `1626056989619` | 行为发生时间。13位时间戳。毫秒 |
| `kdt_id` | `integer` | ❌ 否 | `888888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `root_kdt_id` | `integer` | ❌ 否 | `888888` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `current_day` | `string` | ❌ 否 | `20210708` | 日期，格式：yyyyMMdd |
| `page_url` | `string` | ❌ 否 | `https://www.youzan.com/` | 用户行为发生的页面地址 |
| `page_title` | `string` | ❌ 否 | `主页` | 用户行为发生的页面标题 |
| `event_sign` | `string` | ❌ 否 | `enterpage` | 用户行为的事件标识,枚举值过多，具体参见每个大客的大客文档 |
| `scene_level1` | `string` | ❌ 否 | `h5` | 流量来源的一级分类：渠道 |
| `scene_level2` | `string` | ❌ 否 | `weixin` | 流量来源的二级分类：小程序下为wexin、alipay、baidu、qq等 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3033

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "current_day": "2021-07-08",
  "page_no": "1",
  "page_size": "10"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.1"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "current_day": "2021-07-08",
  "page_no": "1",
  "page_size": "10"
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
| 服务名称 | `com.youzan.bigdata.datacenter.base.api.service.customer.UserOpenBehaviorService` |
| 方法名称 | `scan` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3033)_