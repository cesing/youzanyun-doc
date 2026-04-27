---
apiName: "youzan.pay.user.contract.query.TaxContractSign.1.0.4"
version: "1.0.4"
appName: "pay-gateway"
apiGroup: "大客CRM"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3260"
---

# youzan.pay.user.contract.query.TaxContractSign.1.0.4

> **所属分组**: 大客CRM

---

## 1. 场景说明

查询是否有生效的C端个税代缴协议，输入用户有赞openId
返回data中pass值为true则代表查询到生效的C端个税代缴协议
返回data中pass值为false则代表未查询到生效的C端个税代缴协议
bizSuccess代表了业务操作是否成功


---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.pay.user.contract.query.TaxContractSign/1.0.4`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.pay.user.contract.query.TaxContractSign/1.0.4' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.pay.user.contract.query.TaxContractSign/1.0.4"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3260)*