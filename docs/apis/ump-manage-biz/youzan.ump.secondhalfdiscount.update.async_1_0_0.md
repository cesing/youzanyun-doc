---
apiName: "youzan.ump.secondhalfdiscount.update.async.1.0.0"
version: "1.0.0"
appName: "ump-manage-biz"
apiGroup: "营销优惠"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2713"
---

# youzan.ump.secondhalfdiscount.update.async.1.0.0

> **所属分组**: 营销优惠

---

## 1. 场景说明

第二件半价活动异步编辑。第二件半价活动包括1.第2件半价活动，2.买1送1活动，3.自定义优惠活动。合youzan_ump_OperateActivityResult异步操作活动结果消息使用。编辑后会返回一个rediskey。同时监听youzan_ump_OperateActivityResult消息。消息中会包含编辑接口同步返回的rediskey和编辑结果。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.secondhalfdiscount.update.async/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.secondhalfdiscount.update.async/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.secondhalfdiscount.update.async/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2713)*