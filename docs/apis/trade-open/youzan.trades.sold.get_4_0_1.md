---
apiName: "youzan.trades.sold.get.4.0.1"
version: "4.0.1"
appName: "trade-open"
apiGroup: "trade"
method: "queryNewTradeList"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2019-03-06"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/638"
---
# youzan.trades.sold.get.4.0.1
> **所属分组**: trade　**所属应用**: trade-open
---
## 1. 场景说明
订单搜索接口，升级yz_open_id，该接口目前不支持返回buyer_id。 排序规则基于订单创建时间、更新时间和完成时间 创建时间可以获取指定时间内所有的订单。 更新时间可以获取最新更新订单，但是范围内订单是动态变化的。完成时间可以获取指定时间内完成的订单。  1.只有创建时间start_created和end_created，按创建时间排序 2.只有更新时间start_update和end_update，按更新时间排序 
3.只有完成时间start_success和end_success，按完成时间排序 4.同时存在创建时间、更新时间，按更新时间排序
5.同时存在创建时间、完成时间，按完成时间排序
6.同时存在更新时间、完成时间，按完成时间排序
7.同时存在创建时间、更新时间、完成时间，按完成时间排序
8.如创建或更新或完成时间的开始和结束时间不是成对出现，条件无效
9.注意：查询2020年以前的订单数据请使用youzan.trades.sold.get.4.0.0接口查询，文档地址：https://doc.youzanyun.com/detail/API/0/157
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.trades.sold.get/4.0.1`
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
curl -X POST 'https://open.youzanyun.com/api/youzan.trades.sold.get/4.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.trades.sold.get/4.0.1"
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