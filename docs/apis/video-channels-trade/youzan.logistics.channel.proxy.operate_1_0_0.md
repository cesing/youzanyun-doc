---
apiName: "youzan.logistics.channel.proxy.operate.1.0.0"
version: "1.0.0"
appName: "video-channels-trade"
apiGroup: "物流配送"
method: "callApi"
timeout: 10000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4218"
---

# youzan.logistics.channel.proxy.operate.1.0.0

> **所属分组**: 物流配送  **所属应用**: video-channels-trade

---

## 1. 场景说明

针对部分特殊的业务场景需求，通过代理的方式调用外部渠道接口；当前仅支持视频号小店电子面单相关接口，接口出参和入参请参考微信视频号小店官方文档

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.logistics.channel.proxy.operate/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.logistics.channel.proxy.operate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.logistics.channel.proxy.operate/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4218)*