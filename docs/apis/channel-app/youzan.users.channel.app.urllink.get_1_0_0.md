---
apiName: "youzan.users.channel.app.urllink.get.1.0.0"
version: "1.0.0"
appName: "channel-app"
apiGroup: "会员与客户"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3614"
---

# youzan.users.channel.app.urllink.get.1.0.0

> **所属分组**: 会员与客户

---

## 1. 场景说明

将微信小程序路径转成适用于微信外网页、短信、邮件可打开的链接（短链），用户点击须跳转H5页面后再次点击才可唤起小程序，而Url Link在IOS系统可减少H5中转步骤。该接口基于店铺后台链接生成工具（微信小程序）功能开放。使用说明见：https://bbs.youzan.com/thread-682718-1-1.html；生成接口限流频率为店铺维度QPS：30;单天生成URL Link数量上限为50万条；

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.users.channel.app.urllink.get/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.users.channel.app.urllink.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.users.channel.app.urllink.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3614)*