---
apiName: "youzan.cardvoucher.card.list.commission.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
method: "listValueCardCommissionInfo"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-11-17"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3927"
---
# youzan.cardvoucher.card.list.commission.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz
---
## 1. 场景说明
根据交易单号查询提成信息，如果这个单子没有获得提成的人，则返回空。
下单后非即时返回结果，一般5秒内出结果，建议做个兼容操作，如果未查询到结果，可以1分钟，5分钟，10分钟再进行结果查询。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.list.commission/1.0.0`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "string",
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
  "required": []
}
```
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `request` | `string` | ❌ | `` | 请求参数 |
| `kdt_id` | `integer` | ❌ | `96991937` | 店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺 |
| `out_trade_no` | `string` | ❌ | `RN221110201143000018` | 交易单号充值就是充值单号，购卡就是订单号，退卡就是退卡的业务单号 |
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
      "type": "integer",
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
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 查询返回数据 |
| `accept_kdt_id` | `integer` | ❌ | `101438086` | 受理店铺Id |
| `principal_amount` | `integer` | ❌ | `10000` | 本金变动金额，单位分 |
| `take_commissions_id` | `integer` | ❌ | `0` | 该字段已经废弃，不在透出有效值，切勿使用 |
| `commissions_amount` | `integer` | ❌ | `10000` | 提成金额应退提成金额 |
| `guide_kdt_id` | `integer` | ❌ | `101438086` | 导购所属门店网店id |
| `template_name` | `string` | ❌ | `YZ-测试连锁L版-导购专用余额` | 卡模板名称 |
| `template_no` | `string` | ❌ | `110202622134533` | 卡模版号 |
| `operate_type` | `integer` | ❌ | `0` | 操作类型0：充值1：购卡2：退卡3：充值退款 |
| `yz_open_id` | `integer` | ❌ | `QEcp8wef856822440347590656` | 提成人id对应的yzOpenId |
| `count` | `integer` | ❌ | `2` | 总的记录数 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.card.list.commission/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "kdt_id": "96991937",\n  "out_trade_no": "RN221110201143000018"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.list.commission/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "kdt_id": "96991937",
    "out_trade_no": "RN221110201143000018"
}

resp = requests.post(url, json=payload, headers=headers)
print(resp.json())
```
---
## 5. 错误码
| 错误码 | 类型 | 说明 |
|--------|------|------|
| 10001 | `SYSTEM_ERROR` | 系统内部错误 |
| 10002 | `INVALID_PARAMETER` | 参数错误 |
| 10003 | `UNAUTHORIZED` | 未授权或授权已过期 |
| 10004 | `PERMISSION_DENIED` | 无权限调用此接口 |
| 10005 | `RESOURCE_NOT_FOUND` | 请求的资源不存在 |
| 20001 | `RATE_LIMIT_EXCEEDED` | 调用频率超限 |
| 20002 | `QUOTA_EXCEEDED` | 接口配额已用完 |
---
## 6. 权限与计费

**接口计费状态：未知（请以官网实际披露为准）。**

**拥有此API的能力包：** 暂无数据（请以官网实际披露为准）。

---
## 7. 权限说明

**应用类目 → 权限类型：**

| 应用类目 | 权限类型 |
|----------|----------|
| 有赞微商城、有赞零售、有赞教育、有赞美业 | 普通自研商家（基础权益） |
| 大客户定制接口、美业大客户定制、零售大客户定制、收款二维码-大客专用 | 大客定制接口（需购买大客套餐） |
| 客户关系CRM、门店POS | iPaaS 套餐权益（需购买 iPaaS 套餐） |

> 权限数据来源：[有赞云能力包说明](https://doc.youzanyun.com/detail/content/API/0/120)