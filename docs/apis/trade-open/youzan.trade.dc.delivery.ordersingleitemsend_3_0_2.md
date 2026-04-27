---
apiName: "youzan.trade.dc.delivery.ordersingleitemsend.3.0.2"
version: "3.0.2"
appName: "trade-open"
apiGroup: "trade-delivery"
method: "orderSingleItemSend"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-06-08"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2930"
---
# youzan.trade.dc.delivery.ordersingleitemsend.3.0.2
> **所属分组**: trade-delivery　**所属应用**: trade-open
---
## 1. 场景说明
用于一笔订单一种商品有多个数量进行拆单发货，支持选择多家物流发货。即一笔订单中，同种商品有多个时，必须一次性全部发货，不可以分多次发货，使用（num）数量参数控制一笔订单是否全部发货。支持随心订订单单商品多运单发货，单商品发货数量需要等于单期发货数量。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.trade.dc.delivery.ordersingleitemsend/3.0.2`
**请求参数 Schema**（0 个参数）:
```json
{
  "type": "object",
  "properties": {},
  "required": []
}
```
**请求参数明细**：暂无数据

---
## 3. 响应
**响应参数 Schema**（0 个字段）:
```json
{
  "type": "object",
  "properties": {}
}
```
**成功响应示例**:
```json
{}
```
**响应参数明细**：暂无数据

---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.trade.dc.delivery.ordersingleitemsend/3.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.trade.dc.delivery.ordersingleitemsend/3.0.2"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {}

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