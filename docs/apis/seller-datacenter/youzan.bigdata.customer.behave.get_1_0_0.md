---
apiName: "youzan.bigdata.customer.behave.get.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "ka_customization"
method: "findCustomerBehavePage"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2020-11-19"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1562"
---
# youzan.bigdata.customer.behave.get.1.0.0
> **所属分组**: ka_customization　**所属应用**: seller-datacenter
---
## 1. 场景说明
获取小程序用户行为数据，当前是提供给腾讯有数
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.0`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "页面大小， 最大50",
      "example": "20"
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
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `page_no` | `integer` | ❌ | `1` | 页码 |
| `page_size` | `integer` | ❌ | `20` | 页面大小， 最大50 |
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
      "description": "响应参数"
    },
    "paginator": {
      "type": "string",
      "description": "页面信息"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "页面大小",
      "example": "20"
    },
    "total_count": {
      "type": "integer",
      "description": "总数据条数",
      "example": "907"
    },
    "items": {
      "type": "array",
      "description": "返回列表"
    },
    "current_day": {
      "type": "string",
      "description": "日期yyyy-MM-dd",
      "example": "2020-11-18"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "41433171"
    },
    "user_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用",
      "example": "LnhGm4rh576452722916618240"
    },
    "event_sign": {
      "type": "string",
      "description": "事件类型：小程序启动-performance ，小程序显示-enterapp，小程序隐藏-leaveapp，页面浏览-enterpage，搜索-search， 商品卡曝光-view_goods， 商品卡触发-open_goods，商品页浏览-enterpage，商品加购-add_cart",
      "example": "search"
    },
    "page_uri": {
      "type": "string",
      "description": "当前页uri",
      "example": "packages/salesman/salesman-center/index"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "paginator": "",
  "page_no": "1",
  "page_size": "20",
  "total_count": "907",
  "items": [],
  "current_day": "2020-11-18",
  "kdt_id": "41433171"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 响应参数 |
| `paginator` | `string` | ❌ | `` | 页面信息 |
| `page_no` | `integer` | ❌ | `1` | 页码 |
| `page_size` | `integer` | ❌ | `20` | 页面大小 |
| `total_count` | `integer` | ❌ | `907` | 总数据条数 |
| `items` | `array` | ❌ | `` | 返回列表 |
| `current_day` | `string` | ❌ | `2020-11-18` | 日期yyyy-MM-dd |
| `kdt_id` | `integer` | ❌ | `41433171` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `user_id` | `integer` | ❌ | `LnhGm4rh576452722916618240` | 有赞用户id，用户在有赞的唯一id。推荐使用 |
| `event_sign` | `string` | ❌ | `search` | 事件类型：小程序启动-performance ，小程序显示-enterapp，小程序隐藏-leaveapp，页面浏览-enterpage，搜索-search，  |
| `page_uri` | `string` | ❌ | `packages/salesman/salesman-center/index` | 当前页uri |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "page_no": "1",\n  "page_size": "20",\n  "event_sign": "search"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "page_no": "1",
    "page_size": "20",
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