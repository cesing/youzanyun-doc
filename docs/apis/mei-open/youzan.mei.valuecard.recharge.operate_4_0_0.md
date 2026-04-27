---
apiName: "youzan.mei.valuecard.recharge.operate.4.0.0"
version: "4.0.0"
appName: "mei-open"
apiGroup: "美业"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3116"
---

# youzan.mei.valuecard.recharge.operate.4.0.0

> **所属分组**: 美业

---

## 1. 场景说明

该接口仅支持美业调用，适用于根据account_no等给用户充值，目前仅支持类似支付10元储值入账10元的功能，暂不支持储值规则。
接口仅做充值受理，是否最后充值入账成功可以查询【youzan.mei.valuecard.recharge.get.result】接口。
目前充值仅支持 现金/ 自定义记账渠道方式记录支付方式
如发生下述任一情况而导致服务中断及开发者损失的，有赞不承担责任： （1）发生不可抗力情形的； （2）黑客攻击、计算机病毒侵入或发作的； （3）计算机系统遭到破坏、瘫痪或无法正常使用的； （4）电信部门技术调整的； （5）因政府管制而造成暂时性关闭的； （6）其它非因有赞的原因

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.operate/4.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.operate/4.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.mei.valuecard.recharge.operate/4.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3116)*