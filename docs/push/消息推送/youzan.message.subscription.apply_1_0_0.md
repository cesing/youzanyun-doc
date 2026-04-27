---
apiName: "youzan.message.subscription.apply.1.0.0"
version: "1.0.0"
appName: "msg-push"
apiGroup: "消息推送"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1336"
---

# youzan.message.subscription.apply.1.0.0

> **所属分组**: 消息推送

---

## 1. 场景说明

1、调用该接口前请先查询【youzan.message.subscription.template.get】获取模板。
2、获取下发权限，详见：https://developers.weixin.qq.com/miniprogram/dev/api/open-api/subscribe-message/wx.requestSubscribeMessage.html
3、调用小程序订阅消息推送(仅支持含食品、服装/鞋/箱包类目的小程序), 通过https://developers.weixin.qq.com/miniprogram/dev/framework/open-ability/subscribe-message.html文档了解微信小程序订阅消息的实现流程
4、注意：用户勾选 “总是保持以上选择，不再询问” 之后，下次订阅调用 wx.requestSubscribeMessage 不会弹窗，保持之前的选择，修改选择需要打开小程序设置进行修改。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.message.subscription.apply/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.message.subscription.apply/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.message.subscription.apply/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1336)*