---
apiName: "youzan.cardvoucher.poundage.rule.query.3.0.0"
version: "3.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
method: "queryPoundageRule"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3057"
---

# youzan.cardvoucher.poundage.rule.query.3.0.0

> **所属分组**: 储值卡  **所属应用**: yz-cardvoucher-biz

---

## 1. 场景说明

储值卡退卡手续费规则查询，调用储值卡退卡申请API前置调用，用于计算退卡手续费

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.poundage.rule.query/3.0.0`

**请求参数**（0 个）:

```json
{
  "type": "object",
  "properties": {},
  "required": []
}
```

**响应参数**（9 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.response.PoundageRuleDTO",
      "description": "返回参数",
      "example": ""
    },
    "scenes": {
      "type": "java.lang.String",
      "description": "场景，RECEDE_CARD:退卡",
      "example": "RECEDE_CARD"
    },
    "type": {
      "type": "java.lang.String",
      "description": "类型：FIX:固定手续费，PERCENT:百分比",
      "example": "PERCENT"
    },
    "poundage_value": {
      "type": "java.lang.Long",
      "description": "手续费金额，type为FIX：则为具体金额,单位为分； type为PERCENT：返回值范围0~10000，单位：万分比 例如返回值为10即表示手续费比例是0.1%",
      "example": "1"
    },
    "format_poundage_value": {
      "type": "java.lang.String",
      "description": "手续费金额，数值为保留2位小数后的格式化字符串，可以直接用于展示",
      "example": "0.01"
    },
    "limit_value": {
      "type": "java.lang.Long",
      "description": "手续费门槛金额，退卡金额高于门槛金额，按上述规则收取手续费，单位为分",
      "example": "10"
    },
    "success": {
      "type": "boolean",
      "description": "处理结果",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "处理结果状态码",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "处理结果提示",
      "example": "执行成功"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "scenes": "RECEDE_CARD",
  "type": "PERCENT",
  "poundage_value": "1",
  "format_poundage_value": "0.01",
  "limit_value": "10",
  "success": "true",
  "code": "200"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.poundage.rule.query/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.poundage.rule.query/3.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3057)*