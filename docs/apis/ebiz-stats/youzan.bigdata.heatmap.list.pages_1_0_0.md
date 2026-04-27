---
apiName: "youzan.bigdata.heatmap.list.pages.1.0.0"
version: "1.0.0"
appName: "ebiz-stats"
apiGroup: "数据分析"
method: "getPages"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4075"
---

# youzan.bigdata.heatmap.list.pages.1.0.0

> **所属分组**: 数据分析  **所属应用**: ebiz-stats

---

## 1. 场景说明

获取热力图页面列表,分页方式获取页面列表。支持页面模糊搜索和页面类型的筛选。返回的id为热力图id，后续查询页面统计信息时传递上述id进行查询。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.bigdata.heatmap.list.pages/1.0.0`

**请求参数**（4 个）:

```json
{
  "type": "object",
  "properties": {
    "page_type": {
      "type": "java.lang.String",
      "description": "热力图页面类型。微页面：f，商详页g，不传查全部",
      "example": "f"
    },
    "page_name": {
      "type": "java.lang.String",
      "description": "热力图页面名称模糊搜索",
      "example": "主页"
    },
    "page_no": {
      "type": "java.lang.Integer",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "java.lang.Integer",
      "description": "每页大小",
      "example": "10"
    }
  },
  "required": []
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "com.youzan.api.common.vo.ListWithPaginatorVO<T>",
      "description": "结果",
      "example": ""
    },
    "paginator": {
      "type": "com.youzan.api.common.response.Paginator",
      "description": "分页结果",
      "example": ""
    },
    "page_no": {
      "type": "int",
      "description": "页码",
      "example": "1"
    },
    "page_size": {
      "type": "int",
      "description": "每页大小",
      "example": "10"
    },
    "total_count": {
      "type": "int",
      "description": "总数",
      "example": "15"
    },
    "items": {
      "type": "java.util.List<com.youzan.ebiz.stats.domain.heatmap.PageBO>",
      "description": "热力图页面信息列表",
      "example": ""
    },
    "id": {
      "type": "java.lang.Long",
      "description": "热力图id，查询热力图统计数据时使用",
      "example": "1"
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "88888"
    },
    "page_id": {
      "type": "java.lang.Long",
      "description": "商品或者微页面id",
      "example": "123"
    },
    "page_alias": {
      "type": "java.lang.String",
      "description": "商品或者微页面别名",
      "example": "ffff"
    },
    "page_name": {
      "type": "java.lang.String",
      "description": "商品或者微页面名称",
      "example": "主页面"
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
  "page_size": "10",
  "total_count": "15",
  "items": "",
  "id": "1",
  "kdt_id": "88888"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.bigdata.heatmap.list.pages/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.bigdata.heatmap.list.pages/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4075)*