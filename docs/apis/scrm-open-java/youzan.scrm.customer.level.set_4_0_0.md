---
apiName: "youzan.scrm.customer.level.set.4.0.0"
version: "4.0.0"
appName: "scrm-open-java"
apiGroup: "会员与客户"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/877"
---

# youzan.scrm.customer.level.set.4.0.0

> **所属分组**: 会员与客户

---

## 1. 场景说明

给会员设置单个等级
支持的用户账号类型
1-有赞粉丝id(有赞不同的合作渠道会生成不同渠道对应在有赞平台下的fans_id) ;
2-手机号;
4-union_id(同一用户，对同一个微信开放平台下的不同应用，unionid是相同的) ;
5-有赞用户id，用户在有赞的唯一id。推荐使用）
注意：不支持设置付费会员等级

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.scrm.customer.level.set/4.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.scrm.customer.level.set/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.scrm.customer.level.set/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/877)*