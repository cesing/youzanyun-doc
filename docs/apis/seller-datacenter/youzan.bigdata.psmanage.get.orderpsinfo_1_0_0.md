---
apiName: "youzan.bigdata.psmanage.get.orderpsinfo.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "data_center"
method: "getPsInfoByOrderNo"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2023-02-19"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3998"
---
# youzan.bigdata.psmanage.get.orderpsinfo.1.0.0
> **所属分组**: data_center　**所属应用**: seller-datacenter
---
## 1. 场景说明
通过订单号查询订单所属推广分析信息
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.psmanage.get.orderpsinfo/1.0.0`
**请求参数 Schema**（1 个参数）:
```json
{
  "type": "object",
  "properties": {
    "tid": {
      "type": "string",
      "description": "有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E20190312105415047400001"
    }
  },
  "required": [
    "tid"
  ]
}
```
**请求参数明细**（1 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `tid` | `string` | ✅ | `E20190312105415047400001` | 有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
---
## 3. 响应
**响应参数 Schema**（7 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "业务数据"
    },
    "tid": {
      "type": "string",
      "description": "有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E20190312105415047400001"
    },
    "dcps": {
      "type": "string",
      "description": "推广分析唯一标识符",
      "example": "213125605561431230.20001"
    },
    "ps_name": {
      "type": "string",
      "description": "推广分析名称",
      "example": "推广分析01"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "successful"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "tid": "E20190312105415047400001",
  "dcps": "213125605561431230.20001",
  "ps_name": "推广分析01",
  "success": "true",
  "code": "200",
  "message": "successful"
}
```
**响应参数明细**（7 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 业务数据 |
| `tid` | `string` | ❌ | `E20190312105415047400001` | 有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `dcps` | `string` | ❌ | `213125605561431230.20001` | 推广分析唯一标识符 |
| `ps_name` | `string` | ❌ | `推广分析01` | 推广分析名称 |
| `success` | `boolean` | ❌ | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `integer` | ❌ | `200` | 网关返回码，表示本次请求是否成功。200 :成功。 |
| `message` | `string` | ❌ | `successful` | 网关返回码描述 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.psmanage.get.orderpsinfo/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "tid": "E20190312105415047400001"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.psmanage.get.orderpsinfo/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "tid": "E20190312105415047400001"
}

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