---
apiName: "youzan.cardvoucher.datasync.import.cardcreate.1.0.1"
version: "1.0.1"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardDataSyncOpenService"
method: "openCard"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, beauty, retail_head, retail_head_high, edu_head, edu, edu_branch, 1, 1, 1, 1]
deprecated: false
since: "2022-10-28"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3913"
---
# youzan.cardvoucher.datasync.import.cardcreate.1.0.1
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
用于外部储值根据外部卡号，进行开卡
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.1`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（12 个参数）:
```json
{
  "type": "object",
  "properties": {
    "open": {
      "type": "object",
      "description": "request"
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
    "client_source": {
      "type": "string",
      "description": "请求来源业务方标识，必填",
      "example": "clientSource"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用",
      "example": "LnhGm4rh576452722916618240"
    },
    "out_card_no": {
      "type": "string",
      "description": "外部储值卡号，必填",
      "example": "OUT2022111"
    },
    "card_type": {
      "type": "string",
      "description": "储值卡类型，不填默认为余额卡，储值卡类型时extra中的卡模板号templateNo，必填1001余额卡，仅支持余额卡",
      "example": "1001"
    },
    "out_biz_no": {
      "type": "string",
      "description": "外部系统业务单号，非必填说明：可做幂等等逻辑判断",
      "example": "OUTBIZsss222"
    },
    "open_time": {
      "type": "integer",
      "description": "三方卡账单业务发生时间格式：毫秒时间戳",
      "example": "160000000"
    },
    "amount": {
      "type": "integer",
      "description": "开卡总金额，单位：分，非必填",
      "example": "0"
    },
    "bonus_amt": {
      "type": "integer",
      "description": "开卡赠送金额，单位:分，非必填",
      "example": "0"
    },
    "desc": {
      "type": "string",
      "description": "流水描述，非必填",
      "example": "地方的"
    }
  },
  "required": [
    "kdt_id",
    "root_kdt_id",
    "client_source",
    "yz_open_id",
    "out_card_no",
    "card_type"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `open` | `object` | ❌ 否 | `` | request |
| `kdt_id` | `integer` | ✅ 是 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `root_kdt_id` | `integer` | ✅ 是 | `232423` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `client_source` | `string` | ✅ 是 | `clientSource` | 请求来源业务方标识，必填 |
| `yz_open_id` | `integer` | ✅ 是 | `LnhGm4rh576452722916618240` | 有赞用户id，用户在有赞的唯一id。推荐使用 |
| `out_card_no` | `string` | ✅ 是 | `OUT2022111` | 外部储值卡号，必填 |
| `card_type` | `string` | ✅ 是 | `1001` | 储值卡类型，不填默认为余额卡，储值卡类型时extra中的卡模板号templateNo，必填1001余额卡，仅支持余额卡 |
| `out_biz_no` | `string` | ❌ 否 | `OUTBIZsss222` | 外部系统业务单号，非必填说明：可做幂等等逻辑判断 |
| `open_time` | `integer` | ❌ 否 | `160000000` | 三方卡账单业务发生时间格式：毫秒时间戳 |
| `amount` | `integer` | ❌ 否 | `0` | 开卡总金额，单位：分，非必填 |
| `bonus_amt` | `integer` | ❌ 否 | `0` | 开卡赠送金额，单位:分，非必填 |
| `desc` | `string` | ❌ 否 | `地方的` | 流水描述，非必填 |
---
## 3. 响应
**响应参数 Schema**（8 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "返回数据"
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
      "example": "ddd1111"
    },
    "extra": {
      "type": "string",
      "description": "扩展信息",
      "example": "{\"\"}"
    },
    "success": {
      "type": "string",
      "description": "是否成功",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "状态码",
      "example": "0"
    },
    "message": {
      "type": "string",
      "description": "错误信息",
      "example": "error"
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
  "card_no": "ddd1111",
  "extra": "{\"\"}",
  "success": "true",
  "code": "0",
  "message": "error"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 返回数据 |
| `kdt_id` | `integer` | ❌ 否 | `88888` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `root_kdt_id` | `integer` | ❌ 否 | `232423` | 有赞连锁总部店铺id，仅供有赞连锁场景下使用。有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个总部 |
| `card_no` | `string` | ❌ 否 | `ddd1111` | 储值卡号 |
| `extra` | `string` | ❌ 否 | `{""}` | 扩展信息 |
| `success` | `string` | ❌ 否 | `true` | 是否成功 |
| `code` | `string` | ❌ 否 | `0` | 状态码 |
| `message` | `string` | ❌ 否 | `error` | 错误信息 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3913

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.1' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "kdt_id": "88888",
  "root_kdt_id": "232423",
  "client_source": "clientSource",
  "yz_open_id": "LnhGm4rh576452722916618240",
  "out_card_no": "OUT2022111"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.datasync.import.cardcreate/1.0.1"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "kdt_id": "88888",
  "root_kdt_id": "232423",
  "client_source": "clientSource",
  "yz_open_id": "LnhGm4rh576452722916618240",
  "out_card_no": "OUT2022111"
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
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3913)_