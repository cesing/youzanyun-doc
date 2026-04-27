---
apiName: "youzan.cardvoucher.card.create.template.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "create"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3588"
---

# youzan.cardvoucher.card.create.template.1.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

地址：商家后台-会员-储值规则，创建余额模板或储值卡模板
一个店铺只能创建一个余额模板，可创建多个储值卡模板，储值卡的名字不能重复
仅限连接器项目使用，此接口生成的卡模板部分属性储值内部已写死

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.create.template/1.0.0`

**请求参数**（7 个）:

```json
{
  "type": "object",
  "properties": {
    "kdt_id": {
      "type": "java.lang.String",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "102129885"
    },
    "operator_uid": {
      "type": "java.lang.String",
      "description": "操作人id，传入注册过有赞的手机号，会自动转换成有赞体系内的id",
      "example": "18758285476"
    },
    "template_type": {
      "type": "java.lang.Integer",
      "description": "模板类型：1001 余额模板 1002 储值卡模板",
      "example": "1002"
    },
    "operator_name": {
      "type": "java.lang.String",
      "description": "操作人名称",
      "example": "fairy"
    },
    "template_name": {
      "type": "java.lang.String",
      "description": "模版名称，",
      "example": "fairy测试储值卡"
    },
    "limit_type": {
      "type": "java.lang.Integer",
      "description": "卡模板适用店铺类型：0 所有店铺 1 部分店铺适用 2 部分店铺不适应",
      "example": "0"
    },
    "kdt_ids": {
      "type": "java.util.List<java.lang.String>",
      "description": "当卡模板适用店铺类型为1/2时必填",
      "example": "[\"102129885\"]"
    }
  },
  "required": [
    "kdt_id",
    "operator_uid",
    "template_type",
    "template_name",
    "limit_type"
  ]
}
```

**响应参数**（7 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenTemplateDTO",
      "description": "创建卡模板接口响应参数",
      "example": ""
    },
    "template_no": {
      "type": "java.lang.String",
      "description": "模版编号",
      "example": "6534123450"
    },
    "success": {
      "type": "boolean",
      "description": "请求是否成功",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "响应码",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "响应信息",
      "example": "成功"
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "请求id",
      "example": "0000000000000"
    },
    "error_data": {
      "type": "java.util.Map<java.lang.String,java.lang.Object>",
      "description": "错误信息",
      "example": "错误"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "template_no": "6534123450",
  "success": "true",
  "code": "200",
  "message": "成功",
  "request_id": "0000000000000",
  "error_data": "错误"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.card.create.template/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.create.template/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3588)*