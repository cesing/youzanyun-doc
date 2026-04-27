---
apiName: "youzan.cardvoucher.valuecard.fund.adjust.3.0.0"
version: "3.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "adjust"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/199"
---

# youzan.cardvoucher.valuecard.fund.adjust.3.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

连锁门店网店模式的总部，没有经营权限的，不能使用该接口。
如发生下述任一情况而导致服务中断及开发者损失的，有赞不承担责任：
（1）发生不可抗力情形的；
（2）黑客攻击、计算机病毒侵入或发作的；
（3）计算机系统遭到破坏、瘫痪或无法正常使用的；
（4）电信部门技术调整的；
（5）因政府管制而造成暂时性关闭的；
（6）其它非因有赞的过错而引起的。
此为老版，推荐使用3.0.1新版本


---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.adjust/3.0.0`

**请求参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.request.OpenAdjustRequest",
      "description": "",
      "example": ""
    },
    "request_no": {
      "type": "java.lang.String",
      "description": "请求号，请确保唯一（长度不超过24个字符）",
      "example": "weixiao20190730001"
    },
    "mobile": {
      "type": "java.lang.String",
      "description": "客户手机号码（mobile或者buyer_id二选一）",
      "example": "18972515558"
    },
    "buyer_id": {
      "type": "java.lang.Long",
      "description": "客户Id（mobile或者buyer_id二选一）",
      "example": "1441668074"
    },
    "card_no": {
      "type": "java.lang.String",
      "description": "卡号",
      "example": "310201043501229"
    },
    "adjust_principal": {
      "type": "java.lang.Long",
      "description": "调整本金金额，单位：分",
      "example": "100"
    },
    "adjust_bonus": {
      "type": "java.lang.Long",
      "description": "调整赠送金金额，单位：分",
      "example": "20"
    },
    "adjust_type": {
      "type": "java.lang.Integer",
      "description": "调账类型；1：调增，2：调减",
      "example": "1"
    },
    "remark": {
      "type": "java.lang.String",
      "description": "描述",
      "example": "描述TEST"
    },
    "operator_name": {
      "type": "java.lang.String",
      "description": "操作员姓名",
      "example": "卫潇"
    },
    "operator_mobile": {
      "type": "java.lang.String",
      "description": "操作员手机号",
      "example": "13209******"
    }
  },
  "required": [
    "request_no",
    "card_no",
    "adjust_type",
    "operator_name",
    "operator_mobile"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.OpenAdjustResultDTO",
      "description": "",
      "example": ""
    },
    "request_no": {
      "type": "java.lang.String",
      "description": "请求号",
      "example": "weixiao20190730001"
    },
    "adjust_no": {
      "type": "java.lang.String",
      "description": "调账单号",
      "example": "CDA190730041652000092"
    },
    "status": {
      "type": "java.lang.String",
      "description": "调账状态；SUCCESS：成功，FAIL：失败，ING：处理中",
      "example": "SUCCESS"
    },
    "code": {
      "type": "int",
      "description": "网关返回码，表示本次请求是否成功。200:成功",
      "example": "200"
    },
    "msg": {
      "type": "java.lang.String",
      "description": "状态描述",
      "example": "调账成功"
    },
    "inner_adjust_no": {
      "type": "java.lang.String",
      "description": "内部调账单号",
      "example": "SGCDA190730041652000092"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。true:成功,false:失败",
      "example": "true"
    },
    "message": {
      "type": "java.lang.String",
      "description": "网关返回码描述",
      "example": "successful"
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "",
      "example": ""
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "request_no": "weixiao20190730001",
  "adjust_no": "CDA190730041652000092",
  "status": "SUCCESS",
  "code": "200",
  "msg": "调账成功",
  "inner_adjust_no": "SGCDA190730041652000092",
  "success": "true"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.adjust/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.valuecard.fund.adjust/3.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/199)*