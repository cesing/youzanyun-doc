---
apiName: "youzan.guide.shoppingguide.query.1.0.1"
version: "1.0.1"
appName: "guide-pyxis"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3584"
---

# youzan.guide.shoppingguide.query.1.0.1

> **所属分组**: 其它

---

## 1. 场景说明

查询导购员信息。（相比于原版接口，该接口将导购信息分为基础信息跟扩展信息两部分，基础信息中提供三方开放者所需要的导购基础信息，扩展字段中提供非导购核心信息字段，可满足连接器项目开发需求）
 Ps. 该接口已废弃，请用youzan.guide.shoppingguide.get.2.0.0接口

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.shoppingguide.query/1.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.shoppingguide.query/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.shoppingguide.query/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3584)*