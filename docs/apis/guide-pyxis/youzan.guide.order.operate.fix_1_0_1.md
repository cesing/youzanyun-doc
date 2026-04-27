---
apiName: "youzan.guide.order.operate.fix.1.0.1"
version: "1.0.1"
appName: "guide-pyxis"
apiGroup: "guide_api"
method: "operateOrder"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2025-05-16"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4802"
---
# youzan.guide.order.operate.fix.1.0.1
> **所属分组**: guide_api　**所属应用**: guide-pyxis
---
## 1. 场景说明
面对打通订单数据和客户定制了业绩提成流程的有赞订单数据，因打通过程中或定制逻辑出现问题导致的问题数据需要进行修复时，使用此接口进行对应的数据修复。当前接口支持以下场景数据处理：1.订单通过有赞的业绩提成规则计算了导购员的业绩提成，但是计算错误或导购员错误，需要删除数据重新归因计算业绩提成，可以通过此接口对已经生成的业绩提成数据进行删除并重新归因，此时接口传参operate_type传10，接口入参除了基本的单据信息还需传入归因所需要的字段2.订单通过有赞的业绩提成规则计算了导购员的业绩提成，出现订单退款单没有处理 或 因为修复数据重新归因了，可以通过此接口重新执行指定订单下的所有退款单的业绩提成数据生成，此时接口传参operate_type传2； 3.商家订单数据出现异常，需要对层级的数据统计进行修复，可以通过此接口删除并重新按照最新的数据生成层级订单明细数据，此时接口传参operate_type传3，该场景数据修复为异步修复，根据并发量在调用后请适当等1-5分钟。 4.商家同步无原单退款单时，存在部分信息同步错误，需要重新同步，例如商品信息错误，退款金额错误等，可以通过此接口删除已经记录的数据，此时接口传参operate_type传4。 6.商家同步线下订单或无原单退款单时，因为商品id或skuId信息错误导致单据明细无法关联品牌品类快照，需要根据最新的商品信息重新修复品牌品类快照，可以通过此接口进行修复，此时接口传参operate_type传6。注:使用接口前请先找导购值班申请令牌，否则接口默认无权限
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.guide.order.operate.fix/1.0.1`
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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.order.operate.fix/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.guide.order.operate.fix/1.0.1"
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