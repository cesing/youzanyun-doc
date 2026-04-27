---
apiName: "api-test.1.0.1"
version: "1.0.1"
appName: "gateway-test"
apiGroup: "网关测试分组"
method: "invoke"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2020-08-28"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1243"
---
# api-test.1.0.1
> **所属分组**: 网关测试分组　**所属应用**: gateway-test
---
## 1. 场景说明
test
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/api-test/1.0.1`
**请求参数 Schema**（4 个参数）:
```json
{
  "type": "object",
  "properties": {
    "add_test": {
      "type": "string",
      "description": "add_test",
      "example": "demo"
    },
    "count": {
      "type": "integer",
      "description": "返回的item个数",
      "example": "demo"
    },
    "process_time": {
      "type": "integer",
      "description": "模拟业务逻辑处理时间测试",
      "example": "demo"
    },
    "factor": {
      "type": "integer",
      "description": "随机因子，用来随机时间因子最大值为100，当100时，程序每次处理时间都等于processTime当因子小于100时，有百分之因子的概率执行时间等于processTime其他时候立即返回因子最小值为0，为0时processTime不生效",
      "example": "demo"
    }
  },
  "required": []
}
```
**请求参数明细**（4 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `add_test` | `string` | ❌ | `demo` | add_test |
| `count` | `integer` | ❌ | `demo` | 返回的item个数 |
| `process_time` | `integer` | ❌ | `demo` | 模拟业务逻辑处理时间测试 |
| `factor` | `integer` | ❌ | `demo` | 随机因子，用来随机时间因子最大值为100，当100时，程序每次处理时间都等于processTime当因子小于100时，有百分之因子的概率执行时间等于proces |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "paginator": {
      "type": "string",
      "description": "1"
    },
    "page": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "page_size": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "total_count": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "items": {
      "type": "array",
      "description": "1"
    },
    "kdt_id": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "group_id": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "count": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "weight": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    },
    "index": {
      "type": "integer",
      "description": "1",
      "example": "demo"
    }
  }
}
```
**成功响应示例**:
```json
{
  "paginator": "",
  "page": "demo",
  "page_size": "demo",
  "total_count": "demo",
  "items": [],
  "kdt_id": "demo",
  "group_id": "demo",
  "count": "demo"
}
```
**响应参数明细**（10 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `paginator` | `string` | ❌ | `` | 1 |
| `page` | `integer` | ❌ | `demo` | 1 |
| `page_size` | `integer` | ❌ | `demo` | 1 |
| `total_count` | `integer` | ❌ | `demo` | 1 |
| `items` | `array` | ❌ | `` | 1 |
| `kdt_id` | `integer` | ❌ | `demo` | 1 |
| `group_id` | `integer` | ❌ | `demo` | 1 |
| `count` | `integer` | ❌ | `demo` | 1 |
| `weight` | `integer` | ❌ | `demo` | 1 |
| `index` | `integer` | ❌ | `demo` | 1 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/api-test/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "add_test": "demo",\n  "count": "demo",\n  "process_time": "demo",\n  "factor": "demo"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/api-test/1.0.1"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "add_test": "demo",
    "count": "demo",
    "process_time": "demo",
    "factor": "demo"
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