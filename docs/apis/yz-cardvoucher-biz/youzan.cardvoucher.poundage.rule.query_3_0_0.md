---
apiName: "youzan.cardvoucher.poundage.rule.query.3.0.0"
version: "3.0.0"
status: "已上线/变更中"
appName: "yz-cardvoucher-biz"
apiGroup: "retail_valuecard"
serviceName: "com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundOpenService"
method: "queryPoundageRule"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner, retail]
deprecated: false
since: "2021-07-15"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3057"
---
# youzan.cardvoucher.poundage.rule.query.3.0.0
> **所属分组**: retail_valuecard　**所属应用**: yz-cardvoucher-biz　**状态**: 已上线/变更中
---
## 1. 场景说明
储值卡退卡手续费规则查询，调用储值卡退卡申请API前置调用，用于计算退卡手续费
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.poundage.rule.query/3.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（0 个参数）:
```json
{
  "type": "object",
  "properties": {},
  "required": null
}
```
**请求参数明细**  （详情页暂无数据）

无结构化参数信息
---
## 3. 响应
**响应参数 Schema**（9 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
      "description": "返回参数"
    },
    "scenes": {
      "type": "string",
      "description": "场景，RECEDE_CARD:退卡",
      "example": "RECEDE_CARD"
    },
    "type": {
      "type": "string",
      "description": "类型：FIX:固定手续费，PERCENT:百分比",
      "example": "PERCENT"
    },
    "poundage_value": {
      "type": "integer",
      "description": "手续费金额，type为FIX：则为具体金额,单位为分； type为PERCENT：返回值范围0~10000，单位：万分比 例如返回值为10即表示手续费比例是0.1%",
      "example": "1"
    },
    "format_poundage_value": {
      "type": "string",
      "description": "手续费金额，数值为保留2位小数后的格式化字符串，可以直接用于展示",
      "example": "0.01"
    },
    "limit_value": {
      "type": "integer",
      "description": "手续费门槛金额，退卡金额高于门槛金额，按上述规则收取手续费，单位为分",
      "example": "10"
    },
    "success": {
      "type": "string",
      "description": "处理结果",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "处理结果状态码",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "处理结果提示",
      "example": "执行成功"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": "",
  "scenes": "RECEDE_CARD",
  "type": "PERCENT",
  "poundage_value": "1",
  "format_poundage_value": "0.01",
  "limit_value": "10",
  "success": "true",
  "code": "200"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 返回参数 |
| `scenes` | `string` | ❌ 否 | `RECEDE_CARD` | 场景，RECEDE_CARD:退卡 |
| `type` | `string` | ❌ 否 | `PERCENT` | 类型：FIX:固定手续费，PERCENT:百分比 |
| `poundage_value` | `integer` | ❌ 否 | `1` | 手续费金额，type为FIX：则为具体金额,单位为分； type为PERCENT：返回值范围0~10000，单位：万分比 |
| `format_poundage_value` | `string` | ❌ 否 | `0.01` | 手续费金额，数值为保留2位小数后的格式化字符串，可以直接用于展示 |
| `limit_value` | `integer` | ❌ 否 | `10` | 手续费门槛金额，退卡金额高于门槛金额，按上述规则收取手续费，单位为分 |
| `success` | `string` | ❌ 否 | `true` | 处理结果 |
| `code` | `string` | ❌ 否 | `200` | 处理结果状态码 |
| `message` | `string` | ❌ 否 | `执行成功` | 处理结果提示 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3057

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/3.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.cardvoucher.poundage.rule.query/3.0.0"
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
| 服务名称 | `com.youzan.pay.cardvoucher.biz.api.valuecard.ValueCardFundOpenService` |
| 方法名称 | `queryPoundageRule` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3057)_