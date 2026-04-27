---
apiName: "youzan.message.wechatSubNotice.get.templateId.1.0.0"
version: "1.0.0"
appName: "msg-push"
apiGroup: "消息推送"
method: "getWechatSubNoticeTemplateList"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2945"
---

# youzan.message.wechatSubNotice.get.templateId.1.0.0

> **所属分组**: 消息推送  **所属应用**: msg-push

---

## 1. 场景说明

微信页面获取订阅模板列表  订阅通知 要求公众号 是认证服务号 且 类目为 商家自营-食品、商家自营-服饰/鞋/箱包 https://help.youzan.com/displaylist/detail_4_4-2-57397
仅限公众号使用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.message.wechatSubNotice.get.templateId/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.message.wechatSubNotice.get.templateId/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.message.wechatSubNotice.get.templateId/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2945)*