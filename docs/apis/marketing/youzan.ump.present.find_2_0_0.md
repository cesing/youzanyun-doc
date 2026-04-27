---
apiName: "youzan.ump.present.find.2.0.0"
version: "2.0.0"
appName: "marketing"
apiGroup: "营销优惠"
method: "findCanUsePresentsWithCheckStock"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4548"
---

# youzan.ump.present.find.2.0.0

> **所属分组**: 营销优惠  **所属应用**: marketing

---

## 1. 场景说明

查询店铺可用的赠品信息，支持根据赠品活动名称关键词模糊查询。
返回数据规则：
1.活动在进行中（赠品开始有效期设置是当前时间，例如新增一个2021-03-20开始的赠品活动，在2021-03-01查询接口是获取不到这一条数据，因为该条数据还未进行），赠品活动未删除、未失效
2.赠品有库存
3.赠品对应的原商品未删除；

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.present.find/2.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.present.find/2.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.present.find/2.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4548)*