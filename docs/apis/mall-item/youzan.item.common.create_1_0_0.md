---
apiName: "youzan.item.common.create.1.0.0"
version: "1.0.0"
appName: "mall-item"
apiGroup: "商品与库存"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4653"
---

# youzan.item.common.create.1.0.0

> **所属分组**: 商品与库存

---

## 1. 场景说明

创建商品，支持创建实物、虚拟、电子卡券、蛋糕烘焙、海淘这五种商品。配合【youzan.item.itemdetail.get.1.0.0】查询商品详情，【youzan.item.item.update.1.0.0】更新商品，【youzan.item.channel.publish.2.0.0】发布商品到指定渠道（新商品模型的零售单店或者连锁店铺需要）

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.common.create/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.item.common.create/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.common.create/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4653)*