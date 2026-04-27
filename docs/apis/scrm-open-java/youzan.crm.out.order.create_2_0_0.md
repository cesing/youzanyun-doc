---
apiName: "youzan.crm.out.order.create.2.0.0"
version: "2.0.0"
appName: "scrm-open-java"
apiGroup: "customer"
method: "outOrderCreateV2"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2024-01-26"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4348"
---
# youzan.crm.out.order.create.2.0.0
> **所属分组**: customer　**所属应用**: scrm-open-java
---
## 1. 场景说明
三方单据创建，目前仅支持无原单退款。CRM关联功能内测开放中，对接该接口时，请先咨询对应服务经理 1. 该接口目前仅用于记录无源单退款订单数、订单金额等信息，支持商家在CRM自定义报表中统计查看对应数据。 2. 有效支付次数（扣除无源单）将基于同步的无源单退款订单进行扣除，支持商家在CRM客户分群自定义条件中筛选扣除后支付次数。 3. 支持等级模式为消费等级模式时进行等级计算扣除无源单退款金额和次数。4.支持无原单退款导购业绩计算。

2.0.0版本在1.0.0版本基础上融合了导购系统接收外部单据并计算业绩提成接口（https://doc.youzanyun.com/detail/API/0/4220）功能，外部开发者无需单独调用导购系统接收外部单据并计算业绩提成接口（https://doc.youzanyun.com/detail/API/0/4220）接口进行导购业绩计算。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.crm.out.order.create/2.0.0`
**请求参数 Schema**（0 个参数）:
```json
{
  "type": "object",
  "properties": {},
  "required": []
}
```
**请求参数明细**：暂无数据

---
## 3. 响应
**响应参数 Schema**（0 个字段）:
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
**响应参数明细**：暂无数据

---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.crm.out.order.create/2.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.crm.out.order.create/2.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {}

resp = requests.post(url, json=payload, headers=headers)
print(resp.json())
```
---
## 5. 错误码
| 错误码 | 类型 | 说明 |
|--------|------|------|
| 10001 | `SYSTEM_ERROR` | 系统内部错误 |
| 10002 | `INVALID_PARAMETER` | 参数错误 |
| 10003 | `UNAUTHORIZED` | 未授权或授权已过期 |
| 10004 | `PERMISSION_DENIED` | 无权限调用此接口 |
| 10005 | `RESOURCE_NOT_FOUND` | 请求的资源不存在 |
| 20001 | `RATE_LIMIT_EXCEEDED` | 调用频率超限 |
| 20002 | `QUOTA_EXCEEDED` | 接口配额已用完 |
---
## 6. 权限与计费

**接口计费状态：未知（请以官网实际披露为准）。**

**拥有此API的能力包：** 暂无数据（请以官网实际披露为准）。

---
## 7. 权限说明

**应用类目 → 权限类型：**

| 应用类目 | 权限类型 |
|----------|----------|
| 有赞微商城、有赞零售、有赞教育、有赞美业 | 普通自研商家（基础权益） |
| 大客户定制接口、美业大客户定制、零售大客户定制、收款二维码-大客专用 | 大客定制接口（需购买大客套餐） |
| 客户关系CRM、门店POS | iPaaS 套餐权益（需购买 iPaaS 套餐） |

> 权限数据来源：[有赞云能力包说明](https://doc.youzanyun.com/detail/content/API/0/120)