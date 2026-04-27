---
apiName: "youzan.message.pushFansMsg.apply.1.0.0"
version: "1.0.0"
appName: "msg-push"
apiGroup: "消息推送"
method: "pushFansMsg"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2946"
---

# youzan.message.pushFansMsg.apply.1.0.0

> **所属分组**: 消息推送  **所属应用**: msg-push

---

## 1. 场景说明

推送微信粉丝消息，每次最多50人， 限定关注公众号的微信粉丝。推送成功关注的粉丝在公众号对话解密可以看到推送的信息。
微信规则如下：
https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Service_Center_messages.html

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.message.pushFansMsg.apply/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.message.pushFansMsg.apply/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.message.pushFansMsg.apply/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2946)*