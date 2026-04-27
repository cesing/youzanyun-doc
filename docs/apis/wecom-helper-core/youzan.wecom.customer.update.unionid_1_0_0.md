---
apiName: "youzan.wecom.customer.update.unionid.1.0.0"
version: "1.0.0"
appName: "wecom-helper-core"
apiGroup: "其它"
method: "updateUnionId"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/5132"
---

# youzan.wecom.customer.update.unionid.1.0.0

> **所属分组**: 其它  **所属应用**: wecom-helper-core

---

## 1. 场景说明

给指定的企助客户设置union_id。若商城的小程序、公众号客户，授权获取到相同union_id，会触发账号合并，完成与商城和企助客户打通。
当商家企业微信、小程序、公众号主体不一致时，有赞无法调用企业微信接口客户ID转换接口，导致企助客户和商城客户无法打通。若商家有接入企业微信自建应用，则权限获取到客户的union_id，调用本接口可以将union_id设置到对应有赞企助客户身上，促使企助和商城的客户打通。

注意：
1）如果商家企业微信、小程序、公众号主体一致，无需接入调用接口，使用标品流程可以完成客户打通，参考：https://help.youzan.com/displaylist/detail_26_26-2-55658
2）企业微信、小程序、公众号必须绑定在同一个开放平台下，才能获取到相同的union_id，完成账号打通

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.wecom.customer.update.unionid/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.wecom.customer.update.unionid/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.wecom.customer.update.unionid/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/5132)*