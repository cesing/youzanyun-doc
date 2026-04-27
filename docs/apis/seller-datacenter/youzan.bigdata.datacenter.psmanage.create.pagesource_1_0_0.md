---
apiName: "youzan.bigdata.datacenter.psmanage.create.pagesource.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "extension_analysis"
method: "createPageSource"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-12-14"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3481"
---
# youzan.bigdata.datacenter.psmanage.create.pagesource.1.0.0
> **所属分组**: extension_analysis　**所属应用**: seller-datacenter
---
## 1. 场景说明
创建推广分析, 生成可跟踪数据的推广链接，支持连锁模型
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.create.pagesource/1.0.0`
**请求参数 Schema**（9 个参数）:
```json
{
  "type": "object",
  "properties": {
    "ps_name": {
      "type": "string",
      "description": "推广名称创建时不能为空",
      "example": "微信推广名称"
    },
    "source_name": {
      "type": "string",
      "description": "推广渠道名称",
      "example": "微信渠道"
    },
    "ps_location": {
      "type": "string",
      "description": "推广位置",
      "example": "微信"
    },
    "ps_cost": {
      "type": "integer",
      "description": "推广花费",
      "example": "1000"
    },
    "tag_name": {
      "type": "string",
      "description": "推广标签名称",
      "example": "微信推广标签"
    },
    "url": {
      "type": "string",
      "description": "推广链接",
      "example": "https://shop255245.m.youzan.com/wscgoods/detail/3nsvrpkem6t45"
    },
    "origin": {
      "type": "string",
      "description": "推广来源",
      "example": "dc"
    },
    "visit_fans_tag_name": {
      "type": "string",
      "description": "访问客户打标签",
      "example": "微信推广客户标签"
    },
    "note": {
      "type": "string",
      "description": "备注",
      "example": "备注信息"
    }
  },
  "required": [
    "ps_name",
    "source_name",
    "url"
  ]
}
```
**请求参数明细**（9 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `ps_name` | `string` | ✅ | `微信推广名称` | 推广名称创建时不能为空 |
| `source_name` | `string` | ✅ | `微信渠道` | 推广渠道名称 |
| `ps_location` | `string` | ❌ | `微信` | 推广位置 |
| `ps_cost` | `integer` | ❌ | `1000` | 推广花费 |
| `tag_name` | `string` | ❌ | `微信推广标签` | 推广标签名称 |
| `url` | `string` | ✅ | `https://shop255245.m.youzan.com/wscgoods` | 推广链接 |
| `origin` | `string` | ❌ | `dc` | 推广来源 |
| `visit_fans_tag_name` | `string` | ❌ | `微信推广客户标签` | 访问客户打标签 |
| `note` | `string` | ❌ | `备注信息` | 备注 |
---
## 3. 响应
**响应参数 Schema**（8 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "结果"
    },
    "id": {
      "type": "integer",
      "description": "自增id",
      "example": "7788"
    },
    "dcps": {
      "type": "string",
      "description": "dcps",
      "example": "2474438270512040960.200001"
    },
    "ps_name": {
      "type": "string",
      "description": "推广名称",
      "example": "测试推广名称"
    },
    "success": {
      "type": "boolean",
      "description": "是否成功 true表示成功 false表示失败",
      "example": "true"
    },
    "code": {
      "type": "integer",
      "description": "成功失败码 200 表示成功",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "成功错误消息",
      "example": "参数缺失"
    },
    "request_id": {
      "type": "string",
      "description": "调用链",
      "example": "1111"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "id": "7788",
  "dcps": "2474438270512040960.200001",
  "ps_name": "测试推广名称",
  "success": "true",
  "code": "200",
  "message": "参数缺失",
  "request_id": "1111"
}
```
**响应参数明细**（8 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 结果 |
| `id` | `integer` | ❌ | `7788` | 自增id |
| `dcps` | `string` | ❌ | `2474438270512040960.200001` | dcps |
| `ps_name` | `string` | ❌ | `测试推广名称` | 推广名称 |
| `success` | `boolean` | ❌ | `true` | 是否成功 true表示成功 false表示失败 |
| `code` | `integer` | ❌ | `200` | 成功失败码 200 表示成功 |
| `message` | `string` | ❌ | `参数缺失` | 成功错误消息 |
| `request_id` | `string` | ❌ | `1111` | 调用链 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.create.pagesource/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "ps_name": "微信推广名称",\n  "source_name": "微信渠道",\n  "ps_location": "微信",\n  "ps_cost": "1000",\n  "tag_name": "微信推广标签",\n  "url": "https://shop255245.m.youzan.com/wscgoods/detail/3nsvrpkem6t45",\n  "origin": "dc",\n  "visit_fans_tag_name": "微信推广客户标签",\n  "note": "备注信息"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.create.pagesource/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "ps_name": "微信推广名称",
    "source_name": "微信渠道",
    "ps_location": "微信",
    "ps_cost": "1000",
    "tag_name": "微信推广标签",
    "url": "https://shop255245.m.youzan.com/wscgoods/detail/3nsvrpkem6t45",
    "origin": "dc",
    "visit_fans_tag_name": "微信推广客户标签",
    "note": "备注信息"
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