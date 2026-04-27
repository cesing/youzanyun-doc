---
apiName: "youzan.salesman.saleschannel.get.detail.1.0.0"
version: "1.0.0"
appName: "salesman-makani"
apiGroup: "分销与供货"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3368"
---

# youzan.salesman.saleschannel.get.detail.1.0.0

> **所属分组**: 分销与供货

---

## 1. 场景说明

根据店铺id，渠道商id，渠道商类型 查询渠道商信息，包括基本信息和收益，团队数据
使用条件：
商家需要订阅云分销插件，在云分销商家后台添加渠道商之后，获取到对应的渠道商（代理商/订货商）id

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.salesman.saleschannel.get.detail/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.salesman.saleschannel.get.detail/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.salesman.saleschannel.get.detail/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3368)*