---
apiName: "youzan.bigdata.data.get.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "商品与库存"
method: "query"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1544"
---

# youzan.bigdata.data.get.1.0.0

> **所属分组**: 商品与库存  **所属应用**: seller-datacenter

---

## 1. 场景说明

该接口仅支持在快手直播产生的推广数据，查询时间间隔T+1，建议数据在第二天的10：00之后查询前一天的数据

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.data.get/1.0.0`

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "ad_cps_team_spu_param": {
      "type": "com.youzan.bigdata.datacenter.wsc.api.param.goods.AdCpsTeamSpuParam",
      "description": "入参",
      "example": ""
    },
    "current_day": {
      "type": "java.lang.String",
      "description": "查询日期",
      "example": "2020-11-10"
    },
    "item_id": {
      "type": "java.lang.Long",
      "description": "直播商品id",
      "example": "23333"
    },
    "type": {
      "type": "java.lang.String",
      "description": "渠道类型,默认快手",
      "example": "快手"
    }
  },
  "required": [
    "current_day",
    "item_id"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.wsc.api.model.goods.AdCpsTeamSpuModel",
      "description": "直播数据",
      "example": ""
    },
    "trade_num": {
      "type": "java.lang.Long",
      "description": "支付人数",
      "example": "12"
    },
    "trade_count": {
      "type": "java.lang.Long",
      "description": "支付笔数",
      "example": "121"
    },
    "trade_amount": {
      "type": "java.lang.Long",
      "description": "支付金额（分）",
      "example": "2"
    },
    "pay_num": {
      "type": "java.lang.Long",
      "description": "下单人数",
      "example": "12"
    },
    "pay_count": {
      "type": "java.lang.Long",
      "description": "下单笔数",
      "example": "12"
    },
    "pay_amount": {
      "type": "java.lang.Long",
      "description": "下单金额（分）",
      "example": "12"
    },
    "pv": {
      "type": "java.lang.Long",
      "description": "浏览量",
      "example": "12"
    },
    "uv": {
      "type": "java.lang.Long",
      "description": "访客数",
      "example": "12"
    },
    "success": {
      "type": "boolean",
      "description": "成功与否",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "返回码",
      "example": "200"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "trade_num": "12",
  "trade_count": "121",
  "trade_amount": "2",
  "pay_num": "12",
  "pay_count": "12",
  "pay_amount": "12",
  "pv": "12"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.data.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.data.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1544)*