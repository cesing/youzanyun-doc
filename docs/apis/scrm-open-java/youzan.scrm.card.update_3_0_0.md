---
apiName: "youzan.scrm.card.update.3.0.0"
version: "3.0.0"
appName: "scrm-open-java"
apiGroup: "大客CRM"
method: "updateCard"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/291"
---

# youzan.scrm.card.update.3.0.0

> **所属分组**: 大客CRM  **所属应用**: scrm-open-java

---

## 1. 场景说明

更新会员卡（支持微商城，零售，教育）
以下参数必传{"card_alias":"Y2fqbv28v2rt34","name":"OpenDazhu","color_code":"#cf3e36","description":"1111","service_phone":"10010","activate_mode":1,"sync_weixin_mode":1,"rights":[{"type":2,"discount":80,"is_available":true}],"term_days":360,"term_type":1}

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.scrm.card.update/3.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.scrm.card.update/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.scrm.card.update/3.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/291)*