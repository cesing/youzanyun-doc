---
apiName: "youzan.guide.relation.bind.2.0.0"
version: "2.0.0"
appName: "guide-pyxis"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3734"
---

# youzan.guide.relation.bind.2.0.0

> **所属分组**: 其它

---

## 1. 场景说明

1）指定客户和导购进行专属关系绑定
2）如果客户已经有专属导购，这次接口调用成功的话，会刷新该客户和导购专属户关系的有效时间
3）调用该接口进行专属关系的绑定，专属关系变更设置默认为强制绑定，不受导购PC后台抢客相关设置的影响，只要客户和导购都存在，调用该接口就能进行绑定
4）调用该接口进行专属关系的绑定，若专属关系变更设置为按抢客设置绑定（即换绑时会校验是否符合抢客设置。如：关系有配置保护期，保护期内会换绑失败），则换绑时会校验是否符合抢客设置 

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.relation.bind/2.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.relation.bind/2.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.relation.bind/2.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3734)*