---
apiName: "youzan.cardvoucher.card.list.commission.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.open.CardCommissionOpenService"
method: "listValueCardCommissionInfo"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, retail_head, retail_head_high, retail_online, retail_offline_channel, retail_offline, 1, 1, 1]
deprecated: false
since: "2022-11-17"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3927"
---
# youzan.cardvoucher.card.list.commission.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
根据交易单号查询提成信息，如果这个单子没有获得提成的人，则返回空。
下单后非即时返回结果，一般5秒内出结果，建议做个兼容操作，如果未查询到结果，可以1分钟，5分钟，10分钟再进行结果查询。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.list.commission/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": "请求参数"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "96991937"
    },
    "out_trade_no": {
      "type": "string",
      "description": "交易单号充值就是充值单号，购卡就是订单号，退卡就是退卡的业务单号",
      "example": "RN221110201143000018"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` | 请求参数 |
| `kdt_id` | `integer` | ❌ 否 | `96991937` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `out_trade_no` | `string` | ❌ 否 | `RN221110201143000018` | 交易单号充值就是充值单号，购卡就是订单号，退卡就是退卡的业务单号 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "查询返回数据"
    },
    "accept_kdt_id": {
      "type": "integer",
      "description": "受理店铺Id",
      "example": "101438086"
    },
    "principal_amount": {
      "type": "integer",
      "description": "本金变动金额，单位分",
      "example": "10000"
    },
    "take_commissions_id": {
      "type": "integer",
      "description": "该字段已经废弃，不在透出有效值，切勿使用",
      "example": "0"
    },
    "commissions_amount": {
      "type": "integer",
      "description": "提成金额应退提成金额",
      "example": "10000"
    },
    "guide_kdt_id": {
      "type": "integer",
      "description": "导购所属门店网店id",
      "example": "101438086"
    },
    "template_name": {
      "type": "string",
      "description": "卡模板名称",
      "example": "YZ-测试连锁L版-导购专用余额"
    },
    "template_no": {
      "type": "string",
      "description": "卡模版号",
      "example": "110202622134533"
    },
    "operate_type": {
      "type": "integer",
      "description": "操作类型0：充值1：购卡2：退卡3：充值退款",
      "example": "0"
    },
    "yz_open_id": {
      "type": "integer",
      "description": "提成人id对应的yzOpenId",
      "example": "QEcp8wef856822440347590656"
    },
    "count": {
      "type": "string",
      "description": "总的记录数",
      "example": "2"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "accept_kdt_id": "101438086",
  "principal_amount": "10000",
  "take_commissions_id": "0",
  "commissions_amount": "10000",
  "guide_kdt_id": "101438086",
  "template_name": "YZ-测试连锁L版-导购专用余额",
  "template_no": "110202622134533"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` | 查询返回数据 |
| `accept_kdt_id` | `integer` | ❌ 否 | `101438086` | 受理店铺Id |
| `principal_amount` | `integer` | ❌ 否 | `10000` | 本金变动金额，单位分 |
| `take_commissions_id` | `integer` | ❌ 否 | `0` | 该字段已经废弃，不在透出有效值，切勿使用 |
| `commissions_amount` | `integer` | ❌ 否 | `10000` | 提成金额应退提成金额 |
| `guide_kdt_id` | `integer` | ❌ 否 | `101438086` | 导购所属门店网店id |
| `template_name` | `string` | ❌ 否 | `YZ-测试连锁L版-导购专用余额` | 卡模板名称 |
| `template_no` | `string` | ❌ 否 | `110202622134533` | 卡模版号 |
| `operate_type` | `integer` | ❌ 否 | `0` | 操作类型0：充值1：购卡2：退卡3：充值退款 |
| `yz_open_id` | `integer` | ❌ 否 | `QEcp8wef856822440347590656` | 提成人id对应的yzOpenId |
| `count` | `string` | ❌ 否 | `2` | 总的记录数 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3927

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.list.commission/1.0.0"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.open.CardCommissionOpenService` |
| 方法名称 | `listValueCardCommissionInfo` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3927)_