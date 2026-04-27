---
apiName: "youzan.crm.level.benefit.update.1.0.0"
version: "1.0.0"
appName: "scrm-open-java"
apiGroup: "会员与客户"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4955"
---

# youzan.crm.level.benefit.update.1.0.0

> **所属分组**: 会员与客户

---

## 1. 场景说明

 修改指定等级权益配置，将会覆盖原本的等级权益配置。比如赠品部分没有传入，将直接清空赠品配置。
支持微商城店铺、零售单店、连锁总部。
注意：此API会影响商家的会员等级权益，属于高风险接口，开发者接入需要保证合理调用。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.crm.level.benefit.update/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.crm.level.benefit.update/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.crm.level.benefit.update/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4955)*