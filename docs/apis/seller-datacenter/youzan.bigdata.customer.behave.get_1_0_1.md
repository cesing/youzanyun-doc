---
apiName: "youzan.bigdata.customer.behave.get.1.0.1"
version: "1.0.1"
appName: "seller-datacenter"
apiGroup: "ka_customization"
method: "findCustomerBehavePage"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2020-11-24"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1584"
---
# youzan.bigdata.customer.behave.get.1.0.1
> **所属分组**: ka_customization　**所属应用**: seller-datacenter
---
## 1. 场景说明
获取小程序用户行为数据，当前是提供给腾讯有数
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.1`
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
  "required": []
}
```
**请求参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `start_id` | `integer` | ❌ | `1` | 上一次获取列表最后一个id |
| `page_size` | `integer` | ❌ | `10` | 页面大小，默认10，最大限制50 |
| `kdt_id_list` | `integer` | ❌ | `[41433171L]` | 需要获取的店铺列表 |
| `event_sign` | `string` | ❌ | `search` | 事件信息： 小程序启动- performance ，小程序显示- enterapp，小程序隐藏-leaveapp，页面浏览- enterpage，搜索-sear |
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
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 返回列表 |
| `id` | `integer` | ❌ | `1` | 数据唯一标识 |
| `current_day` | `string` | ❌ | `2020-11-23` | 日期，格式：yyyy-MM-dd |
| `kdt_id` | `integer` | ❌ | `8888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `user_id` | `integer` | ❌ | `8106822293` | 有赞客户userId |
| `event_sign` | `string` | ❌ | `search` | 事件类型,performance:小程序启动,enterapp:小程序显示,leaveapp:小程序隐藏,enterpage:页面浏览,share:页面分享,s |
| `page_uri` | `string` | ❌ | `packages/salesman/salesman-center/index` | 当前页uri |
| `page_title` | `string` | ❌ | `搜索` | 页面标题 |
| `sdk_version` | `string` | ❌ | `2.14.0` | sdk版本 |
| `user_log_time` | `integer` | ❌ | `1605680523000` | 用户行为触发时间。时间戳，单位：毫秒。 |
| `app_id` | `string` | ❌ | `wx12530dfd1c7709a6` | 公众号或小程序唯一id |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "start_id": "1",\n  "page_size": "10",\n  "kdt_id_list": "[41433171L]",\n  "event_sign": "search"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.1"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "start_id": "1",
    "page_size": "10",
    "kdt_id_list": "[41433171L]",
    "event_sign": "search"
}

resp = requests.post(url, json=payload, headers=headers)
print(resp.json())
```
---
## 5. 错误码
| 错误码 | 类型 | 说明 |
|--------|------|------|
| 10001 | `SYSTEM_ERROR` | 系统内部错误 |
| 10002 | `INVALID_PARAMETER` | 参数错误 |
| 10003 | `UNAUTHORIZED` | 未授权或授权已过期 |
| 10004 | `PERMISSION_DENIED` | 无权限调用此接口 |
| 10005 | `RESOURCE_NOT_FOUND` | 请求的资源不存在 |
| 20001 | `RATE_LIMIT_EXCEEDED` | 调用频率超限 |
| 20002 | `QUOTA_EXCEEDED` | 接口配额已用完 |
---
## 6. 权限与计费

**接口计费状态：未知（请以官网实际披露为准）。**

**拥有此API的能力包：** 暂无数据（请以官网实际披露为准）。

---
## 7. 权限说明

**应用类目 → 权限类型：**

| 应用类目 | 权限类型 |
|----------|----------|
| 有赞微商城、有赞零售、有赞教育、有赞美业 | 普通自研商家（基础权益） |
| 大客户定制接口、美业大客户定制、零售大客户定制、收款二维码-大客专用 | 大客定制接口（需购买大客套餐） |
| 客户关系CRM、门店POS | iPaaS 套餐权益（需购买 iPaaS 套餐） |

> 权限数据来源：[有赞云能力包说明](https://doc.youzanyun.com/detail/content/API/0/120)