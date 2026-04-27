---
apiName: "youzan.bigdata.sku.query.getSkuDataInfo.1.0.2"
version: "1.0.2"
appName: "dc-daemon"
apiGroup: "数据分析"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3200"
---

# youzan.bigdata.sku.query.getSkuDataInfo.1.0.2

> **所属分组**: 数据分析

---

## 1. 场景说明

根据商品下的每个sku，通过关联hbase表取出在每一天的成交金额和成交数量。用于报表导出，非实时查询。最大支持31天的查询。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.sku.query.getSkuDataInfo/1.0.2`

**认证方式**: 凭证式

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "item_ids": {
      "type": "java.util.List<java.lang.Long>",
      "description": "商品组id",
      "example": "[557276300,596808495,639125311]"
    },
    "start_day": {
      "type": "java.lang.String",
      "description": "查询起始yyyy-MM-dd",
      "example": "2021-08-29"
    },
    "end_day": {
      "type": "java.lang.String",
      "description": "查询结束yyyy-MM-dd",
      "example": "2021-08-29"
    }
  },
  "required": []
}
```

**响应参数**（6 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.util.List<com.youzan.bigdata.datacenter.task.api.dto.GoodSkuDataDTO>",
      "description": "返回数据",
      "example": ""
    },
    "date_time": {
      "type": "java.lang.Integer",
      "description": "查询指标日期时间（时间格式：yyyyMMdd）",
      "example": "20210816"
    },
    "sku_dim_info": {
      "type": "java.lang.String",
      "description": "skuid的一天的成交金额(元)和成交数量",
      "example": "{463552037:[{\\\"goodsId\\\":463552037,\\\"orderPaidItemAmt\\\":100.0,\\\"orderPaidItemNum\\\":4,\\\"skuId\\\":36304357}],591913036:[{\\\"goodsId\\\":591913036,\\\"orderPaidItemAmt\\\":19.8,\\\"orderPaidItemNum\\\":2,\\\"skuId\\\":36556101}]}"
    },
    "success": {
      "type": "boolean",
      "description": "是否成功 true表示成功 false表示失败",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "成功失败码 200 表示成功",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "成功错误消息",
      "example": "参数缺失"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "date_time": "20210816",
  "sku_dim_info": "{463552037:[{\\\"goodsId\\\":463552037,\\\"orderPaidItemAmt\\\":100.0,\\\"orderPaidItemNum\\\":4,\\\"skuId\\\":36304357}],591913036:[{\\\"goodsId\\\":591913036,\\\"orderPaidItemAmt\\\":19.8,\\\"orderPaidItemNum\\\":2,\\\"skuId\\\":36556101}]}",
  "success": "true",
  "code": "200",
  "message": "参数缺失"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.sku.query.getSkuDataInfo/1.0.2' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.sku.query.getSkuDataInfo/1.0.2"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3200)*