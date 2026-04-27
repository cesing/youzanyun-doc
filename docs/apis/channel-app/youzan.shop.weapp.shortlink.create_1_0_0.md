---
apiName: "youzan.shop.weapp.shortlink.create.1.0.0"
version: "1.0.0"
appName: "channel-app"
apiGroup: "店铺信息"
method: "generateShortLink"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4729"
---

# youzan.shop.weapp.shortlink.create.1.0.0

> **所属分组**: 店铺信息  **所属应用**: channel-app

---

## 1. 场景说明

生成微信小程序Short Link
注：
1、目前仅支持电商平台、商家自营、跨境电商任意一种类目，不支持其他类目。
2、单个小程序每日生成 ShortLink 上限为50万个（包含短期有效 ShortLink 与长期有效 ShortLink ）
3、单个小程序总共可生成永久有效 ShortLink 上限为10万个，请谨慎调用。
4、短期有效是30天，微信不支持指定其他过期时间。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.shop.weapp.shortlink.create/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.shop.weapp.shortlink.create/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.shop.weapp.shortlink.create/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4729)*