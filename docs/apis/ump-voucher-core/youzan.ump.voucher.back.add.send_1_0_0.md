---
apiName: "youzan.ump.voucher.back.add.send.1.0.0"
version: "1.0.0"
appName: "ump-voucher-core"
apiGroup: "营销优惠"
method: "sendBack"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3036"
---

# youzan.ump.voucher.back.add.send.1.0.0

> **所属分组**: 营销优惠  **所属应用**: ump-voucher-core

---

## 1. 场景说明

外部券回流发放
该接口不走发放前置校验，不扣减库存，直接落库存，发出发券消息，数据类型为回流类型
结合发券扩展点com.youzan.ump.voucher.core.extpoint.api.extpoint.ThirdpartyVoucherSendExtPoint进行使用，发券扩展点发送外部券之后，如果有需要回流发券操作，调用该接口记录发券信息
只用于连接器，外部应用不可用，当前用户志华双中心回流

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.voucher.back.add.send/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.voucher.back.add.send/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.voucher.back.add.send/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3036)*