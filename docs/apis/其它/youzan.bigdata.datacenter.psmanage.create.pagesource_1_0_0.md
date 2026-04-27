---
apiName: "youzan.bigdata.datacenter.psmanage.create.pagesource.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3481"
---

# youzan.bigdata.datacenter.psmanage.create.pagesource.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

创建推广分析, 生成可跟踪数据的推广链接，支持连锁模型

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.create.pagesource/1.0.0`

**认证方式**: 凭证式

**请求参数**（9 个）:

```json
{
  "type": "object",
  "properties": {
    "ps_name": {
      "type": "java.lang.String",
      "description": "推广名称创建时不能为空",
      "example": "微信推广名称"
    },
    "source_name": {
      "type": "java.lang.String",
      "description": "推广渠道名称",
      "example": "微信渠道"
    },
    "ps_location": {
      "type": "java.lang.String",
      "description": "推广位置",
      "example": "微信"
    },
    "ps_cost": {
      "type": "java.lang.Long",
      "description": "推广花费",
      "example": "1000"
    },
    "tag_name": {
      "type": "java.lang.String",
      "description": "推广标签名称",
      "example": "微信推广标签"
    },
    "url": {
      "type": "java.lang.String",
      "description": "推广链接",
      "example": "https://shop255245.m.youzan.com/wscgoods/detail/3nsvrpkem6t45"
    },
    "origin": {
      "type": "java.lang.String",
      "description": "推广来源",
      "example": "dc"
    },
    "visit_fans_tag_name": {
      "type": "java.lang.String",
      "description": "访问客户打标签",
      "example": "微信推广客户标签"
    },
    "note": {
      "type": "java.lang.String",
      "description": "备注",
      "example": "备注信息"
    }
  },
  "required": [
    "ps_name",
    "source_name",
    "url"
  ]
}
```

**响应参数**（8 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.base.api.model.psmanage.yun.YunCreatePsResultModel",
      "description": "结果",
      "example": ""
    },
    "id": {
      "type": "java.lang.Long",
      "description": "自增id",
      "example": "7788"
    },
    "dcps": {
      "type": "java.lang.String",
      "description": "dcps",
      "example": "2474438270512040960.200001"
    },
    "ps_name": {
      "type": "java.lang.String",
      "description": "推广名称",
      "example": "测试推广名称"
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
    },
    "request_id": {
      "type": "java.lang.String",
      "description": "调用链",
      "example": "1111"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "id": "7788",
  "dcps": "2474438270512040960.200001",
  "ps_name": "测试推广名称",
  "success": "true",
  "code": "200",
  "message": "参数缺失",
  "request_id": "1111"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.create.pagesource/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.create.pagesource/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3481)*