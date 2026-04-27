---
apiName: "youzan.cardvoucher.valuecard.pay.rcd.bypub.search.3.0.1"
version: "3.0.1"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "pageQueryPayLogByPublishKdtId"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/533"
---

# youzan.cardvoucher.valuecard.pay.rcd.bypub.search.3.0.1

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

该接口用于具备发卡能力的总店或合伙人店铺查询其发行的储值卡所产生的全部支付记录
版本新增：yz_open_id（有赞开放ID）参数


---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.pay.rcd.bypub.search/3.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.pay.rcd.bypub.search/3.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.pay.rcd.bypub.search/3.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/533)*