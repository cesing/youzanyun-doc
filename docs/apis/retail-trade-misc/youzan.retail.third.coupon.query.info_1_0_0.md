---
apiName: "youzan.retail.third.coupon.query.info.1.0.0"
version: "1.0.0"
appName: "retail-trade-misc"
apiGroup: "零售门店"
method: "queryCouponInfo"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3991"
---

# youzan.retail.third.coupon.query.info.1.0.0

> **所属分组**: 零售门店  **所属应用**: retail-trade-misc

---

## 1. 场景说明

通过youzan.trade.get.4.0.2查询为使用了外部卡券的订单可以通过本接口。
查询订单核销的外部券卡券 核销渠道、卡券项目、卡券类型、券码、券码状态。
卡券核销是异步进行的，订单创建后立刻查询会出现卡券还未核销完成，可使用订单查询的coupon_num来做重试。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.retail.third.coupon.query.info/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.retail.third.coupon.query.info/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.retail.third.coupon.query.info/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3991)*