---
apiName: "youzan.appstore.service.demand.order.query.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "appstore"
apiGroup: "customized_api"
serviceName: "com.youzan.cloud.appstore.api.service.open.AppstoreSubscribeQuery"
method: "getDemandOrderDetail"
timeout: "5000"
protocol: "dubbo"
authType: "OAuth"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2021-07-29"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3092"
---
# youzan.appstore.service.demand.order.query.1.0.0
> **所属分组**: customized_api　**所属应用**: appstore　**状态**: 已上线/变更中
---
## 1. 场景说明
服务需求订单查询订单金额（纷享销客，连接器使用）当data返回为空时，代表kdt_id和订单号无对应关系。当data有值时表示请求成功
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.service.demand.order.query/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `OAuth`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "tid": {
      "type": "string",
      "description": "有赞应用市场订单号",
      "example": "23202107272015210109053"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "demand_no": {
      "type": "string",
      "description": "需求号 （youzan.appstore.sevicedemand.query接口获取，demand_no字段）",
      "example": "12345"
    }
  },
  "required": [
    "tid",
    "kdt_id"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `tid` | `string` | ✅ 是 | `23202107272015210109053` | 有赞应用市场订单号 |
| `kdt_id` | `integer` | ✅ 是 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `demand_no` | `string` | ❌ 否 | `12345` | 需求号 （youzan.appstore.sevicedemand.query接口获取，demand_no字段） |
---
## 3. 响应
**响应参数 Schema**（6 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "data"
    },
    "tid": {
      "type": "string",
      "description": "有赞应用市场订单号",
      "example": "23202107272015210109053"
    },
    "price": {
      "type": "integer",
      "description": "订单金额（分）",
      "example": "123"
    },
    "success": {
      "type": "string",
      "description": "true",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "200",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "successful",
      "example": "successful"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "tid": "23202107272015210109053",
  "price": "123",
  "success": "true",
  "code": "200",
  "message": "successful"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | data |
| `tid` | `string` | ❌ 否 | `23202107272015210109053` | 有赞应用市场订单号 |
| `price` | `integer` | ❌ 否 | `123` | 订单金额（分） |
| `success` | `string` | ❌ 否 | `true` | true |
| `code` | `string` | ❌ 否 | `200` | 200 |
| `message` | `string` | ❌ 否 | `successful` | successful |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3092

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "tid": "23202107272015210109053",
  "kdt_id": "88888"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.service.demand.order.query/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "tid": "23202107272015210109053",
  "kdt_id": "88888"
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
| 服务名称 | `com.youzan.cloud.appstore.api.service.open.AppstoreSubscribeQuery` |
| 方法名称 | `getDemandOrderDetail` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3092)_