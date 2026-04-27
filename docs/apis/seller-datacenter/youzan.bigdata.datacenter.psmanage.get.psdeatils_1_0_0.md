---
apiName: "youzan.bigdata.datacenter.psmanage.get.psdeatils.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.yunapi.ManagePageSourceYunService"
method: "getPsDetailData"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2021-12-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3485"
---
# youzan.bigdata.datacenter.psmanage.get.psdeatils.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
获取单个推广监控数据详情(包含明细和汇总)
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psdeatils/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（7 个参数）:
```json
{
  "type": "object",
  "properties": {
    "ps_code": {
      "type": "string",
      "description": "dcps号",
      "example": "2118722746287589378.200001"
    },
    "attribution_period": {
      "type": "integer",
      "description": "归因周期当天:1,七天:7,15天:15,30天:30@seePsAttributionPeriodEnum",
      "example": "1"
    },
    "statistical_scope": {
      "type": "integer",
      "description": "统计范围全部转化数据：空，推广页直接转化数据：2，连带销售：3@seePsStatisticalScopeTypeEnum",
      "example": "1"
    },
    "attribution_type": {
      "type": "integer",
      "description": "归因方式首次1，末次2@seePsAttributionTypeEnum",
      "example": "1"
    },
    "start_day": {
      "type": "string",
      "description": "开始时间yyyy-MM-dd",
      "example": "2021-12-01"
    },
    "end_day": {
      "type": "string",
      "description": "结束时间yyyy-MM-dd",
      "example": "2021-12-02"
    },
    "node_kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。连锁总部查询汇总数据不传该字段",
      "example": "88888"
    }
  },
  "required": [
    "ps_code",
    "attribution_period",
    "attribution_type",
    "start_day",
    "end_day"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `ps_code` | `string` | ✅ 是 | `2118722746287589378.200001` | dcps号 |
| `attribution_period` | `integer` | ✅ 是 | `1` | 归因周期当天:1,七天:7,15天:15,30天:30@seePsAttributionPeriodEnum |
| `statistical_scope` | `integer` | ❌ 否 | `1` | 统计范围全部转化数据：空，推广页直接转化数据：2，连带销售：3@seePsStatisticalScopeTypeEnu |
| `attribution_type` | `integer` | ✅ 是 | `1` | 归因方式首次1，末次2@seePsAttributionTypeEnum |
| `start_day` | `string` | ✅ 是 | `2021-12-01` | 开始时间yyyy-MM-dd |
| `end_day` | `string` | ✅ 是 | `2021-12-02` | 结束时间yyyy-MM-dd |
| `node_kdt_id` | `integer` | ❌ 否 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。连锁总部查询汇总数据不传该字段 |
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
    "summary_data": {
      "type": "object",
      "description": "汇总数据这里会给算一遍,实时数据的UV之类要去重，并不是明细数据相加"
    },
    "time": {
      "type": "string",
      "description": "按日期维度的详细数据，如果是今日实时，则小时展示为0,1……,22,23如果是天，则key为2018-01-01",
      "example": "all"
    },
    "pv": {
      "type": "integer",
      "description": "浏览量",
      "example": "1"
    },
    "uv": {
      "type": "integer",
      "description": "访客数",
      "example": "1"
    },
    "landing_pv": {
      "type": "integer",
      "description": "到达浏览量",
      "example": "1"
    },
    "landing_uv": {
      "type": "integer",
      "description": "到达访客数",
      "example": "1"
    },
    "new_uv": {
      "type": "integer",
      "description": "到达新访客数",
      "example": "1"
    },
    "share_pv": {
      "type": "integer",
      "description": "分享浏览量",
      "example": "1"
    },
    "share_uv": {
      "type": "integer",
      "description": "分享访客数",
      "example": "1"
    },
    "click_pv": {
      "type": "integer",
      "description": "二跳浏览量",
      "example": "1"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "summary_data": "",
  "time": "all",
  "pv": "1",
  "uv": "1",
  "landing_pv": "1",
  "landing_uv": "1",
  "new_uv": "1"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 结果 |
| `summary_data` | `object` | ❌ 否 | `` | 汇总数据这里会给算一遍,实时数据的UV之类要去重，并不是明细数据相加 |
| `time` | `string` | ❌ 否 | `all` | 按日期维度的详细数据，如果是今日实时，则小时展示为0,1……,22,23如果是天，则key为2018-01-01 |
| `pv` | `integer` | ❌ 否 | `1` | 浏览量 |
| `uv` | `integer` | ❌ 否 | `1` | 访客数 |
| `landing_pv` | `integer` | ❌ 否 | `1` | 到达浏览量 |
| `landing_uv` | `integer` | ❌ 否 | `1` | 到达访客数 |
| `new_uv` | `integer` | ❌ 否 | `1` | 到达新访客数 |
| `share_pv` | `integer` | ❌ 否 | `1` | 分享浏览量 |
| `share_uv` | `integer` | ❌ 否 | `1` | 分享访客数 |
| `click_pv` | `integer` | ❌ 否 | `1` | 二跳浏览量 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3485

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "ps_code": "2118722746287589378.200001",
  "attribution_period": "1",
  "attribution_type": "1",
  "start_day": "2021-12-01",
  "end_day": "2021-12-02"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psdeatils/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "ps_code": "2118722746287589378.200001",
  "attribution_period": "1",
  "attribution_type": "1",
  "start_day": "2021-12-01",
  "end_day": "2021-12-02"
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
| 方法名称 | `getPsDetailData` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3485)_