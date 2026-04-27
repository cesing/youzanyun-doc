---
apiName: "youzan.guide.relation.bind.2.0.0"
version: "2.0.0"
appName: "guide-pyxis"
apiGroup: "guide_api"
method: "bindRelation"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-04-20"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3734"
---
# youzan.guide.relation.bind.2.0.0
> **所属分组**: guide_api　**所属应用**: guide-pyxis
---
## 1. 场景说明
1）指定客户和导购进行专属关系绑定
2）如果客户已经有专属导购，这次接口调用成功的话，会刷新该客户和导购专属户关系的有效时间
3）调用该接口进行专属关系的绑定，专属关系变更设置默认为强制绑定，不受导购PC后台抢客相关设置的影响，只要客户和导购都存在，调用该接口就能进行绑定
4）调用该接口进行专属关系的绑定，若专属关系变更设置为按抢客设置绑定（即换绑时会校验是否符合抢客设置。如：关系有配置保护期，保护期内会换绑失败），则换绑时会校验是否符合抢客设置 
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.guide.relation.bind/2.0.0`
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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.relation.bind/2.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.guide.relation.bind/2.0.0"
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