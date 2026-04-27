---
apiName: "youzan.users.info.query.1.0.0"
version: "1.0.0"
appName: "uic-user"
apiGroup: "会员与客户"
method: "queryUserForOpen"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2193"
---

# youzan.users.info.query.1.0.0

> **所属分组**: 会员与客户  **所属应用**: uic-user

---

## 1. 场景说明

用户信息查询接口（非店铺客户查询接口，如果有赞域存在该账号信息，那么接口就会返回该账号的数据，如果查店铺客户的数据使用：youzan.scrm.customer.detail.get）。
查询条件说明：
1. 支持根据yz_open_id查询
2. 支持根据mobile（国内手机号）查询
3. 支持根据unionId（微信体系下帐号标识）查询
4. 支持weixin_open_id + open_id_type查询，支持微信公众号H5，微信小程序、有赞大账号
5. 查询优先级yz_open_id>mobile>weixin_union_id>weixin_open_id
返回结果说明：
1.  默认只返回用户对应的手机帐号信息（platform_type = 0）
2. 可使用result_type_list控制返回结果，如传入[1, 9]则返回自有粉丝和大账号粉丝；
  补充说明：在微信公众号场景下，正常会进行两次授权，一次通过商家公众号授权，一次通过有赞公众号授权，分别产生不同的用户数据：
1）1-微信公众号：通过商家的公众号授权产生的用户
2）9-微信大账号：通过”有赞“公众号授权产生的用户


---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.users.info.query/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.users.info.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.users.info.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2193)*