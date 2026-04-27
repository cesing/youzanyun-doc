---
apiName: "youzan.bigdata.useropenbehavior.query.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "data_center"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.customer.UserOpenBehaviorService"
method: "scan"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner]
deprecated: false
since: "2021-07-09"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3021"
---
# youzan.bigdata.useropenbehavior.query.1.0.0
> **所属分组**: data_center　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
店铺用户行为数据接口（大客户专属），每天早上9点更新前一天的用户行为数据
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "current_day": {
      "type": "string",
      "description": "日期，日期的格式为：yyyy-MM-dd",
      "example": "2021-07-08"
    },
    "page_num": {
      "type": "integer",
      "description": "页数",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页查看的条数",
      "example": "100"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `current_day` | `string` | ❌ 否 | `2021-07-08` | 日期，日期的格式为：yyyy-MM-dd |
| `page_num` | `integer` | ❌ 否 | `1` | 页数 |
| `page_size` | `integer` | ❌ 否 | `100` | 每页查看的条数 |
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
    "yz_uid": {
      "type": "string",
      "description": "有赞用户id",
      "example": "1"
    },
    "user_log_time": {
      "type": "integer",
      "description": "行为发生时间。13位时间戳",
      "example": "1234567891234"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "91619160"
    },
    "hq_kdt_id": {
      "type": "integer",
      "description": "连锁店铺,总店id,非连锁店铺等同于kdt_id",
      "example": "91619160"
    },
    "current_day": {
      "type": "string",
      "description": "日期，格式：yyyy-MM-dd",
      "example": "2021-07-08"
    },
    "page": {
      "type": "string",
      "description": "行为发生页面地址",
      "example": "https://shimo.im/docs/VMAPV72EwMSayEqg"
    },
    "page_title": {
      "type": "string",
      "description": "行为发生页面标题",
      "example": "埋点分析中间层"
    },
    "event_sign": {
      "type": "string",
      "description": "行为事件标识",
      "example": "enterpage"
    },
    "scene_level1": {
      "type": "string",
      "description": "流量来源第一级:小程序下为weapp",
      "example": "enterpage"
    },
    "scene_level2": {
      "type": "string",
      "description": "流量来源第二级:小程序下为wexin、alipay、baidu、qq等",
      "example": "enterpage"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "yz_uid": "1",
  "user_log_time": "1234567891234",
  "kdt_id": "91619160",
  "hq_kdt_id": "91619160",
  "current_day": "2021-07-08",
  "page": "https://shimo.im/docs/VMAPV72EwMSayEqg",
  "page_title": "埋点分析中间层"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` | 业务数据 |
| `yz_uid` | `string` | ❌ 否 | `1` | 有赞用户id |
| `user_log_time` | `integer` | ❌ 否 | `1234567891234` | 行为发生时间。13位时间戳 |
| `kdt_id` | `integer` | ❌ 否 | `91619160` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `hq_kdt_id` | `integer` | ❌ 否 | `91619160` | 连锁店铺,总店id,非连锁店铺等同于kdt_id |
| `current_day` | `string` | ❌ 否 | `2021-07-08` | 日期，格式：yyyy-MM-dd |
| `page` | `string` | ❌ 否 | `https://shimo.im/docs/VMAPV72E` | 行为发生页面地址 |
| `page_title` | `string` | ❌ 否 | `埋点分析中间层` | 行为发生页面标题 |
| `event_sign` | `string` | ❌ 否 | `enterpage` | 行为事件标识 |
| `scene_level1` | `string` | ❌ 否 | `enterpage` | 流量来源第一级:小程序下为weapp |
| `scene_level2` | `string` | ❌ 否 | `enterpage` | 流量来源第二级:小程序下为wexin、alipay、baidu、qq等 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3021

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.useropenbehavior.query/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {}

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
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3021)_