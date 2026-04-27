---
apiName: "youzan.cloud.deliveryconfig.callback.1.0.0"
version: "1.0.0"
appName: "cloud-connector-pangoo"
apiGroup: "消息推送"
method: "createConfigDeliveryTaskCallback"
timeout: 5000
authType: "无认证"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4301"
---

# youzan.cloud.deliveryconfig.callback.1.0.0

> **所属分组**: 消息推送  **所属应用**: cloud-connector-pangoo

---

## 1. 场景说明

数据通/融合舱商家选择的业务打通方案初始化结果回执。若初始化成功，则平台可展示给用户方案开通成功，否则告知失败原因.

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cloud.deliveryconfig.callback/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.deliveryconfig.callback/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cloud.deliveryconfig.callback/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4301)*