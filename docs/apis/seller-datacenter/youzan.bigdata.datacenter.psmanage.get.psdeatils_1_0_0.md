---
apiName: "youzan.bigdata.datacenter.psmanage.get.psdeatils.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "其它"
method: "getPsDetailData"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3485"
---

# youzan.bigdata.datacenter.psmanage.get.psdeatils.1.0.0

> **所属分组**: 其它  **所属应用**: seller-datacenter

---

## 1. 场景说明

获取单个推广监控数据详情(包含明细和汇总)

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psdeatils/1.0.0`

**请求参数**（7 个）:

```json
{
  "type": "object",
  "properties": {
    "ps_code": {
      "type": "java.lang.String",
      "description": "dcps号",
      "example": "2118722746287589378.200001"
    },
    "attribution_period": {
      "type": "java.lang.Integer",
      "description": "归因周期当天:1,七天:7,15天:15,30天:30@seePsAttributionPeriodEnum",
      "example": "1"
    },
    "statistical_scope": {
      "type": "java.lang.Integer",
      "description": "统计范围全部转化数据：空，推广页直接转化数据：2，连带销售：3@seePsStatisticalScopeTypeEnum",
      "example": "1"
    },
    "attribution_type": {
      "type": "java.lang.Integer",
      "description": "归因方式首次1，末次2@seePsAttributionTypeEnum",
      "example": "1"
    },
    "start_day": {
      "type": "java.lang.String",
      "description": "开始时间yyyy-MM-dd",
      "example": "2021-12-01"
    },
    "end_day": {
      "type": "java.lang.String",
      "description": "结束时间yyyy-MM-dd",
      "example": "2021-12-02"
    },
    "node_kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺。连锁总部查询汇总数据不传该字段",
      "example": "88888"
    }
  },
  "required": [
    "ps_code",
    "attribution_period",
    "attribution_type",
    "start_day",
    "end_day"
  ]
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.base.api.model.psmanage.chain.PsStatisticsDataDTO",
      "description": "结果",
      "example": ""
    },
    "summary_data": {
      "type": "com.youzan.bigdata.datacenter.base.api.model.psmanage.chain.PsStatisticsMeasureDTO",
      "description": "汇总数据这里会给算一遍,实时数据的UV之类要去重，并不是明细数据相加",
      "example": ""
    },
    "time": {
      "type": "java.lang.String",
      "description": "按日期维度的详细数据，如果是今日实时，则小时展示为0,1……,22,23如果是天，则key为2018-01-01",
      "example": "all"
    },
    "pv": {
      "type": "java.lang.Long",
      "description": "浏览量",
      "example": "1"
    },
    "uv": {
      "type": "java.lang.Long",
      "description": "访客数",
      "example": "1"
    },
    "landing_pv": {
      "type": "java.lang.Long",
      "description": "到达浏览量",
      "example": "1"
    },
    "landing_uv": {
      "type": "java.lang.Long",
      "description": "到达访客数",
      "example": "1"
    },
    "new_uv": {
      "type": "java.lang.Long",
      "description": "到达新访客数",
      "example": "1"
    },
    "share_pv": {
      "type": "java.lang.Long",
      "description": "分享浏览量",
      "example": "1"
    },
    "share_uv": {
      "type": "java.lang.Long",
      "description": "分享访客数",
      "example": "1"
    },
    "click_pv": {
      "type": "java.lang.Long",
      "description": "二跳浏览量",
      "example": "1"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "summary_data": "",
  "time": "all",
  "pv": "1",
  "uv": "1",
  "landing_pv": "1",
  "landing_uv": "1",
  "new_uv": "1"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psdeatils/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psdeatils/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3485)*