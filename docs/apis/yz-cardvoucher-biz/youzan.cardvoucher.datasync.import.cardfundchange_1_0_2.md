---
apiName: "youzan.cardvoucher.datasync.import.cardfundchange.1.0.2"
version: "1.0.2"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardDataSyncOpenService"
method: "syncCardFundChange"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail, 101, 102, 103, 2, 1, 1, 1, 1, 1, 1]
deprecated: false
since: "2023-02-13"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3990"
---
# youzan.cardvoucher.datasync.import.cardfundchange.1.0.2
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
接入前请阅读调用注意事项：https://doc.youzanyun.com/resource/doc/3404/5593
本接口需配合
youzan.cardvoucher.datasync.import.cardfundchangeresultquery进行同步结果查询使用
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.2`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（11 个参数）:
```json
{
  "type": "object",
  "properties": {
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，为发生交易的门网店",
      "example": "60102804"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "总部店铺id",
      "example": "60102626"
    },
    "out_uniq_water_no": {
      "type": "string",
      "description": "外部系统储值卡流水号，必填。说明：储值卡流水的唯一标识,如请求明确失败重试需换单号",
      "example": "HBYTESTIMPORT0103"
    },
    "client_source": {
      "type": "string",
      "description": "请求来源业务方标识，必填，比如烘焙云：HONGBEIYUN",
      "example": "open"
    },
    "user_info": {
      "type": "object",
      "description": "用户信息"
    },
    "mobile_no": {
      "type": "string",
      "description": "手机号",
      "example": "13186972611"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "用户id",
      "example": "7j3Gi1UH732330877366837248"
    },
    "user_name": {
      "type": "string",
      "description": "用户名称",
      "example": "木七"
    },
    "user_nick_name": {
      "type": "string",
      "description": "用户昵称",
      "example": "木七"
    },
    "card_no": {
      "type": "string",
      "description": "卡号，必填",
      "example": "1234567891271"
    },
    "card_type": {
      "type": "string",
      "description": "卡类型：1001储值余额卡 1002 储值卡(即礼品卡) 默认为余额卡",
      "example": "1001"
    }
  },
  "required": [
    "kdt_id",
    "root_kdt_id",
    "out_uniq_water_no",
    "client_source",
    "user_info",
    "yz_open_id",
    "card_no",
    "card_type"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `kdt_id` | `integer` | ✅ 是 | `60102804` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，为发生交易的门网店 |
| `root_kdt_id` | `integer` | ✅ 是 | `60102626` | 总部店铺id |
| `out_uniq_water_no` | `string` | ✅ 是 | `HBYTESTIMPORT0103` | 外部系统储值卡流水号，必填。说明：储值卡流水的唯一标识,如请求明确失败重试需换单号 |
| `client_source` | `string` | ✅ 是 | `open` | 请求来源业务方标识，必填，比如烘焙云：HONGBEIYUN |
| `user_info` | `object` | ✅ 是 | `` | 用户信息 |
| `mobile_no` | `string` | ❌ 否 | `13186972611` | 手机号 |
| `yz_open_id` | `integer` | ✅ 是 | `7j3Gi1UH732330877366837248` | 用户id |
| `user_name` | `string` | ❌ 否 | `木七` | 用户名称 |
| `user_nick_name` | `string` | ❌ 否 | `木七` | 用户昵称 |
| `card_no` | `string` | ✅ 是 | `1234567891271` | 卡号，必填 |
| `card_type` | `string` | ✅ 是 | `1001` | 卡类型：1001储值余额卡 1002 储值卡(即礼品卡) 默认为余额卡 |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "同步储值卡资金变动流水信息至有赞接口响应参数"
    },
    "extra": {
      "type": "string",
      "description": "扩展信息",
      "example": "{\"\":\"\"}"
    },
    "process_status": {
      "type": "string",
      "description": "流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败",
      "example": "SUCCESS"
    },
    "fail_reason": {
      "type": "string",
      "description": "处理失败原因",
      "example": "开卡失败，本流水仅允许充值类型开卡"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "总部kdtid",
      "example": "60102626"
    },
    "out_water_no": {
      "type": "string",
      "description": "外部系统储值卡唯一流水号",
      "example": "HBYTESTIMPORT0103"
    },
    "card_no": {
      "type": "string",
      "description": "卡号",
      "example": "1234567891271"
    },
    "success": {
      "type": "string",
      "description": "true",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "180001",
      "example": "001"
    },
    "message": {
      "type": "string",
      "description": "SUCCESS",
      "example": "success"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "extra": "{\"\":\"\"}",
  "process_status": "SUCCESS",
  "fail_reason": "开卡失败，本流水仅允许充值类型开卡",
  "root_kdt_id": "60102626",
  "out_water_no": "HBYTESTIMPORT0103",
  "card_no": "1234567891271",
  "success": "true"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 同步储值卡资金变动流水信息至有赞接口响应参数 |
| `extra` | `string` | ❌ 否 | `{"":""}` | 扩展信息 |
| `process_status` | `string` | ❌ 否 | `SUCCESS` | 流水处理状态：PROCESSING 处理中；SUCCESS：处理成功 ；FAIL 处理失败 |
| `fail_reason` | `string` | ❌ 否 | `开卡失败，本流水仅允许充值类型开卡` | 处理失败原因 |
| `root_kdt_id` | `integer` | ❌ 否 | `60102626` | 总部kdtid |
| `out_water_no` | `string` | ❌ 否 | `HBYTESTIMPORT0103` | 外部系统储值卡唯一流水号 |
| `card_no` | `string` | ❌ 否 | `1234567891271` | 卡号 |
| `success` | `string` | ❌ 否 | `true` | true |
| `code` | `string` | ❌ 否 | `001` | 180001 |
| `message` | `string` | ❌ 否 | `success` | SUCCESS |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3990

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.2' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "kdt_id": "60102804",
  "root_kdt_id": "60102626",
  "out_uniq_water_no": "HBYTESTIMPORT0103",
  "client_source": "open",
  "user_info": "<user_info>"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardfundchange/1.0.2"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "kdt_id": "60102804",
  "root_kdt_id": "60102626",
  "out_uniq_water_no": "HBYTESTIMPORT0103",
  "client_source": "open",
  "user_info": "<user_info>"
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
| 方法名称 | `syncCardFundChange` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3990)_