---
apiName: "youzan.cardvoucher.datasync.import.cardcreate.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardDataSyncOpenService"
method: "openCard"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, retail_head, edu, retail_head_high, edu_head, edu_branch, retail_online, retail_online_lite, retail_offline]
deprecated: false
since: "2022-10-27"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3908"
---
# youzan.cardvoucher.datasync.import.cardcreate.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
供储值卡外部开卡
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（12 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": "入参request"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "60102804"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "60102626"
    },
    "out_uniq_water_no": {
      "type": "string",
      "description": "外部系统储值卡流水号，必填说明：储值卡流水的唯一标识",
      "example": "HBYTESTIMPORT0103"
    },
    "client_source": {
      "type": "string",
      "description": "请求来源业务方标识，必填",
      "example": "open"
    },
    "user_info": {
      "type": "object",
      "description": "用户信息，必填"
    },
    "mobile_no": {
      "type": "string",
      "description": "手机号",
      "example": "13186972611"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id因开放网关审核要求，必须命名为yzOpenUid，但实际赋值为yzUid",
      "example": "7j3Gi1UH732330877366837248"
    },
    "user_name": {
      "type": "string",
      "description": "用户姓名",
      "example": "木七"
    },
    "user_nick_name": {
      "type": "string",
      "description": "用户昵称",
      "example": "木七"
    },
    "card_no": {
      "type": "string",
      "description": "储值卡号，必填",
      "example": "1234567891271"
    },
    "card_type": {
      "type": "string",
      "description": "储值卡类型，不填默认为余额卡，储值卡类型时extra中的卡模板号templateNo必填1001余额卡1002储值卡",
      "example": "1001"
    }
  },
  "required": [
    "request",
    "kdt_id",
    "root_kdt_id",
    "out_uniq_water_no",
    "client_source",
    "user_info",
    "mobile_no",
    "yz_open_id",
    "user_name",
    "user_nick_name",
    "card_no",
    "card_type"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ✅ 是 | `` | 入参request |
| `kdt_id` | `integer` | ✅ 是 | `60102804` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `root_kdt_id` | `integer` | ✅ 是 | `60102626` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `out_uniq_water_no` | `string` | ✅ 是 | `HBYTESTIMPORT0103` | 外部系统储值卡流水号，必填说明：储值卡流水的唯一标识 |
| `client_source` | `string` | ✅ 是 | `open` | 请求来源业务方标识，必填 |
| `user_info` | `object` | ✅ 是 | `` | 用户信息，必填 |
| `mobile_no` | `string` | ✅ 是 | `13186972611` | 手机号 |
| `yz_open_id` | `integer` | ✅ 是 | `7j3Gi1UH732330877366837248` | 有赞用户id因开放网关审核要求，必须命名为yzOpenUid，但实际赋值为yzUid |
| `user_name` | `string` | ✅ 是 | `木七` | 用户姓名 |
| `user_nick_name` | `string` | ✅ 是 | `木七` | 用户昵称 |
| `card_no` | `string` | ✅ 是 | `1234567891271` | 储值卡号，必填 |
| `card_type` | `string` | ✅ 是 | `1001` | 储值卡类型，不填默认为余额卡，储值卡类型时extra中的卡模板号templateNo必填1001余额卡1002储值卡 |
---
## 3. 响应
**响应参数 Schema**（8 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "返回信息"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "root_kdt_id": {
      "type": "integer",
      "description": "有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部",
      "example": "232423"
    },
    "card_no": {
      "type": "string",
      "description": "储值卡号",
      "example": "ddddd"
    },
    "extra": {
      "type": "string",
      "description": "扩展信息",
      "example": "{\"\":\"\"}"
    },
    "success": {
      "type": "string",
      "description": "是否成功",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "错误码",
      "example": "1"
    },
    "message": {
      "type": "string",
      "description": "错误信息",
      "example": "sss"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "kdt_id": "88888",
  "root_kdt_id": "232423",
  "card_no": "ddddd",
  "extra": "{\"\":\"\"}",
  "success": "true",
  "code": "1",
  "message": "sss"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 返回信息 |
| `kdt_id` | `integer` | ❌ 否 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `root_kdt_id` | `integer` | ❌ 否 | `232423` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `card_no` | `string` | ❌ 否 | `ddddd` | 储值卡号 |
| `extra` | `string` | ❌ 否 | `{"":""}` | 扩展信息 |
| `success` | `string` | ❌ 否 | `true` | 是否成功 |
| `code` | `string` | ❌ 否 | `1` | 错误码 |
| `message` | `string` | ❌ 否 | `sss` | 错误信息 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3908

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "request": "<request>",
  "kdt_id": "60102804",
  "root_kdt_id": "60102626",
  "out_uniq_water_no": "HBYTESTIMPORT0103",
  "client_source": "open"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "request": "<request>",
  "kdt_id": "60102804",
  "root_kdt_id": "60102626",
  "out_uniq_water_no": "HBYTESTIMPORT0103",
  "client_source": "open"
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
| 方法名称 | `openCard` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3908)_