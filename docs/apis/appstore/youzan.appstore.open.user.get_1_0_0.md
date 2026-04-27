---
apiName: "youzan.appstore.open.user.get.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "open_market"
method: "getInfoByUserToken"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2019-11-08"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/707"
---
# youzan.appstore.open.user.get.1.0.0
> **所属分组**: open_market　**所属应用**: appstore
---
## 1. 场景说明
根据”去使用“newUserToken查询员工使用信息，触发场景：当店铺购买应用后，店铺员工点击”去使用“时候触发newUserToken，newUserToken值传入下方请求参数user_token中。该接口access_token调用规则：使用当前应用中下的任意有效access_token即可调用此接口，会校验店铺是否已授权给access_token对应的client_id，校验通过才会响应店铺员工操作人数据。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.user.get/1.0.0`
**请求参数 Schema**（1 个参数）:
```json
{
  "type": "object",
  "properties": {
    "user_token": {
      "type": "string",
      "description": "请传入点击”去使用“时触发newUserToken值，不是传值access_token的值，请勿传错",
      "example": "1624430821983R2fXmLsws9tjuZdhHFSfZ6xS#/user/login"
    }
  },
  "required": []
}
```
**请求参数明细**（1 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `user_token` | `string` | ❌ | `1624430821983R2fXmLsws9tjuZdhHFSfZ6xS#/u` | 请传入点击”去使用“时触发newUserToken值，不是传值access_token的值，请勿传错 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "响应参数"
    },
    "kdt_id": {
      "type": "integer",
      "description": "店铺id",
      "example": "554134"
    },
    "app_id": {
      "type": "integer",
      "description": "应用appid",
      "example": "43513"
    },
    "phone": {
      "type": "string",
      "description": "操作人手机号码",
      "example": "15866666666"
    },
    "user_id": {
      "type": "integer",
      "description": "购买者身份id（不推荐使用，推荐使用下方yz_open_id）",
      "example": "3413423"
    },
    "shop_name": {
      "type": "string",
      "description": "店铺名称",
      "example": "测试店铺"
    },
    "shop_type": {
      "type": "integer",
      "description": "店铺类型： 0:微商城/教育店铺 1:微小店 6:美业 7:零售，详细店铺类型区分请使用店铺分组下【youzan.shop.basic.get.3.0.0】接口查询",
      "example": "0"
    },
    "shop_role": {
      "type": "integer",
      "description": "店铺角色： 0:单店 1:总店 2:分店",
      "example": "1"
    },
    "yz_open_id": {
      "type": "string",
      "description": "有赞客户id(推荐使用)",
      "example": "LnhGm4rh576452722916618240"
    },
    "code": {
      "type": "string",
      "description": "店铺授权授权code，工具型应用使用该code获取access_token",
      "example": "gdkhrwkgrkgjsdgvjoafoworf"
    },
    "success": {
      "type": "boolean",
      "description": "调用结果",
      "example": "true"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "kdt_id": "554134",
  "app_id": "43513",
  "phone": "15866666666",
  "user_id": "3413423",
  "shop_name": "测试店铺",
  "shop_type": "0",
  "shop_role": "1"
}
```
**响应参数明细**（11 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `string` | ❌ | `` | 响应参数 |
| `kdt_id` | `integer` | ❌ | `554134` | 店铺id |
| `app_id` | `integer` | ❌ | `43513` | 应用appid |
| `phone` | `string` | ❌ | `15866666666` | 操作人手机号码 |
| `user_id` | `integer` | ❌ | `3413423` | 购买者身份id（不推荐使用，推荐使用下方yz_open_id） |
| `shop_name` | `string` | ❌ | `测试店铺` | 店铺名称 |
| `shop_type` | `integer` | ❌ | `0` | 店铺类型： 0:微商城/教育店铺 1:微小店 6:美业 7:零售，详细店铺类型区分请使用店铺分组下【youzan.shop.basic.get.3.0.0】接口 |
| `shop_role` | `integer` | ❌ | `1` | 店铺角色： 0:单店 1:总店 2:分店 |
| `yz_open_id` | `string` | ❌ | `LnhGm4rh576452722916618240` | 有赞客户id(推荐使用) |
| `code` | `string` | ❌ | `gdkhrwkgrkgjsdgvjoafoworf` | 店铺授权授权code，工具型应用使用该code获取access_token |
| `success` | `boolean` | ❌ | `true` | 调用结果 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.open.user.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "user_token": "1624430821983R2fXmLsws9tjuZdhHFSfZ6xS#/user/login"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.user.get/1.0.0"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "user_token": "1624430821983R2fXmLsws9tjuZdhHFSfZ6xS#/user/login"
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