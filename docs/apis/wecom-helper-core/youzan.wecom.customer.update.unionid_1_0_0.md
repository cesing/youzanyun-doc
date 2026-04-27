---
apiName: "youzan.wecom.customer.update.unionid.1.0.0"
version: "1.0.0"
appName: "wecom-helper-core"
apiGroup: "wecom-helper-api"
method: "updateUnionId"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2026-04-13"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/5132"
---
# youzan.wecom.customer.update.unionid.1.0.0
> **所属分组**: wecom-helper-api　**所属应用**: wecom-helper-core
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
curl -X POST 'https://open.youzanyun.com/api/youzan.wecom.customer.update.unionid/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.wecom.customer.update.unionid/1.0.0"
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