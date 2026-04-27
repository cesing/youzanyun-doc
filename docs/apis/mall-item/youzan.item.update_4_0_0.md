---
apiName: "youzan.item.update.4.0.0"
version: "4.0.0"
appName: "mall-item"
apiGroup: "大客CRM"
method: "updateItem"
timeout: 10000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1445"
---

# youzan.item.update.4.0.0

> **所属分组**: 大客CRM  **所属应用**: mall-item

---

## 1. 场景说明

更新单个商品信息接口全量更新，例：一个商品有分享描述信息，调用接口为信息不传分享描述字段信息，接口执行成功，商品分享描述信息为空，其他字段规则如上示例。请确认接口规则后再进行接口调用。支持微商城单店、微商城连锁总部、微商城连锁分店、零售高级版总部更新商品。目前仅支持实物商品、虚拟商品、电子卡券、茶饮烘焙类型。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.update/4.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.item.update/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.update/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1445)*