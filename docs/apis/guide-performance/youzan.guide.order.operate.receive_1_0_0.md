---
apiName: "youzan.guide.order.operate.receive.1.0.0"
version: "1.0.0"
appName: "guide-performance"
apiGroup: "guide_api"
method: "receiveOrder"
timeout: "3000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-09-18"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4220"
---
# youzan.guide.order.operate.receive.1.0.0
> **所属分组**: guide_api　**所属应用**: guide-performance
---
## 1. 场景说明
当商家有一种类型的单据，无法转化为有赞交易中心的单据模型，但是又需要在导购助手插件中做数据统计或业绩提成计算的，可以通过此接口推送单据到导购助手。同时为了保证对应单据信息在导购助手的单据列表和详情页能够完整展示，需要同步实现扩展点 ”com.youzan.cloud.extension.api.guide.ListOuterOrderInfos“。
接口支持同一个单据重复调用，重复调用注意事项如下：
1. 当前接口支持同一个单据重复推送，但是每次推送的单据信息必须是一致的，从第二次推送开始，每次推送会基于第一次推送的信息对后续推动的内容做校验，如果推送的单据信息不一致，则拒绝推送请求，此处的单据信息校验不包含业务操作字段operate。
2. 业绩和提成的计算仅执行一次，如果多次推送标记计算业绩或提成，则以第一次推送时计算的结果为准。
当前可接入单据：无原单退款单(biz_type=3, system_from=2)；
当前版本已废弃，新接入的商家请对接接口 youzan.crm.out.order.create.2.0.0
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.guide.order.operate.receive/1.0.0`
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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.order.operate.receive/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.guide.order.operate.receive/1.0.0"
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