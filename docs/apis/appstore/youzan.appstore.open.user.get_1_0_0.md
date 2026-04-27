---
apiName: "youzan.appstore.open.user.get.1.0.0"
version: "1.0.0"
status: "已上线"
appName: "appstore"
apiGroup: "open_market"
serviceName: "com.youzan.cloud.appstore.api.service.open.AppstoreUserTokenService"
method: "getInfoByUserToken"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail, beauty, edu_head]
deprecated: false
since: "2019-11-08"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=707"
---
# youzan.appstore.open.user.get.1.0.0
> **所属分组**: open_market　**所属应用**: appstore　**状态**: 已上线
---
## 1. 场景说明
根据”去使用“newUserToken查询员工使用信息，触发场景：当店铺购买应用后，店铺员工点击”去使用“时候触发newUserToken，newUserToken值传入下方请求参数user_token中。该接口access_token调用规则：使用当前应用中下的任意有效access_token即可调用此接口，会校验店铺是否已授权给access_token对应的client_id，校验通过才会响应店铺员工操作人数据。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.user.get/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `user_token` | `string` | ❌ 否 | `1624430821983R2fXmLsws9tjuZdhH` | 请传入点击”去使用“时触发newUserToken值，不是传值access_token的值，请勿传错 |
---
## 3. 响应
**响应参数 Schema**（11 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
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
      "type": "string",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 响应参数 |
| `kdt_id` | `integer` | ❌ 否 | `554134` | 店铺id |
| `app_id` | `integer` | ❌ 否 | `43513` | 应用appid |
| `phone` | `string` | ❌ 否 | `15866666666` | 操作人手机号码 |
| `user_id` | `integer` | ❌ 否 | `3413423` | 购买者身份id（不推荐使用，推荐使用下方yz_open_id） |
| `shop_name` | `string` | ❌ 否 | `测试店铺` | 店铺名称 |
| `shop_type` | `integer` | ❌ 否 | `0` | 店铺类型： 0:微商城/教育店铺 1:微小店 6:美业 7:零售，详细店铺类型区分请使用店铺分组下【youzan.sho |
| `shop_role` | `integer` | ❌ 否 | `1` | 店铺角色： 0:单店 1:总店 2:分店 |
| `yz_open_id` | `string` | ❌ 否 | `LnhGm4rh576452722916618240` | 有赞客户id(推荐使用) |
| `code` | `string` | ❌ 否 | `gdkhrwkgrkgjsdgvjoafoworf` | 店铺授权授权code，工具型应用使用该code获取access_token |
| `success` | `string` | ❌ 否 | `true` | 调用结果 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=707

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.appstore.open.user.get/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {}

response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

> ⚠️ **注意**：以上为示例代码，`access_token` 需要通过 OAuth2.0 流程获取。
> 真实调用地址和参数请以管理后台详情页为准。

---
## 5. 错误码
## 错误码

| 错误码 | 说明 | 处理建议 |
|--------|------|----------|
| 1000 | 系统内部错误 | 稍后重试或联系技术支持 |
| 1001 | 鉴权失败 | 检查 access_token 是否有效 |
| 1002 | 参数校验失败 | 检查必填参数是否完整 |
| 1003 | 权限不足 | 确认应用已开通对应接口权限 |
| 1004 | 频率超限 | 降低请求频率或申请更高配额 |
| 1005 | 资源不存在 | 检查请求的业务 ID 是否正确 |
| 1006 | 请求超时 | 增加超时时间或稍后重试 |
| 1007 | 账户欠费 | 完成账户充值后重试 |

> 更多错误码请参考：[有赞云错误码文档](https://doc.youzanyun.com) |

---
## 6. 内部服务信息
| 字段 | 值 |
|------|---|
| 协议类型 | dubbo |
| 服务名称 | `com.youzan.cloud.appstore.api.service.open.AppstoreUserTokenService` |
| 方法名称 | `getInfoByUserToken` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=707)_