---
apiName: "youzan.message.pushSubNoticeMsg.apply.1.0.0"
version: "1.0.0"
appName: "msg-push"
apiGroup: "消息推送"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2948"
---

# youzan.message.pushSubNoticeMsg.apply.1.0.0

> **所属分组**: 消息推送

---

## 1. 场景说明

推送订阅通知消息 限定最大50人
限定条件为需要订阅过对应模板的粉丝 
如果没有订阅, 失败结果信息详见 youzan_message_YzCloudOpenPushResult 推送通知

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.message.pushSubNoticeMsg.apply/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.message.pushSubNoticeMsg.apply/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.message.pushSubNoticeMsg.apply/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2948)*