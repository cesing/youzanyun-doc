---
apiName: "youzan.cloud.model.extension.save.1.0.0"
version: "1.0.0"
appName: "model-extension"
apiGroup: "大客CRM"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/992"
---

# youzan.cloud.model.extension.save.1.0.0

> **所属分组**: 大客CRM

---

## 1. 场景说明

商家对于业务的描述需要增加更多的字段，来描述业务中的实体，比如订单，商品，会员等等，在使用扩展点、openAPI、消息推送等方式来处理业务逻辑时，使用模型扩展解决方案，有赞云可以把你定义的业务扩展数据于有赞的基础数据模型进行整合，这样就可以从接口参数中，可以接收到一个统一的模型。
详情请参考接入指南：https://doc.youzanyun.com/doc#/content/35700/38782/47178

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cloud.model.extension.save/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.cloud.model.extension.save/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cloud.model.extension.save/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/992)*