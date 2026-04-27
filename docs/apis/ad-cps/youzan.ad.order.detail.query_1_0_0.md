---
apiName: "youzan.ad.order.detail.query.1.0.0"
version: "1.0.0"
status: "已上线"
appName: "ad-cps"
apiGroup: "dsp_api"
serviceName: "com.youzan.ad.cps.order.oldapi.OpenOrderDetailService"
method: "getOrderDetail"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2019-11-09"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=714"
---
# youzan.ad.order.detail.query.1.0.0
> **所属分组**: dsp_api　**所属应用**: ad-cps　**状态**: 已上线
---
## 1. 场景说明
查询分佣订单信息（仅支持合作渠道方使用，开发者及商家请勿调用）
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.ad.order.detail.query/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `order_no` | `string` | ❌ 否 | `E20190318135014056100001` | 推广订单号即有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `operator` | `string` | ❌ 否 | `有赞` | 操作者 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 查询订单分佣信息的响应数据 |
| `order_no` | `string` | ❌ 否 | `E20190318135014056100001` | 推广订单号即有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `postage` | `integer` | ❌ 否 | `0` | 运费，单位分 |
| `is_cross_border` | `integer` | ❌ 否 | `1` | 是否是海淘订单，1-是，0-否 |
| `tariff` | `integer` | ❌ 否 | `200` | 订单关税，单位：分 |
| `has_freight_insurance` | `boolean` | ❌ 否 | `false` | 退货是否包运费，true：是，false：否 |
| `buy_way_desc` | `string` | ❌ 否 | `微信支付` | 支付方式，0:默认值,未支付; 1:微信自有支付; 2:支付宝wap; 3:支付宝wap; 5:财付通; 7:代付; 8 |
| `is_commission_order` | `boolean` | ❌ 否 | `true` | 是否是分佣订单 |
| `kdt_id` | `integer` | ❌ 否 | `1234575` | 店铺ID |
| `settle_amount` | `integer` | ❌ 否 | `1000` | 订单分佣成功时的结算金额 单位分 |
| `pay_status` | `integer` | ❌ 否 | `10` | 10:待付款30:已付款40:已发货50:已签收70:维权中80:已退款90:订单关闭 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=714

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.ad.order.detail.query/1.0.0"
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
| 服务名称 | `com.youzan.ad.cps.order.oldapi.OpenOrderDetailService` |
| 方法名称 | `getOrderDetail` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=714)_