---
apiName: "youzan.bigdata.sku.query.getSkuDataInfo.1.0.2"
version: "1.0.2"
status: "已上线/变更中"
appName: "dc-daemon"
apiGroup: "data_center"
serviceName: "com.youzan.bigdata.datacenter.task.api.service.SkuDataExportService"
method: "getSkuDataInfo"
timeout: "5000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, wsc_head, wsc_online, retail_d_partner]
deprecated: false
since: "2021-08-30"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=3200"
---
# youzan.bigdata.sku.query.getSkuDataInfo.1.0.2
> **所属分组**: data_center　**所属应用**: dc-daemon　**状态**: 已上线/变更中
---
## 1. 场景说明
根据商品下的每个sku，通过关联hbase表取出在每一天的成交金额和成交数量。用于报表导出，非实时查询。最大支持31天的查询。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.sku.query.getSkuDataInfo/1.0.2`
**超时时间**: `5000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "item_ids": {
      "type": "integer",
      "description": "商品组id",
      "example": "[557276300,596808495,639125311]"
    },
    "start_day": {
      "type": "string",
      "description": "查询起始yyyy-MM-dd",
      "example": "2021-08-29"
    },
    "end_day": {
      "type": "string",
      "description": "查询结束yyyy-MM-dd",
      "example": "2021-08-29"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `item_ids` | `integer` | ❌ 否 | `[557276300,596808495,639125311` | 商品组id |
| `start_day` | `string` | ❌ 否 | `2021-08-29` | 查询起始yyyy-MM-dd |
| `end_day` | `string` | ❌ 否 | `2021-08-29` | 查询结束yyyy-MM-dd |
---
## 3. 响应
**响应参数 Schema**（6 个字段）:
```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "array",
      "description": "返回数据"
    },
    "date_time": {
      "type": "integer",
      "description": "查询指标日期时间（时间格式：yyyyMMdd）",
      "example": "20210816"
    },
    "sku_dim_info": {
      "type": "string",
      "description": "skuid的一天的成交金额(元)和成交数量",
      "example": "{463552037:[{\\\"goodsId\\\":463552037,\\\"orderPaidItemAmt\\\":100.0,\\\"orderPaidItemNum\\\":4,\\\"skuId\\\":36304357}],591913036:[{\\\"goodsId\\\":591913036,\\\"orderPaidItemAmt\\\":19.8,\\\"orderPaidItemNum\\\":2,\\\"skuId\\\":36556101}]}"
    },
    "success": {
      "type": "string",
      "description": "是否成功 true表示成功 false表示失败",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "成功失败码 200 表示成功",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "成功错误消息",
      "example": "参数缺失"
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "date_time": "20210816",
  "sku_dim_info": "{463552037:[{\\\"goodsId\\\":463552037,\\\"orderPaidItemAmt\\\":100.0,\\\"orderPaidItemNum\\\":4,\\\"skuId\\\":36304357}],591913036:[{\\\"goodsId\\\":591913036,\\\"orderPaidItemAmt\\\":19.8,\\\"orderPaidItemNum\\\":2,\\\"skuId\\\":36556101}]}",
  "success": "true",
  "code": "200",
  "message": "参数缺失"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `data` | `array` | ❌ 否 | `` | 返回数据 |
| `date_time` | `integer` | ❌ 否 | `20210816` | 查询指标日期时间（时间格式：yyyyMMdd） |
| `sku_dim_info` | `string` | ❌ 否 | `{463552037:[{\"goodsId\":46355` | skuid的一天的成交金额(元)和成交数量 |
| `success` | `string` | ❌ 否 | `true` | 是否成功 true表示成功 false表示失败 |
| `code` | `string` | ❌ 否 | `200` | 成功失败码 200 表示成功 |
| `message` | `string` | ❌ 否 | `参数缺失` | 成功错误消息 |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=3200

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.2' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.sku.query.getSkuDataInfo/1.0.2"
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
| 服务名称 | `com.youzan.bigdata.datacenter.task.api.service.SkuDataExportService` |
| 方法名称 | `getSkuDataInfo` |
| 超时时间 | 5000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=3200)_