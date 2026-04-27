---
apiName: "youzan.crm.out.order.create.2.0.0"
version: "2.0.0"
appName: "scrm-open-java"
apiGroup: "会员与客户"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4348"
---

# youzan.crm.out.order.create.2.0.0

> **所属分组**: 会员与客户

---

## 1. 场景说明

三方单据创建，目前仅支持无原单退款。CRM关联功能内测开放中，对接该接口时，请先咨询对应服务经理 1. 该接口目前仅用于记录无源单退款订单数、订单金额等信息，支持商家在CRM自定义报表中统计查看对应数据。 2. 有效支付次数（扣除无源单）将基于同步的无源单退款订单进行扣除，支持商家在CRM客户分群自定义条件中筛选扣除后支付次数。 3. 支持等级模式为消费等级模式时进行等级计算扣除无源单退款金额和次数。4.支持无原单退款导购业绩计算。

2.0.0版本在1.0.0版本基础上融合了导购系统接收外部单据并计算业绩提成接口（https://doc.youzanyun.com/detail/API/0/4220）功能，外部开发者无需单独调用导购系统接收外部单据并计算业绩提成接口（https://doc.youzanyun.com/detail/API/0/4220）接口进行导购业绩计算。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.crm.out.order.create/2.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.crm.out.order.create/2.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.crm.out.order.create/2.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4348)*