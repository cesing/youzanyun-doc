---
apiName: "youzan.ad.order.detail.query.1.0.0"
version: "1.0.0"
appName: "ad-cps"
apiGroup: "dsp_api"
method: "getOrderDetail"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2019-11-09"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/714"
---
# youzan.ad.order.detail.query.1.0.0
> **所属分组**: dsp_api　**所属应用**: ad-cps
---
## 1. 场景说明
查询分佣订单信息（仅支持合作渠道方使用，开发者及商家请勿调用）
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.ad.order.detail.query/1.0.0`
**请求参数 Schema**（2 个参数）:
```json
{
  "type": "object",
  "properties": {
    "order_no": {
      "type": "string",
      "description": "推广订单号即有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E20190318135014056100001"
    },
    "operator": {
      "type": "string",
      "description": "操作者",
      "example": "有赞"
    }
  },
  "required": []
}
```
**请求参数明细**（2 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `order_no` | `string` | ❌ | `E20190318135014056100001` | 推广订单号即有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `operator` | `string` | ❌ | `有赞` | 操作者 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "查询订单分佣信息的响应数据"
    },
    "order_no": {
      "type": "string",
      "description": "推广订单号即有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E20190318135014056100001"
    },
    "postage": {
      "type": "integer",
      "description": "运费，单位分",
      "example": "0"
    },
    "is_cross_border": {
      "type": "integer",
      "description": "是否是海淘订单，1-是，0-否",
      "example": "1"
    },
    "tariff": {
      "type": "integer",
      "description": "订单关税，单位：分",
      "example": "200"
    },
    "has_freight_insurance": {
      "type": "boolean",
      "description": "退货是否包运费，true：是，false：否",
      "example": "false"
    },
    "buy_way_desc": {
      "type": "string",
      "description": "支付方式，0:默认值,未支付; 1:微信自有支付; 2:支付宝wap; 3:支付宝wap; 5:财付通; 7:代付; 8:联动优势; 9:货到付款; 10:大账号代销; 11:受理模式; 12:百付宝; 13:sdk支付; 14:合并付货款; 15:赠品; 16:优惠兑换; 17:自动付货款; 18:爱学贷; 19:微信wap; 20:微信红包支付; 21:返利; 22:ump红包; 24:易宝支付; 25:储值卡; 27:qq支付; 28:有赞E卡支付; 29:微信条码; 30:支付宝条码; 33:礼品卡支付; 35:储值卡（会员余额）; 37:银行卡支付;72:微信扫码二维码支付; 100:代收账户; 300:储值账户; 400:保证金账户; 101:收款码; 102:微信; 103:支付宝; 104:刷卡; 105:二维码台卡; 106:储值卡（线下场景使用）; 107:有赞E卡; 110:标记收款-自有微信支付; 111:标记收款-自有支付宝; 112:标记收款-自有POS刷卡; 113:通联刷卡支付; 115:有赞零钱; 200:记账账户; 201:现金;202:组合支付",
      "example": "微信支付"
    },
    "is_commission_order": {
      "type": "boolean",
      "description": "是否是分佣订单",
      "example": "true"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺ID",
      "example": "1234575"
    },
    "settle_amount": {
      "type": "integer",
      "description": "订单分佣成功时的结算金额 单位分",
      "example": "1000"
    },
    "pay_status": {
      "type": "integer",
      "description": "10:待付款30:已付款40:已发货50:已签收70:维权中80:已退款90:订单关闭",
      "example": "10"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "order_no": "E20190318135014056100001",
  "postage": "0",
  "is_cross_border": "1",
  "tariff": "200",
  "has_freight_insurance": "false",
  "buy_way_desc": "微信支付",
  "is_commission_order": "true"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 查询订单分佣信息的响应数据 |
| `order_no` | `string` | ❌ | `E20190318135014056100001` | 推广订单号即有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `postage` | `integer` | ❌ | `0` | 运费，单位分 |
| `is_cross_border` | `integer` | ❌ | `1` | 是否是海淘订单，1-是，0-否 |
| `tariff` | `integer` | ❌ | `200` | 订单关税，单位：分 |
| `has_freight_insurance` | `boolean` | ❌ | `false` | 退货是否包运费，true：是，false：否 |
| `buy_way_desc` | `string` | ❌ | `微信支付` | 支付方式，0:默认值,未支付; 1:微信自有支付; 2:支付宝wap; 3:支付宝wap; 5:财付通; 7:代付; 8:联动优势; 9:货到付款; 10:大账 |
| `is_commission_order` | `boolean` | ❌ | `true` | 是否是分佣订单 |
| `kdt_id` | `integer` | ❌ | `1234575` | 店铺ID |
| `settle_amount` | `integer` | ❌ | `1000` | 订单分佣成功时的结算金额 单位分 |
| `pay_status` | `integer` | ❌ | `10` | 10:待付款30:已付款40:已发货50:已签收70:维权中80:已退款90:订单关闭 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.ad.order.detail.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "order_no": "E20190318135014056100001",\n  "operator": "有赞"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.ad.order.detail.query/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "order_no": "E20190318135014056100001",
    "operator": "有赞"
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