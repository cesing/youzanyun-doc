---
apiName: "youzan.users.info.query.1.0.1"
version: "1.0.1"
appName: "uic-user"
apiGroup: "user"
method: "queryUserForOpen"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2024-06-12"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4451"
---
# youzan.users.info.query.1.0.1
> **所属分组**: user　**所属应用**: uic-user
---
## 1. 场景说明
用户信息查询接口（非店铺客户查询接口，如果有赞域存在该账号信息，那么接口就会返回该账号的数据，如果查店铺客户的数据使用：youzan.scrm.customer.detail.get）。
查询条件说明：
1. 支持根据yz_open_id查询
2. 支持根据mobile查询，默认使用+86区号,如果需要使用其他地区的手机号需要加上区号,例如"+54-123123"
3. 支持根据unionId（微信体系下帐号标识）查询
4. 支持weixin_open_id + open_id_type查询，支持微信公众号H5，微信小程序、有赞大账号
5. 查询优先级yz_open_id>mobile>weixin_union_id>weixin_open_id
返回结果说明：
1.  默认只返回用户对应的手机帐号信息（platform_type = 0）
2. 可使用result_type_list控制返回结果，如传入[1, 9]则返回自有粉丝和大账号粉丝；
  补充说明：在微信公众号场景下，正常会进行两次授权，一次通过商家公众号授权，一次通过有赞公众号授权，分别产生不同的用户数据：
1）1-微信公众号：通过商家的公众号授权产生的用户
2）9-微信大账号：通过”有赞“公众号授权产生的用户

---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.users.info.query/1.0.1`
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
curl -X POST 'https://open.youzanyun.com/api/youzan.users.info.query/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.users.info.query/1.0.1"
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