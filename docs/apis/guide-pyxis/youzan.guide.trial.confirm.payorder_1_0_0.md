---
apiName: "youzan.guide.trial.confirm.payorder.1.0.0"
version: "1.0.0"
appName: "guide-pyxis"
apiGroup: "其它"
method: "confirmOrder"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4822"
---

# youzan.guide.trial.confirm.payorder.1.0.0

> **所属分组**: 其它  **所属应用**: guide-pyxis

---

## 1. 场景说明

导购分享先试后付确认下单链接，消费者打开会调用本API，获取下单数据并写入订单缓存，操作成功后，路由到下单页(name=trade-buy)，引导消费者下单支付。

本接口内部通过调用com.youzan.cloud.extension.api.guide.TrialOrderGetExtPoint扩展点来获取下单数据（例如购买的商品、客户收货地址等），若未实现扩展点，则本接口会执行失败。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.trial.confirm.payorder/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.trial.confirm.payorder/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.trial.confirm.payorder/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4822)*