---
apiName: "youzan.trades.sold.get.4.0.2"
version: "4.0.2"
appName: "trade-open"
apiGroup: "交易订单"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2971"
---

# youzan.trades.sold.get.4.0.2

> **所属分组**: 交易订单

---

## 1. 场景说明

订单搜索接口，升级yz_open_id，该接口目前不支持返回buyer_id。 排序规则基于订单创建时间、更新时间和完成时间 创建时间可以获取指定时间内所有的订单。 更新时间可以获取最新更新订单，但是范围内订单是动态变化的。完成时间可以获取指定时间内完成的订单。  1.只有创建时间start_created和end_created，按创建时间排序 2.只有更新时间start_update和end_update，按更新时间排序 
3.只有完成时间start_success和end_success，按完成时间排序 4.同时存在创建时间、更新时间，按更新时间排序
5.同时存在创建时间、完成时间，按完成时间排序
6.同时存在更新时间、完成时间，按完成时间排序
7.同时存在创建时间、更新时间、完成时间，按完成时间排序
8.如创建或更新或完成时间的开始和结束时间不是成对出现，条件无效
注意：批量接口有一定延时，建议收到交易消息后间隔大于30秒调用接口查询。如果使用批量接口轮询，订单产生到接口查询，建议查询间隔大于30秒，如果返回为空可以重试。
注意：查询2020年以前的订单数据请使用youzan.trades.sold.get.4.0.0接口查询，文档地址：https://doc.youzanyun.com/detail/API/0/157

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.trades.sold.get/4.0.2`

**认证方式**: 凭证式

**请求参数**（0 个）:

```json
{
  "type": "object",
  "properties": {},
  "required": []
}
```

**响应参数**（0 个）:

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

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.trades.sold.get/4.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.trades.sold.get/4.0.2"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2971)*