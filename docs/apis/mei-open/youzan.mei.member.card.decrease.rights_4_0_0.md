---
apiName: "youzan.mei.member.card.decrease.rights.4.0.0"
version: "4.0.0"
appName: "mei-open"
apiGroup: "美业"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3845"
---

# youzan.mei.member.card.decrease.rights.4.0.0

> **所属分组**: 美业

---

## 1. 场景说明

大客户定制接口
扣减次卡权益次数

注意：
* 该接口所扣减权益将不会在 [报表中心/卡项统计报表] 内呈现，且PC页面无法展示消耗原因
* 需商家提前评估影响，再进行调用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.mei.member.card.decrease.rights/4.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.mei.member.card.decrease.rights/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.mei.member.card.decrease.rights/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3845)*