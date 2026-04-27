---
apiName: "youzan.bigdata.sku.query.getSkuDataInfo.1.0.2"
version: "1.0.2"
appName: "dc-daemon"
apiGroup: "data_center"
method: "getSkuDataInfo"
timeout: "5000"
authType: "凭证式"
type: "HTTP"
deprecated: false
since: "2021-08-30"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3200"
---
# youzan.bigdata.sku.query.getSkuDataInfo.1.0.2
> **所属分组**: data_center　**所属应用**: dc-daemon
---
## 1. 场景说明
根据商品下的每个sku，通过关联hbase表取出在每一天的成交金额和成交数量。用于报表导出，非实时查询。最大支持31天的查询。
---
## 2. 请求
**请求方法**: `POST`
**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.sku.query.getSkuDataInfo/1.0.2`
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
  "required": []
}
```
**请求参数明细**（3 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `item_ids` | `integer` | ❌ | `[557276300,596808495,639125311]` | 商品组id |
| `start_day` | `string` | ❌ | `2021-08-29` | 查询起始yyyy-MM-dd |
| `end_day` | `string` | ❌ | `2021-08-29` | 查询结束yyyy-MM-dd |
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
      "example": "{463552037:[{\\\"goodsId\\\":463552037,\\\"orderPaidItemAmt\\\":100.0,\\\"orderPaidItemNum\\\":4,\\\"skuId\\\":36304357}],591913036:[{\\\"goodsId\\\":591913036,\\\"orderPaidItemAmt\\\":19.8,\\\"orderPaidItemNum\\\":2,\\\"skuId\\\":3"
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
    }
  }
}
```
**成功响应示例**:
```json
{
  "data": [],
  "date_time": "20210816",
  "sku_dim_info": "{463552037:[{\\\"goodsId\\\":463552037,\\\"orderPaidItemAmt\\\":100.0,\\\"orderPaidItemNum\\\":4,\\\"skuId\\\":36304357}],591913036:[{\\\"goodsId\\\":591913036,\\\"orderPaidItemAmt\\\":19.8,\\\"orderPaidItemNum\\\":2,\\\"skuId\\\":3",
  "success": "true",
  "code": "200",
  "message": "参数缺失"
}
```
**响应参数明细**（6 个字段）：

| 参数名 | 类型 | 必填 | 示例 | 说明 |
|--------|------|------|------|------|
| `data` | `array` | ❌ | `` | 返回数据 |
| `date_time` | `integer` | ❌ | `20210816` | 查询指标日期时间（时间格式：yyyyMMdd） |
| `sku_dim_info` | `string` | ❌ | `{463552037:[{\"goodsId\":463552037,\"ord` | skuid的一天的成交金额(元)和成交数量 |
| `success` | `boolean` | ❌ | `true` | 是否成功 true表示成功 false表示失败 |
| `code` | `integer` | ❌ | `200` | 成功失败码 200 表示成功 |
| `message` | `string` | ❌ | `参数缺失` | 成功错误消息 |
---
## 4. cURL / Python 调用示例
```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.sku.query.getSkuDataInfo/1.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{\n  "item_ids": "[557276300,596808495,639125311]",\n  "start_day": "2021-08-29",\n  "end_day": "2021-08-29"\n}'
```

```python
import requests

url = "https://open.youzanyun.com/api/youzan.bigdata.sku.query.getSkuDataInfo/1.0.2"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
payload = {
    "item_ids": "[557276300,596808495,639125311]",
    "start_day": "2021-08-29",
    "end_day": "2021-08-29"
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