---
apiName: "youzan.bigdata.psmanage.get.orderpsinfo.1.0.0"
version: "1.0.0"
status: "已上线/变更中"
appName: "seller-datacenter"
apiGroup: "data_center"
serviceName: "com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.ManagePsOder2PsCodeService"
method: "getPsInfoByOrderNo"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [1, wsc, wsc_head, wsc_online, retail, retail_d_partner, retail_head_high, retail_head, retail_online, retail_offline, retail_partner, 1]
deprecated: false
since: "2023-02-19"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3998"
---
# youzan.bigdata.psmanage.get.orderpsinfo.1.0.0
> **所属分组**: data_center　**所属应用**: seller-datacenter　**状态**: 已上线/变更中
---
## 1. 场景说明
通过订单号查询订单所属推广分析信息
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.psmanage.get.orderpsinfo/1.0.0`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
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
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `tid` | `string` | ✅ 是 | `E20190312105415047400001` | 有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
---
## 3. 响应
**响应参数 Schema**（7 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "object",
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
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `object` | ❌ 否 | `` | 业务数据 |
| `tid` | `string` | ❌ 否 | `E20190312105415047400001` | 有赞订单号，E开头+年月日时分秒+随机数，长度24位字母和数字组合 |
| `dcps` | `string` | ❌ 否 | `213125605561431230.20001` | 推广分析唯一标识符 |
| `ps_name` | `string` | ❌ 否 | `推广分析01` | 推广分析名称 |
| `success` | `string` | ❌ 否 | `true` | 表示本次请求是否成功。 true:成功 false：失败 |
| `code` | `string` | ❌ 否 | `200` | 网关返回码，表示本次请求是否成功。200 :成功。 |
| `message` | `string` | ❌ 否 | `successful` | 网关返回码描述 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3998

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{
  "tid": "E20190312105415047400001"
}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.psmanage.get.orderpsinfo/1.0.0"
headers = {
    "Authorization": "Bearer <YOUR_ACCESS_TOKEN>",
    "Content-Type": "application/json"
}
payload = {
  "tid": "E20190312105415047400001"
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
| 服务名称 | `com.youzan.bigdata.datacenter.base.api.service.psmanage.chain.ManagePsOder2PsCodeService` |
| 方法名称 | `getPsInfoByOrderNo` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3998)_