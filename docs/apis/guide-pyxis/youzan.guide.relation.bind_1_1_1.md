---
apiName: "youzan.guide.relation.bind.1.1.1"
version: "1.1.1"
appName: "guide-pyxis"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4313"
---

# youzan.guide.relation.bind.1.1.1

> **所属分组**: 其它

---

## 1. 场景说明

绑定导购专属关系（需向有赞申请）：
1.接口为开白接口,需要向有赞申请通过后，才可以调用接口。
2.支持给停用状态 和 正常状态 的导购 绑定客户专属关系。
3.不支持 给 清退状态的导购绑定专属关系。
4. 需要 向有赞（新零售-解决方案-售后-定制交付） 部门申请接口调用权限。



---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.relation.bind/1.1.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.relation.bind/1.1.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.relation.bind/1.1.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4313)*