---
apiName: "youzan.cardvoucher.datasync.import.cardfundchangeresultquery.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardDataSyncOpenService"
method: "querySyncCardFundChangeResult"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, retail_d_partner, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offline, retail_offline_channel, retail_partner, edu, edu_head, edu_branch]
deprecated: false
since: "2023-02-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3996"
---
# youzan.cardvoucher.datasync.import.cardfundchangeresultquery.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
搭配youzan.cardvoucher.datasync.import.cardfundchange使用；回流接口响应成功后可通过本接口查询结果，通常5s内能返回明确的结果，如果返回的是PROCRSSING处理中，一般是未能正确被处理(比如关联流水还未写入会尝试等待)，内部会进行补偿处理，3次补偿仍未成功当做失败处理，因此建议轮询查询时间间隔为：回流后的2s,回流后的5s,回流后的35s,回流后的65s...后续间隔30s查询一次至明确成功或失败
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchangeresultquery/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": ""
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "out_uniq_water_no": {
      "type": "string",
      "description": "外部系统储值卡流水号，必填说明：储值卡流水的唯一标识",
      "example": "1111"
    }
  },
  "required": [
    "root_kdt_id",
    "out_uniq_water_no"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` |  |
| `root_kdt_id` | `integer` | ✅ 是 | `232423` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `out_uniq_water_no` | `string` | ✅ 是 | `1111` | 外部系统储值卡流水号，必填说明：储值卡流水的唯一标识 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": ""
    },
    "process_status": {
      "type": "string",
      "description": "流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败",
      "example": "FAIL"
    },
    "extra": {
      "type": "string",
      "description": "扩展信息",
      "example": "{\"\":\"\"}"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "out_water_no": {
      "type": "string",
      "description": "外部唯一流水号",
      "example": "1111"
    },
    "card_no": {
      "type": "string",
      "description": "储值卡号",
      "example": "aaaaa"
    },
    "fail_reason": {
      "type": "string",
      "description": "处理失败原因",
      "example": "开卡失败，本流水仅允许充值类型开卡"
    },
    "success": {
      "type": "string",
      "description": "true",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "200",
      "example": "118711202"
    },
    "message": {
      "type": "string",
      "description": ""
    },
    "request_id": {
      "type": "string",
      "description": ""
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "process_status": "FAIL",
  "extra": "{\"\":\"\"}",
  "root_kdt_id": "232423",
  "out_water_no": "1111",
  "card_no": "aaaaa",
  "fail_reason": "开卡失败，本流水仅允许充值类型开卡",
  "success": "true"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `process_status` | `string` | ❌ 否 | `FAIL` | 流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败 |
| `extra` | `string` | ❌ 否 | `{"":""}` | 扩展信息 |
| `root_kdt_id` | `integer` | ❌ 否 | `232423` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `out_water_no` | `string` | ❌ 否 | `1111` | 外部唯一流水号 |
| `card_no` | `string` | ❌ 否 | `aaaaa` | 储值卡号 |
| `fail_reason` | `string` | ❌ 否 | `开卡失败，本流水仅允许充值类型开卡` | 处理失败原因 |
| `success` | `string` | ❌ 否 | `true` | true |
| `code` | `string` | ❌ 否 | `118711202` | 200 |
| `message` | `string` | ❌ 否 | `` |  |
| `request_id` | `string` | ❌ 否 | `` |  |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3996

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "root_kdt_id": "232423",
  "out_uniq_water_no": "1111"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchangeresultquery/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "root_kdt_id": "232423",
  "out_uniq_water_no": "1111"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardDataSyncOpenService` |
| 方法名称 | `querySyncCardFundChangeResult` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3996)_