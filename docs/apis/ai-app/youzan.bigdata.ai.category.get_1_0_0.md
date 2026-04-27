---
apiName: "youzan.bigdata.ai.category.get.1.0.0"
version: "1.0.0"
status: "待上线"
appName: "ai-app"
apiGroup: "item_category"
serviceName: "com.youzan.ai.app.api.service.category.RetrieveService"
method: "retrieveBifrost"
timeout: "2000"
protocol: "dubbo"
authType: "需要Token"
type: "查询/写入"
kdtTypes: [wsc, retail, wsc_head, wsc_online, retail_d_partner, retail_front_warehouse, retail_head, retail_head_high, retail_online, retail_online_lite, retail_offlineretail_partner, retail_supplier, retail_single_warehouse, beauty, edu, edu_headedu_branch, hotel]
deprecated: false
since: "2020-06-19"
detailUrl: "https://gateway.qima-inc.com/api-manager/detail?id=1048"
---
# youzan.bigdata.ai.category.get.1.0.0
> **所属分组**: item_category　**所属应用**: ai-app　**状态**: 待上线
---
## 1. 场景说明
场景：商家可传入商品标题/描述，店铺名称调用接口，接口会根据上述条件生成对应的商品类目推荐。例如：输入”iPhone XS Max 64G “  就会返回”{"rule_id":"10050012""category_chain_list":[0:"数码办公"1:"手机"]"percent":1}” rule_id：类目id，category_chain_list：推荐类目分类，percent：分类准确度为1 推荐使用。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.ai.category.get/1.0.0`
**超时时间**: `2000ms`
**鉴权方式**: `需要Token`
**请求参数 Schema**（3 个参数）:
```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "object",
      "description": "请求体"
    },
    "query": {
      "type": "string",
      "description": "待分类文本，最大支持传值80个字符",
      "example": "小碎花连衣裙"
    },
    "shop_name": {
      "type": "string",
      "description": "店铺名，如传值可提升分类准确性",
      "example": "苗苗母婴店"
    }
  },
  "required": null
}
```
**请求参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `request` | `object` | ❌ 否 | `` | 请求体 |
| `query` | `string` | ❌ 否 | `小碎花连衣裙` | 待分类文本，最大支持传值80个字符 |
| `shop_name` | `string` | ❌ 否 | `苗苗母婴店` | 店铺名，如传值可提升分类准确性 |
---
## 3. 响应
**响应参数 Schema**（10 个字段）:
```json
{
  "type": "object",
  "properties": {
    "success": {
      "type": "string",
      "description": "是否成功",
      "example": "true"
    },
    "code": {
      "type": "string",
      "description": "code",
      "example": "200"
    },
    "message": {
      "type": "string",
      "description": "信息",
      "example": "successful"
    },
    "request_id": {
      "type": "string",
      "description": "已废弃",
      "example": "已废弃"
    },
    "error_data": {
      "type": "string",
      "description": "已废弃",
      "example": "已废弃"
    },
    "data": {
      "type": "array",
      "description": "响应参数"
    },
    "category_chain_list": {
      "type": "string",
      "description": "类目名称",
      "example": "[\"服装鞋包\",\"女装/女士精品\",\"连衣裙\"]"
    },
    "percent": {
      "type": "number",
      "description": "分类置信度，最大保留小数点后三位，1~0.900：可以使用，0.899~0.700：推荐使用，0.699~0：不推荐使用",
      "example": "1.0"
    },
    "rule_id": {
      "type": "string",
      "description": "类目规则ID",
      "example": "100400060015"
    },
    "category_id": {
      "type": "integer",
      "description": "类目id",
      "example": "3949"
    }
  }
}
```
**成功响应示例**:
```json
{
  "success": "true",
  "code": "200",
  "message": "successful",
  "request_id": "已废弃",
  "error_data": "已废弃",
  "data": [],
  "category_chain_list": "[\"服装鞋包\",\"女装/女士精品\",\"连衣裙\"]",
  "percent": "1.0"
}
```
**响应参数明细**

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| `success` | `string` | ❌ 否 | `true` | 是否成功 |
| `code` | `string` | ❌ 否 | `200` | code |
| `message` | `string` | ❌ 否 | `successful` | 信息 |
| `request_id` | `string` | ❌ 否 | `已废弃` | 已废弃 |
| `error_data` | `string` | ❌ 否 | `已废弃` | 已废弃 |
| `data` | `array` | ❌ 否 | `` | 响应参数 |
| `category_chain_list` | `string` | ❌ 否 | `["服装鞋包","女装/女士精品","连衣裙"]` | 类目名称 |
| `percent` | `number` | ❌ 否 | `1.0` | 分类置信度，最大保留小数点后三位，1~0.900：可以使用，0.899~0.700：推荐使用，0.699~0：不推荐使用 |
| `rule_id` | `string` | ❌ 否 | `100400060015` | 类目规则ID |
| `category_id` | `integer` | ❌ 否 | `3949` | 类目id |
---
## 4. cURL / Python 调用示例
```bash
# 有赞云 API 调用示例
# 有赞云地址: https://open.youzanyun.com
# 文档地址: https://gateway.qima-inc.com/api-manager/detail?id=1048

curl -X POST 'https://open.youzanyun.com/api/youzan.skinfo/1.0.0' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.ai.category.get/1.0.0"
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
| 服务名称 | `com.youzan.ai.app.api.service.category.RetrieveService` |
| 方法名称 | `retrieveBifrost` |
| 超时时间 | 2000ms |
---
## 8. 关联接口
*（暂无关联数据，文档完善后将补充相关接口）*
---
_本文档由 AI 自动生成，源数据来自 [有赞云开放平台详情页](https://gateway.qima-inc.com/api-manager/detail?id=1048)_