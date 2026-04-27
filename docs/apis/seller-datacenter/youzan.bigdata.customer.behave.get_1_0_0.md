---
apiName: "youzan.bigdata.customer.behave.get.1.0.0"
version: "1.0.0"
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
since: "2020-11-19"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1562"
---
# youzan.bigdata.customer.behave.get.1.0.0
> **所属分组**: ka_customization　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
获取小程序用户行为数据，当前是提供给腾讯有数
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `page_no` | `integer` | ❌ 否 | `1` | 页码 |
| `page_size` | `integer` | ❌ 否 | `20` | 页面大小， 最大50 |
| `event_sign` | `string` | ❌ 否 | `search` | 事件信息： 小程序启动- performance ，小程序显示- enterapp，小程序隐藏-leaveapp，页面浏 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "响应参数"
    },
    "paginator": {
      "type": "object",
      "description": "页面信息"
    },
    "page_no": {
      "type": "string",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "页面大小",
      "example": "20"
    },
    "total_count": {
      "type": "string",
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
  "data": "",
  "paginator": "",
  "page_no": "1",
  "page_size": "20",
  "total_count": "907",
  "items": [],
  "current_day": "2020-11-18",
  "kdt_id": "41433171"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 响应参数 |
| `paginator` | `object` | ❌ 否 | `` | 页面信息 |
| `page_no` | `string` | ❌ 否 | `1` | 页码 |
| `page_size` | `string` | ❌ 否 | `20` | 页面大小 |
| `total_count` | `string` | ❌ 否 | `907` | 总数据条数 |
| `items` | `array` | ❌ 否 | `` | 返回列表 |
| `current_day` | `string` | ❌ 否 | `2020-11-18` | 日期yyyy-MM-dd |
| `kdt_id` | `integer` | ❌ 否 | `41433171` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `user_id` | `integer` | ❌ 否 | `LnhGm4rh576452722916618240` | 有赞用户id，用户在有赞的唯一id。推荐使用 |
| `event_sign` | `string` | ❌ 否 | `search` | 事件类型：小程序启动-performance ，小程序显示-enterapp，小程序隐藏-leaveapp，页面浏览-e |
| `page_uri` | `string` | ❌ 否 | `packages/salesman/salesman-cen` | 当前页uri |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1562

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.customer.behave.get/1.0.0"
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
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1562)_