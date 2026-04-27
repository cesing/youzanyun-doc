---
apiName: "youzan.users.weapp.shortlink.create.1.0.0"
version: "1.0.0"
appName: "channel-app"
apiGroup: "会员与客户"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3712"
---

# youzan.users.weapp.shortlink.create.1.0.0

> **所属分组**: 会员与客户

---

## 1. 场景说明

1、生成short link的时候，是有要求的，要类目为电商平台、商家自营、跨境电商
2、在类目不符合的时候即无法生成short link的时候，会降级获取有赞短链，降级获取的有赞短链，默认30天有效
3、有赞短链也是可以打开的，但是相对short link，打开的速度慢一些，链路长一些
4、short link是只能在微信内打开唤起小程序，而有赞短链在微信内外都可以打开
5、单个小程序每日生成 ShortLink 上限为50万个（包含短期有效 ShortLink 与长期有效 ShortLink ）
 6、单个小程序总共可生成永久有效 ShortLink 上限为10万个，请谨慎调用。
 7、短期有效ShortLink 有效时间为30天，单个小程序生成短期有效ShortLink 不设上限。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.users.weapp.shortlink.create/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.users.weapp.shortlink.create/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.users.weapp.shortlink.create/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3712)*