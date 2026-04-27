---
apiName: "youzan.scrm.ma.notice.callback.1.0.0"
version: "1.0.0"
appName: "scrm-ma-facade"
apiGroup: "数据分析"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4125"
---

# youzan.scrm.ma.notice.callback.1.0.0

> **所属分组**: 数据分析

---

## 1. 场景说明

营销画布自定义消息回调。
根据回调的消息触达结果，更新对应的触达记录。
需配合消息推送API：”营销画布自定义消息“组合使用。
商家通过CRM-营销画布配置了定制的消息触达节点，则会根据调度规则触发有赞云消息“营销画布自定义消息”，在消息完成消费后，通过回调本接口将执行结果返回，用于营销画布的后续效果数据分析。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.scrm.ma.notice.callback/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.scrm.ma.notice.callback/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.scrm.ma.notice.callback/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4125)*