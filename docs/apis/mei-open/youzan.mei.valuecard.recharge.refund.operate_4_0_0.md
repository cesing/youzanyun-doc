---
apiName: "youzan.mei.valuecard.recharge.refund.operate.4.0.0"
version: "4.0.0"
appName: "mei-open"
apiGroup: "美业"
method: "refund"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3146"
---

# youzan.mei.valuecard.recharge.refund.operate.4.0.0

> **所属分组**: 美业  **所属应用**: mei-open

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
curl -X POST 'https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.refund.operate/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.refund.operate/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3146)*