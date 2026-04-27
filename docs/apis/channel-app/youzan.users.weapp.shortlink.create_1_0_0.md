---
apiName: "youzan.users.weapp.shortlink.create.1.0.0"
version: "1.0.0"
appName: "channel-app"
apiGroup: "user"
method: "generateShortLinkV2"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2022-03-15"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3712"
---
# youzan.users.weapp.shortlink.create.1.0.0
> **所属分组**: user　**所属应用**: channel-app
---
## 1. 场景说明
1、生成short link的时候，是有要求的，要类目为电商平台、商家自营、跨境电商
2、在类目不符合的时候即无法生成short link的时候，会降级获取有赞短链，降级获取的有赞短链，默认30天有效
3、有赞短链也是可以打开的，但是相对short link，打开的速度慢一些，链路长一些
4、short link是只能在微信内打开唤起小程序，而有赞短链在微信内外都可以打开
5、单个小程序每日生成 ShortLink 上限为50万个（包含短期有效 ShortLink 与长期有效 ShortLink ）
 6、单个小程序总共可生成永久有效 ShortLink 上限为10万个，请谨慎调用。
 7、短期有效ShortLink 有效时间为30天，单个小程序生成短期有效ShortLink 不设上限。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.users.weapp.shortlink.create/1.0.0`
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
curl -X POST 'https://open.youzanyun.com/api/youzan.users.weapp.shortlink.create/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.users.weapp.shortlink.create/1.0.0"
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