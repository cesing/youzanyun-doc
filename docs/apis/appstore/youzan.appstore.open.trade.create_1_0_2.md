---
apiName: "youzan.appstore.open.trade.create.1.0.2"
version: "1.0.2"
status: "待上线"
appName: "appstore"
apiGroup: "open_market"
serviceName: "com.youzan.cloud.appstore.api.service.open.AppstoreTradeOpenService"
method: "create"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc]
deprecated: false
since: "2019-12-19"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=756"
---
# youzan.appstore.open.trade.create.1.0.2
> **所属分组**: open_market　**所属应用**: appstore　**状态**: 待上线
---
## 1. 场景说明
用于创建应用内购订单
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.trade.create/1.0.2`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（6 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": ""
    },
    "out_item_id": {
      "type": "string",
      "description": "商品外部id",
      "example": "OUT123"
    },
    "app_id": {
      "type": "integer",
      "description": "应用编号",
      "example": "43201"
    },
    "buyer_phone": {
      "type": "string",
      "description": "买家手机号（不推荐使用）",
      "example": "15865656767"
    },
    "num": {
      "type": "integer",
      "description": "订购数量默认1",
      "example": "1"
    },
    "user_id": {
      "type": "integer",
      "description": "有赞用户ID，手机号注册的ID；user_id 和buyer_phone 必须二选一传入",
      "example": "1234123"
    }
  },
  "required": [
    "out_item_id",
    "app_id"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` |  |
| `out_item_id` | `string` | ✅ 是 | `OUT123` | 商品外部id |
| `app_id` | `integer` | ✅ 是 | `43201` | 应用编号 |
| `buyer_phone` | `string` | ❌ 否 | `15865656767` | 买家手机号（不推荐使用） |
| `num` | `integer` | ❌ 否 | `1` | 订购数量默认1 |
| `user_id` | `integer` | ❌ 否 | `1234123` | 有赞用户ID，手机号注册的ID；user_id 和buyer_phone 必须二选一传入 |
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
    "payment_url": {
      "type": "string",
      "description": "有赞应用市场付款地址",
      "example": "https://app.youzanyun.com/transaction/payment?orderNo=E20191219195731028700001"
    },
    "order_no": {
      "type": "string",
      "description": "老订单Id",
      "example": "E20191219195731028700001"
    },
    "goods_name": {
      "type": "string",
      "description": "商品名称",
      "example": "测试内购"
    },
    "shop_name_group": {
      "type": "string",
      "description": "授权的店铺名称",
      "example": "测试店铺"
    },
    "pay_amount": {
      "type": "integer",
      "description": "支付金额，单位（分）",
      "example": "1000"
    },
    "cashier_url": {
      "type": "string",
      "description": "有赞H5收银台地址",
      "example": "https://cashier.youzan.com/pay/preorder?prepay_id=PT1653349182078976&cashier_sign=B9ECC1CDD0C6D506DB85D49B12FD3415&cashier_salt=1576756651843&partner_id=820000000003"
    },
    "seller_name": {
      "type": "string",
      "description": "卖家名称",
      "example": "有赞云店铺"
    },
    "sku_info": {
      "type": "string",
      "description": "sku套餐信息ex：基础版（三个月）"
    },
    "use_app_url": {
      "type": "string",
      "description": "授权成功时有应用使用地址"
    },
    "order_status_enum": {
      "type": "string",
      "description": "枚举类型：订单状态",
      "example": "WAIT_PAY"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "payment_url": "https://app.youzanyun.com/transaction/payment?orderNo=E20191219195731028700001",
  "order_no": "E20191219195731028700001",
  "goods_name": "测试内购",
  "shop_name_group": "测试店铺",
  "pay_amount": "1000",
  "cashier_url": "https://cashier.youzan.com/pay/preorder?prepay_id=PT1653349182078976&cashier_sign=B9ECC1CDD0C6D506DB85D49B12FD3415&cashier_salt=1576756651843&partner_id=820000000003",
  "seller_name": "有赞云店铺"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` |  |
| `payment_url` | `string` | ❌ 否 | `https://app.youzanyun.com/tran` | 有赞应用市场付款地址 |
| `order_no` | `string` | ❌ 否 | `E20191219195731028700001` | 老订单Id |
| `goods_name` | `string` | ❌ 否 | `测试内购` | 商品名称 |
| `shop_name_group` | `string` | ❌ 否 | `测试店铺` | 授权的店铺名称 |
| `pay_amount` | `integer` | ❌ 否 | `1000` | 支付金额，单位（分） |
| `cashier_url` | `string` | ❌ 否 | `https://cashier.youzan.com/pay` | 有赞H5收银台地址 |
| `seller_name` | `string` | ❌ 否 | `有赞云店铺` | 卖家名称 |
| `sku_info` | `string` | ❌ 否 | `` | sku套餐信息ex：基础版（三个月） |
| `use_app_url` | `string` | ❌ 否 | `` | 授权成功时有应用使用地址 |
| `order_status_enum` | `string` | ❌ 否 | `WAIT_PAY` | 枚举类型：订单状态 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=756

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.2' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "out_item_id": "OUT123",
  "app_id": "43201"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.trade.create/1.0.2"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "out_item_id": "OUT123",
  "app_id": "43201"
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
| 服务名称 | `com.youzan.cloud.appstore.api.service.open.AppstoreTradeOpenService` |
| 方法名称 | `create` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=756)_