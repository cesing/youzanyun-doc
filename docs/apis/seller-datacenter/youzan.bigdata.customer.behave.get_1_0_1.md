---
apiName: "youzan.bigdata.customer.behave.get.1.0.1"
version: "1.0.1"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "ka_customization"
serviceName: "com.youzan.bigdata.datacenter.wsc.api.service.customer.CustomerBehaveDayService"
method: "findCustomerBehavePage"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner]
deprecated: false
since: "2020-11-24"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1584"
---
# youzan.bigdata.customer.behave.get.1.0.1
> **所属分组**: ka_customization　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
获取小程序用户行为数据，当前是提供给腾讯有数
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "start_id": {
      "type": "integer",
      "description": "上一次获取列表最后一个id",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "页面大小，默认10，最大限制50",
      "example": "10"
    },
    "kdt_id_list": {
      "type": "integer",
      "description": "需要获取的店铺列表",
      "example": "[41433171L]"
    },
    "event_sign": {
      "type": "string",
      "description": "事件信息： 小程序启动- performance ，小程序显示- enterapp，小程序隐藏-leaveapp，页面浏览- enterpage，搜索-search， 商品卡曝光-view_goods， 商品卡触发-open_goods，商品页浏览-enterpage，商品加购-add_cart",
      "example": "search"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `start_id` | `integer` | ❌ 否 | `1` | 上一次获取列表最后一个id |
| `page_size` | `integer` | ❌ 否 | `10` | 页面大小，默认10，最大限制50 |
| `kdt_id_list` | `integer` | ❌ 否 | `[41433171L]` | 需要获取的店铺列表 |
| `event_sign` | `string` | ❌ 否 | `search` | 事件信息： 小程序启动- performance ，小程序显示- enterapp，小程序隐藏-leaveapp，页面浏 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "返回列表"
    },
    "id": {
      "type": "integer",
      "description": "数据唯一标识",
      "example": "1"
    },
    "current_day": {
      "type": "string",
      "description": "日期，格式：yyyy-MM-dd",
      "example": "2020-11-23"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "8888"
    },
    "user_id": {
      "type": "integer",
      "description": "有赞客户userId",
      "example": "8106822293"
    },
    "event_sign": {
      "type": "string",
      "description": "事件类型,performance:小程序启动,enterapp:小程序显示,leaveapp:小程序隐藏,enterpage:页面浏览,share:页面分享,search:搜索,view_goods:商品卡曝光,open_goods:商品卡触发,add_cart:商品加购,商品页浏览:exposure_goods",
      "example": "search"
    },
    "page_uri": {
      "type": "string",
      "description": "当前页uri",
      "example": "packages/salesman/salesman-center/index"
    },
    "page_title": {
      "type": "string",
      "description": "页面标题",
      "example": "搜索"
    },
    "sdk_version": {
      "type": "string",
      "description": "sdk版本",
      "example": "2.14.0"
    },
    "user_log_time": {
      "type": "integer",
      "description": "用户行为触发时间。时间戳，单位：毫秒。",
      "example": "1605680523000"
    },
    "app_id": {
      "type": "string",
      "description": "公众号或小程序唯一id",
      "example": "wx12530dfd1c7709a6"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "id": "1",
  "current_day": "2020-11-23",
  "kdt_id": "8888",
  "user_id": "8106822293",
  "event_sign": "search",
  "page_uri": "packages/salesman/salesman-center/index",
  "page_title": "搜索"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` | 返回列表 |
| `id` | `integer` | ❌ 否 | `1` | 数据唯一标识 |
| `current_day` | `string` | ❌ 否 | `2020-11-23` | 日期，格式：yyyy-MM-dd |
| `kdt_id` | `integer` | ❌ 否 | `8888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `user_id` | `integer` | ❌ 否 | `8106822293` | 有赞客户userId |
| `event_sign` | `string` | ❌ 否 | `search` | 事件类型,performance:小程序启动,enterapp:小程序显示,leaveapp:小程序隐藏,enterpa |
| `page_uri` | `string` | ❌ 否 | `packages/salesman/salesman-cen` | 当前页uri |
| `page_title` | `string` | ❌ 否 | `搜索` | 页面标题 |
| `sdk_version` | `string` | ❌ 否 | `2.14.0` | sdk版本 |
| `user_log_time` | `integer` | ❌ 否 | `1605680523000` | 用户行为触发时间。时间戳，单位：毫秒。 |
| `app_id` | `string` | ❌ 否 | `wx12530dfd1c7709a6` | 公众号或小程序唯一id |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1584

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.1"
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
| 服务名称 | `com.youzan.bigdata.datacenter.wsc.api.service.customer.CustomerBehaveDayService` |
| 方法名称 | `findCustomerBehavePage` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1584)_