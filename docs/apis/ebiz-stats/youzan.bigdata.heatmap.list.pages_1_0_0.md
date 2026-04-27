---
apiName: "youzan.bigdata.heatmap.list.pages.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "ebiz-stats"
apiGroup: "data_center"
serviceName: "com.youzan.ebiz.stats.biz.heatmap.dubboapi.HeatMapNewService"
method: "getPages"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc]
deprecated: false
since: "2023-05-18"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4075"
---
# youzan.bigdata.heatmap.list.pages.1.0.0
> **所属分组**: data_center　**所属应用**: ebiz-stats　**状态**: 已上线/变更中
---
## 1. 场景说明
获取热力图页面列表,分页方式获取页面列表。支持页面模糊搜索和页面类型的筛选。返回的id为热力图id，后续查询页面统计信息时传递上述id进行查询。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.heatmap.list.pages/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "page_type": {
      "type": "string",
      "description": "热力图页面类型。微页面：f，商详页g，不传查全部",
      "example": "f"
    },
    "page_name": {
      "type": "string",
      "description": "热力图页面名称模糊搜索",
      "example": "主页"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页大小",
      "example": "10"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `page_type` | `string` | ❌ 否 | `f` | 热力图页面类型。微页面：f，商详页g，不传查全部 |
| `page_name` | `string` | ❌ 否 | `主页` | 热力图页面名称模糊搜索 |
| `page_no` | `integer` | ❌ 否 | `1` | 页码 |
| `page_size` | `integer` | ❌ 否 | `10` | 每页大小 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "结果"
    },
    "paginator": {
      "type": "object",
      "description": "分页结果"
    },
    "page_no": {
      "type": "string",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "每页大小",
      "example": "10"
    },
    "total_count": {
      "type": "string",
      "description": "总数",
      "example": "15"
    },
    "items": {
      "type": "array",
      "description": "热力图页面信息列表"
    },
    "id": {
      "type": "integer",
      "description": "热力图id，查询热力图统计数据时使用",
      "example": "1"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "page_id": {
      "type": "integer",
      "description": "商品或者微页面id",
      "example": "123"
    },
    "page_alias": {
      "type": "string",
      "description": "商品或者微页面别名",
      "example": "ffff"
    },
    "page_name": {
      "type": "string",
      "description": "商品或者微页面名称",
      "example": "主页面"
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
  "page_size": "10",
  "total_count": "15",
  "items": [],
  "id": "1",
  "kdt_id": "88888"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 结果 |
| `paginator` | `object` | ❌ 否 | `` | 分页结果 |
| `page_no` | `string` | ❌ 否 | `1` | 页码 |
| `page_size` | `string` | ❌ 否 | `10` | 每页大小 |
| `total_count` | `string` | ❌ 否 | `15` | 总数 |
| `items` | `array` | ❌ 否 | `` | 热力图页面信息列表 |
| `id` | `integer` | ❌ 否 | `1` | 热力图id，查询热力图统计数据时使用 |
| `kdt_id` | `integer` | ❌ 否 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `page_id` | `integer` | ❌ 否 | `123` | 商品或者微页面id |
| `page_alias` | `string` | ❌ 否 | `ffff` | 商品或者微页面别名 |
| `page_name` | `string` | ❌ 否 | `主页面` | 商品或者微页面名称 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4075

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.heatmap.list.pages/1.0.0"
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
| 服务名称 | `com.youzan.ebiz.stats.biz.heatmap.dubboapi.HeatMapNewService` |
| 方法名称 | `getPages` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4075)_