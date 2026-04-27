---
apiName: "youzan.fenxiao.item.detail.get.1.0.0"
version: "1.0.0"
appName: "fx-goods"
apiGroup: "分销与供货"
method: "getItemDetail"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/473"
---

# youzan.fenxiao.item.detail.get.1.0.0

> **所属分组**: 分销与供货  **所属应用**: fx-goods

---

## 1. 场景说明

用于分销商获取分销商品详情，并支持海淘分销商品查询。注意该场景，此时查询商品同时会更新商品：如果供货商更新A商品价格，分销商店铺中的商品A会直接变为售罄（买家无法购买），如果分销商使用该接口查询商品A，这个时候商品A价格会更新为供货商分销默认价（有库存买家可以下单）。如果不想跟着供货商的价格更新商品A可以使用【youzan.item.get.3.0.0】查询。注意：仅支持已上架商品

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.fenxiao.item.detail.get/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.fenxiao.item.detail.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.fenxiao.item.detail.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/473)*