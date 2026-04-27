---
apiName: "youzan.ump.manage.activity.find.1.0.0"
version: "1.0.0"
appName: "marketing"
apiGroup: "营销优惠"
method: "queryActivityListPaged"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/927"
---

# youzan.ump.manage.activity.find.1.0.0

> **所属分组**: 营销优惠  **所属应用**: marketing

---

## 1. 场景说明

批量拉取商家端活动列表，返回基本活动信息和活动描述；当前支持拉取的活动：限时折扣、砍价0元购、打包一口价、满减送、第二件半价、0元抽奖、秒杀、优惠券、好友瓜分券

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.manage.activity.find/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.manage.activity.find/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.manage.activity.find/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/927)*