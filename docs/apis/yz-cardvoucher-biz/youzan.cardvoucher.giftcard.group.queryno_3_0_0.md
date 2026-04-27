---
apiName: "youzan.cardvoucher.giftcard.group.queryno.3.0.0"
version: "3.0.0"
status: "待上线"
appName: "yz-cardvoucher-biz"
apiGroup: "gift_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.giftcard.GiftCardRecordService"
method: "queryGroupNoListByOrderNo"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [retail, wsc]
deprecated: false
since: "2019-06-11"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=367"
---
# youzan.cardvoucher.giftcard.group.queryno.3.0.0
> **所属分组**: gift_card　**所属应用**: yz-cardvoucher-biz　**状态**: 待上线
---
## 1. 场景说明
根据订单号查询已经开卡成功的卡号列表
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.group.queryno/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": ""
    },
    "yz_uid": {
      "type": "string",
      "description": "有赞用户ID，在有赞平台账号平台下唯一。user_id，yz_uid，account_id都是账号id（后续会废弃推荐使用yz_open_id）",
      "example": "677009"
    },
    "order_no": {
      "type": "string",
      "description": "有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合",
      "example": "E20190418174101045100001"
    }
  },
  "required": [
    "order_no"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` |  |
| `yz_uid` | `string` | ❌ 否 | `677009` | 有赞用户ID，在有赞平台账号平台下唯一。user_id，yz_uid，account_id都是账号id（后续会废弃推荐使 |
| `order_no` | `string` | ✅ 是 | `E20190418174101045100001` | 有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
---
## 3. 响应
**响应参数 Schema**（6 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "string",
      "description": "卡号",
      "example": "[\"310101052630044\"]"
    },
    "success": {
      "type": "string",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "网关返回码描述",
      "example": "successful"
    },
    "request_id": {
      "type": "string",
      "description": "请求id"
    },
    "error_data": {
      "type": "string",
      "description": "错误数据"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "[\"310101052630044\"]",
  "success": "true",
  "code": "200",
  "message": "successful",
  "request_id": "",
  "error_data": ""
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `string` | ❌ 否 | `["310101052630044"]` | 卡号 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200 :成功。 |
| `message` | `string` | ❌ 否 | `successful` | 网关返回码描述 |
| `request_id` | `string` | ❌ 否 | `` | 请求id |
| `error_data` | `string` | ❌ 否 | `` | 错误数据 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=367

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "order_no": "E20190418174101045100001"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.group.queryno/3.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "order_no": "E20190418174101045100001"
}

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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.giftcard.GiftCardRecordService` |
| 方法名称 | `queryGroupNoListByOrderNo` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=367)_