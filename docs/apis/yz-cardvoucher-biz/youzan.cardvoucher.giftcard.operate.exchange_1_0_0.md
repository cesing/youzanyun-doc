---
apiName: "youzan.cardvoucher.giftcard.operate.exchange.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.open.GiftCardOpenService"
method: "exchangeCard"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, retail_d_partner, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offline, retail_offline_channel, retail_partner, edu, edu_head, edu_branch, 1]
deprecated: false
since: "2023-04-07"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=4029"
---
# youzan.cardvoucher.giftcard.operate.exchange.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
礼品卡兑换：支持卡密兑换和扫码兑换，仅进行兑换，不会自动触发激活。可通过商家后台批量制卡后生成的兑换信息进行调用，支持电子卡和实体卡兑换。
备注：如扩展点兑换流程中衔接本接口，返回的电子卡号不可直接作为用户的卡号返回，否则选择此卡号支付时会走到标品，可通过自定义卡号映射或加固定前/后缀解决，非扩展点流程对接无需关注本备注。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.operate.exchange/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（5 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "integer",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】",
      "example": "MVJ5w0uy585097513770430464"
    },
    "card_no_or_serial_num": {
      "type": "string",
      "description": "卡密兑换时必填：可填批量制卡后的电子卡的序列号或实体卡的卡号进行兑换序列号",
      "example": "aaaaaaa"
    },
    "check_code": {
      "type": "string",
      "description": "卡密兑换时必填：兑换码",
      "example": "1111111"
    },
    "card_random": {
      "type": "string",
      "description": "扫码兑换时必填：卡号随机数"
    },
    "exchange_type": {
      "type": "integer",
      "description": "兑换类型：0(卡密兑换) 1(扫码兑换)",
      "example": "0"
    }
  },
  "required": [
    "yz_open_id",
    "card_no_or_serial_num",
    "exchange_type"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `yz_open_id` | `integer` | ✅ 是 | `MVJ5w0uy585097513770430464` | 有赞用户id，用户在有赞的唯一id。推荐使用【可通过youzan.user.openid.get接口获取】 |
| `card_no_or_serial_num` | `string` | ✅ 是 | `aaaaaaa` | 卡密兑换时必填：可填批量制卡后的电子卡的序列号或实体卡的卡号进行兑换序列号 |
| `check_code` | `string` | ❌ 否 | `1111111` | 卡密兑换时必填：兑换码 |
| `card_random` | `string` | ❌ 否 | `` | 扫码兑换时必填：卡号随机数 |
| `exchange_type` | `integer` | ✅ 是 | `0` | 兑换类型：0(卡密兑换) 1(扫码兑换) |
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
    "card_no": {
      "type": "string",
      "description": "电子卡卡号",
      "example": "1234567890"
    },
    "exchange_status": {
      "type": "integer",
      "description": "兑换状态：2(兑换成功，且是首次被兑换成功) 3(卡已经被兑换过，且是当前用户兑换的) 4(卡已经被兑换过，且是被他人兑换的) 5(卡已被失效，无法兑换)",
      "example": "2"
    },
    "exchange_date": {
      "type": "string",
      "description": "兑换时间-毫秒级时间戳",
      "example": "1680863031000"
    },
    "template_no": {
      "type": "string",
      "description": "卡模板号",
      "example": "1234567899"
    },
    "template_name": {
      "type": "string",
      "description": "卡模板名称",
      "example": "测试卡模板"
    },
    "denomination": {
      "type": "integer",
      "description": "卡面额-分",
      "example": "100"
    },
    "principal": {
      "type": "integer",
      "description": "卡内本金-分",
      "example": "60"
    },
    "bonus": {
      "type": "integer",
      "description": "卡内赠送金-分",
      "example": "40"
    },
    "expired_date": {
      "type": "string",
      "description": "批量制卡时卡的有效期截止日期-毫秒时间戳",
      "example": "1680863031"
    },
    "support_give": {
      "type": "boolean",
      "description": "卡模板配置的礼品卡是否支持赠送：true支持，false不支持",
      "example": "true"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "card_no": "1234567890",
  "exchange_status": "2",
  "exchange_date": "1680863031000",
  "template_no": "1234567899",
  "template_name": "测试卡模板",
  "denomination": "100",
  "principal": "60"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `card_no` | `string` | ❌ 否 | `1234567890` | 电子卡卡号 |
| `exchange_status` | `integer` | ❌ 否 | `2` | 兑换状态：2(兑换成功，且是首次被兑换成功) 3(卡已经被兑换过，且是当前用户兑换的) 4(卡已经被兑换过，且是被他人兑 |
| `exchange_date` | `string` | ❌ 否 | `1680863031000` | 兑换时间-毫秒级时间戳 |
| `template_no` | `string` | ❌ 否 | `1234567899` | 卡模板号 |
| `template_name` | `string` | ❌ 否 | `测试卡模板` | 卡模板名称 |
| `denomination` | `integer` | ❌ 否 | `100` | 卡面额-分 |
| `principal` | `integer` | ❌ 否 | `60` | 卡内本金-分 |
| `bonus` | `integer` | ❌ 否 | `40` | 卡内赠送金-分 |
| `expired_date` | `string` | ❌ 否 | `1680863031` | 批量制卡时卡的有效期截止日期-毫秒时间戳 |
| `support_give` | `boolean` | ❌ 否 | `true` | 卡模板配置的礼品卡是否支持赠送：true支持，false不支持 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=4029

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "yz_open_id": "MVJ5w0uy585097513770430464",
  "card_no_or_serial_num": "aaaaaaa",
  "exchange_type": "0"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.operate.exchange/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "yz_open_id": "MVJ5w0uy585097513770430464",
  "card_no_or_serial_num": "aaaaaaa",
  "exchange_type": "0"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.open.GiftCardOpenService` |
| 方法名称 | `exchangeCard` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=4029)_