---
apiName: "youzan.salesman.shoppingguide.query.1.0.0"
version: "1.0.0"
appName: "ebiz-salesman"
apiGroup: "其它"
method: "getShoppingGuide"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2892"
---

# youzan.salesman.shoppingguide.query.1.0.0

> **所属分组**: 其它  **所属应用**: ebiz-salesman

---

## 1. 场景说明

根据用户id查询店铺导购员详情-仅限伯俊使用。需要店铺购买导购插件（需要升级到新版的销售员插件能力，详情见：https://help.youzan.com/displaylist/detail_4_4-2-57122?page=1）

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.salesman.shoppingguide.query/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.salesman.shoppingguide.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.salesman.shoppingguide.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2892)*