---
apiName: "youzan.appstore.service.demand.order.query.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "大客CRM"
method: "getDemandOrderDetail"
timeout: 5000
authType: "无认证"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3092"
---

# youzan.appstore.service.demand.order.query.1.0.0

> **所属分组**: 大客CRM  **所属应用**: appstore

---

## 1. 场景说明

服务需求订单查询订单金额（纷享销客，连接器使用）当data返回为空时，代表kdt_id和订单号无对应关系。当data有值时表示请求成功

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.service.demand.order.query/1.0.0`

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "tid": {
      "type": "java.lang.String",
      "description": "有赞应用市场订单号",
      "example": "23202107272015210109053"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "demand_no": {
      "type": "java.lang.String",
      "description": "需求号 （youzan.appstore.sevicedemand.query接口获取，demand_no字段）",
      "example": "12345"
    }
  },
  "required": [
    "tid",
    "kdt_id"
  ]
}
```

**响应参数**（6 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.cloud.appstore.api.dto.response.open.DemandOrderResponse",
      "description": "data",
      "example": ""
    },
    "tid": {
      "type": "java.lang.String",
      "description": "有赞应用市场订单号",
      "example": "23202107272015210109053"
    },
    "price": {
      "type": "java.lang.Long",
      "description": "订单金额（分）",
      "example": "123"
    },
    "success": {
      "type": "boolean",
      "description": "true",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "200",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "successful",
      "example": "successful"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "tid": "23202107272015210109053",
  "price": "123",
  "success": "true",
  "code": "200",
  "message": "successful"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.service.demand.order.query/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.appstore.service.demand.order.query/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3092)*