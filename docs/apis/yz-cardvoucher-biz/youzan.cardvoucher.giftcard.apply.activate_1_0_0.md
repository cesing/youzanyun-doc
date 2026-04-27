---
apiName: "youzan.cardvoucher.giftcard.apply.activate.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "stored_value_card"
serviceName: "com.youzan.pay.cardvoucher.biz.api.open.GiftCardOpenService"
method: "activate"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, retail_head, retail_head_high, retail_online, retail_offline, 1, 1]
deprecated: false
since: "2022-03-14"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3706"
---
# youzan.cardvoucher.giftcard.apply.activate.1.0.0
> **所属分组**: stored_value_card　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
储值礼品卡激活接口，（如实现储值卡激活扩展点https://doc.youzanyun.com/detail/EXT/20001可触发扩展点；如礼品卡已经激活会返回成功）
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.apply.activate/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "yz_open_id": {
      "type": "string",
      "description": "有赞用户id，用户在有赞的唯一id。",
      "example": "Kce872bU658955584007081984"
    },
    "card_alias": {
      "type": "string",
      "description": "礼品卡别名（扩展点场景无需传入）",
      "example": "3XYALEPnOrAxJiB6DMZ"
    },
    "group_no": {
      "type": "string",
      "description": "礼品卡组号",
      "example": "310201391527990"
    }
  },
  "required": [
    "yz_open_id",
    "card_alias",
    "group_no"
  ]
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `yz_open_id` | `string` | ✅ 是 | `Kce872bU658955584007081984` | 有赞用户id，用户在有赞的唯一id。 |
| `card_alias` | `string` | ✅ 是 | `3XYALEPnOrAxJiB6DMZ` | 礼品卡别名（扩展点场景无需传入） |
| `group_no` | `string` | ✅ 是 | `310201391527990` | 礼品卡组号 |
---
## 3. 响应
**响应参数 Schema**（4 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "boolean",
      "description": "是否激活成功",
      "example": "true"
    },
    "success": {
      "type": "string",
      "description": "请求是否成功",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "网关响应码",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "网关响应描述",
      "example": "successful"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "true",
  "success": "true",
  "code": "200",
  "message": "successful"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `boolean` | ❌ 否 | `true` | 是否激活成功 |
| `success` | `string` | ❌ 否 | `true` | 请求是否成功 |
| `code` | `string` | ❌ 否 | `200` | 网关响应码 |
| `message` | `string` | ❌ 否 | `successful` | 网关响应描述 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3706

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "yz_open_id": "Kce872bU658955584007081984",
  "card_alias": "3XYALEPnOrAxJiB6DMZ",
  "group_no": "310201391527990"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.giftcard.apply.activate/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "yz_open_id": "Kce872bU658955584007081984",
  "card_alias": "3XYALEPnOrAxJiB6DMZ",
  "group_no": "310201391527990"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.open.GiftCardOpenService` |
| 方法名称 | `activate` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3706)_