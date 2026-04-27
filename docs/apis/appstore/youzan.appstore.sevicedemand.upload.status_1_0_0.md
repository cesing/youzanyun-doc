---
apiName: "youzan.appstore.sevicedemand.upload.status.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "大客CRM"
authType: "无认证"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2802"
---

# youzan.appstore.sevicedemand.upload.status.1.0.0

> **所属分组**: 大客CRM

---

## 1. 场景说明

修改服务市场需求状态

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.sevicedemand.upload.status/1.0.0`

**认证方式**: 无认证

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "service_demand_status_update_request": {
      "type": "com.youzan.cloud.appstore.api.dto.request.demand.ServiceDemandStatusUpdateRequest",
      "description": "请求集",
      "example": ""
    },
    "demand_no": {
      "type": "java.lang.String",
      "description": "需求编号",
      "example": "864642465397448704"
    },
    "status": {
      "type": "java.lang.Integer",
      "description": "需求状态@seeServiceDemandStatusEnum",
      "example": "10"
    },
    "remark": {
      "type": "java.lang.String",
      "description": "需求备注",
      "example": "需求状态变更备注"
    }
  },
  "required": [
    "demand_no",
    "status",
    "remark"
  ]
}
```

**响应参数**（5 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.lang.Boolean",
      "description": "data",
      "example": "true"
    },
    "success": {
      "type": "boolean",
      "description": "是否成功",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "结果code",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "结果message",
      "example": "成功"
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "请求id",
      "example": "111111"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "true",
  "success": "true",
  "code": "200",
  "message": "成功",
  "request_id": "111111"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.sevicedemand.upload.status/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.appstore.sevicedemand.upload.status/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2802)*