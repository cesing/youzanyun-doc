---
apiName: "youzan.bigdata.datacenter.psmanage.update.pagesource.1.0.0"
version: "1.0.0"
appName: "seller-datacenter"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3482"
---

# youzan.bigdata.datacenter.psmanage.update.pagesource.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

更新推广监控名称

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.update.pagesource/1.0.0`

**认证方式**: 凭证式

**请求参数**（2 个）:

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "java.lang.Long",
      "description": "id更新时不能为空",
      "example": "id，推广监控id，可通过<获取推广监控列表>接口获取。"
    },
    "ps_name": {
      "type": "java.lang.String",
      "description": "推广名称创建时不能为空",
      "example": "推广名称"
    }
  },
  "required": [
    "id",
    "ps_name"
  ]
}
```

**响应参数**（9 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.bigdata.datacenter.base.api.model.psmanage.PsPageSourceModel",
      "description": "数据",
      "example": ""
    },
    "id": {
      "type": "java.lang.Long",
      "description": "自增id",
      "example": "1"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "ps_code": {
      "type": "java.lang.String",
      "description": "dcps",
      "example": "111111"
    },
    "ps_name": {
      "type": "java.lang.String",
      "description": "推广名称",
      "example": "推广名称"
    },
    "source_id": {
      "type": "java.lang.Long",
      "description": "推广渠道，ps_sourceid",
      "example": "1"
    },
    "source_name": {
      "type": "java.lang.String",
      "description": "渠道名称",
      "example": "渠道"
    },
    "source_default_tag": {
      "type": "java.lang.Integer",
      "description": "是否默认渠道,0:默认渠道;1:自定义渠道",
      "example": "1"
    },
    "page_info_id": {
      "type": "java.lang.Long",
      "description": "推广页面，ps_page_info主键id",
      "example": "1"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "id": "1",
  "kdt_id": "88888",
  "ps_code": "111111",
  "ps_name": "推广名称",
  "source_id": "1",
  "source_name": "渠道",
  "source_default_tag": "1"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.update.pagesource/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.datacenter.psmanage.update.pagesource/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3482)*