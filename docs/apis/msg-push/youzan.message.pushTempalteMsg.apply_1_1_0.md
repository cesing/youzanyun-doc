---
apiName: "youzan.message.pushTempalteMsg.apply.1.1.0"
version: "1.1.0"
appName: "msg-push"
apiGroup: "消息推送"
method: "pushTemplateMsg"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3419"
---

# youzan.message.pushTempalteMsg.apply.1.1.0

> **所属分组**: 消息推送  **所属应用**: msg-push

---

## 1. 场景说明

微信推送模板消息  限定关注公众号的微信粉丝
https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.message.pushTempalteMsg.apply/1.1.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.message.pushTempalteMsg.apply/1.1.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.message.pushTempalteMsg.apply/1.1.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3419)*