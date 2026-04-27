---
apiName: "youzan.mei.valuecard.recharge.refund.operate.4.0.0"
version: "4.0.0"
appName: "mei-open"
apiGroup: "mei_open_ka"
method: "refund"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-08-12"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3146"
---
# youzan.mei.valuecard.recharge.refund.operate.4.0.0
> **所属分组**: mei_open_ka　**所属应用**: mei-open
---
## 1. 场景说明
该接口仅支持美业调用，适用于根据 【youzan.mei.valuecard.recharge.operate】接口充值后进行退款
商家选择使用时，请注意，调用该接口退款【仅作记账处理, 进行标记退款】，不支持原路退回，比如支付宝/微信等退款方式
一般情况下，退款将立即完成，余额会立即扣除
如发生下述任一情况而导致服务中断及开发者损失的，有赞不承担责任： （1）发生不可抗力情形的； （2）黑客攻击、计算机病毒侵入或发作的； （3）计算机系统遭到破坏、瘫痪或无法正常使用的； （4）电信部门技术调整的； （5）因政府管制而造成暂时性关闭的； （6）其它非因有赞的原因
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.refund.operate/4.0.0`
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
curl -X POST 'https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.refund.operate/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.refund.operate/4.0.0"
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