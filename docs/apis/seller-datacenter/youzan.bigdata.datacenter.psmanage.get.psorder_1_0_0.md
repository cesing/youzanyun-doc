---
apiName: "youzan.bigdata.datacenter.psmanage.get.psorder.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3486"
---

# youzan.bigdata.datacenter.psmanage.get.psorder.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

按天获取某个推广分析下的订单，仅支持离线，不支持今日实时

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psorder/1.0.0`

**认证方式**: 凭证式

**请求参数**（8 个）:

```json
{
  "type": "object",
  "properties": {
    "attribution_period": {
      "type": "java.lang.Integer",
      "description": "归因周期。当天:1,七天:7,15天:15,30天:30",
      "example": "1"
    },
    "statistical_scope": {
      "type": "java.lang.Integer",
      "description": "统计范围 。 全部转化数据：不传、 推广页直接转化数据：2、连带销售：3",
      "example": "1"
    },
    "attribution_type": {
      "type": "java.lang.Integer",
      "description": "归因方式 。 首次1、末次2",
      "example": "1"
    },
    "dcps": {
      "type": "java.lang.String",
      "description": "推广监控标识",
      "example": "2956668732916707328.200001"
    },
    "current_day": {
      "type": "java.lang.Integer",
      "description": "导出日期",
      "example": "20211201"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "有赞用户id，用户在有赞的唯一id。推荐使用店铺管理员id",
      "example": "LnhGm4rh576452722916618240"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "每页条数。默认100条",
      "example": "100"
    }
  },
  "required": [
    "attribution_period",
    "attribution_type",
    "dcps",
    "current_day",
    "yz_open_id",
    "page_no",
    "page_size"
  ]
}
```

**响应参数**（9 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.api.common.vo.ListWithPaginatorVO<T>",
      "description": "返回结果",
      "example": ""
    },
    "paginator": {
      "type": "com.youzan.api.common.response.Paginator",
      "description": "分页结果信息",
      "example": ""
    },
    "page_no": {
      "type": "int",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "int",
      "description": "条数",
      "example": "100"
    },
    "total_count": {
      "type": "int",
      "description": "分页查询的总条数",
      "example": "1000"
    },
    "items": {
      "type": "java.util.List<java.lang.String>",
      "description": "订单集合",
      "example": "['E10001','E1002']"
    },
    "success": {
      "type": "boolean",
      "description": "表示本次请求是否成功。 true:成功 false：失败",
      "example": "true"
    },
    "code": {
      "type": "int",
      "description": "网关返回码，表示本次请求是否成功。200 :成功。",
      "example": "200"
    },
    "message": {
      "type": "java.lang.String",
      "description": "网关返回码描述",
      "example": "参数缺失"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "paginator": "",
  "page_no": "1",
  "page_size": "100",
  "total_count": "1000",
  "items": "['E10001','E1002']",
  "success": "true",
  "code": "200"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psorder/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.get.psorder/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3486)*