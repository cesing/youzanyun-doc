---
apiName: "youzan.saleschannel.cultivation.achievement.list.1.0.0"
version: "1.0.0"
appName: "salesman-open"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4436"
---

# youzan.saleschannel.cultivation.achievement.list.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

分页查询渠道商培育业绩，可按时间、培育者昵称或手机号、被培育者昵称或手机号进行筛选。连锁场景下仅支持查指定分店的培育业绩数据，必须传递node_kdt_id参数。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.saleschannel.cultivation.achievement.list/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.saleschannel.cultivation.achievement.list/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.saleschannel.cultivation.achievement.list/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4436)*