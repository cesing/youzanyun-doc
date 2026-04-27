---
apiName: "youzan.users.weapp.urllink.redirect.create.1.0.0"
version: "1.0.0"
appName: "channel-app"
apiGroup: "会员与客户"
method: "generateUrlLinkRedirectUrl"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3711"
---

# youzan.users.weapp.urllink.redirect.create.1.0.0

> **所属分组**: 会员与客户  **所属应用**: channel-app

---

## 1. 场景说明

1、有赞短链和长链是url link的中间链接，两者都能打开对应的小程序页面，建议使用短链
2、三种链接的逻辑，目前是先生成url link的中间链接有赞短链和长链；有赞短链，最后经过有赞的短链技术也是会到长链的，长链的页面是个中间页，在该中间页中会利用长链携带的code去调用后端服务换取url link并利用url link打开对应的小程序页面

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.users.weapp.urllink.redirect.create/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.users.weapp.urllink.redirect.create/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.users.weapp.urllink.redirect.create/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3711)*