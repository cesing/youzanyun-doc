---
apiName: "youzan.guide.visit.taobao.add.1.0.0"
version: "1.0.0"
appName: "guide-pyxis"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4912"
---

# youzan.guide.visit.taobao.add.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明


保存客户访问导购分享淘天链接记录，用于客户在淘宝或天猫下单后计算业绩。

场景：
导购分享淘宝小程序链接给客户，客户点击淘宝小程序链接，然后保存客户和导购的销售关系，后续客户在淘宝下单后 计算导购业绩。


---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.visit.taobao.add/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.visit.taobao.add/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.visit.taobao.add/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4912)*