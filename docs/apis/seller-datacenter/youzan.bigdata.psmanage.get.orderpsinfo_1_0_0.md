---
apiName: "youzan.bigdata.psmanage.get.orderpsinfo.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "数据分析"
method: "getPsInfoByOrderNo"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3998"
---

# youzan.bigdata.psmanage.get.orderpsinfo.1.0.0

> **所属分组**: 数据分析  **所属应用**: seller-datacenter

---

## 1. 场景说明

通过订单号查询订单所属推广分析信息

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.psmanage.get.orderpsinfo/1.0.0`

**请求参数**（1 个）:

```json
{
  "type": "object",
  "properties": {
    "tid": {
      "type": "java.lang.String",
      "description": "有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E20190312105415047400001"
    }
  },
  "required": [
    "tid"
  ]
}
```

**响应参数**（7 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.base.api.model.psmanage.chain.PsOrderInfo",
      "description": "业务数据",
      "example": ""
    },
    "tid": {
      "type": "java.lang.String",
      "description": "有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E20190312105415047400001"
    },
    "dcps": {
      "type": "java.lang.String",
      "description": "推广分析唯一标识符",
      "example": "213125605561431230.20001"
    },
    "ps_name": {
      "type": "java.lang.String",
      "description": "推广分析名称",
      "example": "推广分析01"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "网关返回码描述",
      "example": "successful"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "tid": "E20190312105415047400001",
  "dcps": "213125605561431230.20001",
  "ps_name": "推广分析01",
  "success": "true",
  "code": "200",
  "message": "successful"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.psmanage.get.orderpsinfo/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.psmanage.get.orderpsinfo/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3998)*