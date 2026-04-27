---
apiName: "youzan.edu.owl.live.edu.callback.playback.1.0.0"
version: "1.0.0"
appName: "ebiz-owl"
apiGroup: "消息推送"
method: "playBackCallBack"
timeout: 5000
authType: "无认证"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/843"
---

# youzan.edu.owl.live.edu.callback.playback.1.0.0

> **所属分组**: 消息推送  **所属应用**: ebiz-owl

---

## 1. 场景说明

教育直播（保利威）转存回调接口（仅支持保利威使用，开发者及商家请勿调用）

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.edu.owl.live.edu.callback.playback/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.edu.owl.live.edu.callback.playback/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.edu.owl.live.edu.callback.playback/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/843)*