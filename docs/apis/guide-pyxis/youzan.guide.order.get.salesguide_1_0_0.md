---
apiName: "youzan.guide.order.get.salesguide.1.0.0"
version: "1.0.0"
appName: "guide-pyxis"
apiGroup: "其它"
method: "getPredictSalesGuide"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4783"
---

# youzan.guide.order.get.salesguide.1.0.0

> **所属分组**: 其它  **所属应用**: guide-pyxis

---

## 1. 场景说明

获取订单预估的销售导购（订单扩展字段上的销售导购），不一定等于最终的归因的销售导购。如需获取准确的销售导购，应监听导购归因完成消息（youzan_guide_OrderAttributeResult）后，调用订单查询接口youzan.trade.get.4.0.2，获取准确的销售导购数据。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.order.get.salesguide/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.order.get.salesguide/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.order.get.salesguide/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4783)*