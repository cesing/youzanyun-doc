---
apiName: "youzan.bigdata.datacenter.psmanage.get.psorder.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.yunapi.ManagePageSourceYunService"
method: "fetchAttrPsOrderInfo"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2021-12-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3486"
---
# youzan.bigdata.datacenter.psmanage.get.psorder.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
按天获取某个推广分析下的订单，仅支持离线，不支持今日实时
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psorder/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（8 个参数）:
```json
{
  "type": "object",
  "properties": {
    "attribution_period": {
      "type": "integer",
      "description": "归因周期。当天:1,七天:7,15天:15,30天:30",
      "example": "1"
    },
    "statistical_scope": {
      "type": "integer",
      "description": "统计范围 。 全部转化数据：不传、 推广页直接转化数据：2、连带销售：3",
      "example": "1"
    },
    "attribution_type": {
      "type": "integer",
      "description": "归因方式 。 首次1、末次2",
      "example": "1"
    },
    "dcps": {
      "type": "string",
      "description": "推广监控标识",
      "example": "2956668732916707328.200001"
    },
    "current_day": {
      "type": "integer",
      "description": "导出日期",
      "example": "20211201"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用店铺管理员id",
      "example": "LnhGm4rh576452722916618240"
    },
    "page_no": {
      "type": "integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "integer",
      "description": "每页条数。默认100条",
      "example": "100"
    }
  },
  "required": [
    "attribution_period",
    "attribution_type",
    "dcps",
    "current_day",
    "yz_open_id",
    "page_no",
    "page_size"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `attribution_period` | `integer` | ✅ 是 | `1` | 归因周期。当天:1,七天:7,15天:15,30天:30 |
| `statistical_scope` | `integer` | ❌ 否 | `1` | 统计范围 。 全部转化数据：不传、 推广页直接转化数据：2、连带销售：3 |
| `attribution_type` | `integer` | ✅ 是 | `1` | 归因方式 。 首次1、末次2 |
| `dcps` | `string` | ✅ 是 | `2956668732916707328.200001` | 推广监控标识 |
| `current_day` | `integer` | ✅ 是 | `20211201` | 导出日期 |
| `yz_open_id` | `integer` | ✅ 是 | `LnhGm4rh576452722916618240` | 有赞用户id，用户在有赞的唯一id。推荐使用店铺管理员id |
| `page_no` | `integer` | ✅ 是 | `1` | 页码 |
| `page_size` | `integer` | ✅ 是 | `100` | 每页条数。默认100条 |
---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "返回结果"
    },
    "paginator": {
      "type": "object",
      "description": "分页结果信息"
    },
    "page_no": {
      "type": "string",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "string",
      "description": "条数",
      "example": "100"
    },
    "total_count": {
      "type": "string",
      "description": "分页查询的总条数",
      "example": "1000"
    },
    "items": {
      "type": "string",
      "description": "订单集合",
      "example": "['E10001','E1002']"
    },
    "success": {
      "type": "string",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "参数缺失"
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
  "page_size": "100",
  "total_count": "1000",
  "items": "['E10001','E1002']",
  "success": "true",
  "code": "200"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 返回结果 |
| `paginator` | `object` | ❌ 否 | `` | 分页结果信息 |
| `page_no` | `string` | ❌ 否 | `1` | 页码 |
| `page_size` | `string` | ❌ 否 | `100` | 条数 |
| `total_count` | `string` | ❌ 否 | `1000` | 分页查询的总条数 |
| `items` | `string` | ❌ 否 | `['E10001','E1002']` | 订单集合 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200 :成功。 |
| `message` | `string` | ❌ 否 | `参数缺失` | 网关返回码描述 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3486

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "attribution_period": "1",
  "attribution_type": "1",
  "dcps": "2956668732916707328.200001",
  "current_day": "20211201",
  "yz_open_id": "LnhGm4rh576452722916618240"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psorder/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "attribution_period": "1",
  "attribution_type": "1",
  "dcps": "2956668732916707328.200001",
  "current_day": "20211201",
  "yz_open_id": "LnhGm4rh576452722916618240"
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
| 服务名称 | `com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.yunapi.ManagePageSourceYunService` |
| 方法名称 | `fetchAttrPsOrderInfo` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3486)_