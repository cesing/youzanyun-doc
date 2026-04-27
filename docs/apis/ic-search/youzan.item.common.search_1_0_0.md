---
apiName: "youzan.item.common.search.1.0.0"
version: "1.0.0"
appName: "ic-search"
apiGroup: "商品与库存"
method: "list"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3561"
---

# youzan.item.common.search.1.0.0

> **所属分组**: 商品与库存  **所属应用**: ic-search

---

## 1. 场景说明

1、默认根据创建时间倒序返回数据；
2、search_after查询方式，不限制查询总数，需要配合page_size使用；
3、page_no和page_size最大支持查询5000条数据；
4、零售连锁店铺查询结果是账号下所有的门店和网店商品总和，非商品库商品总和；
5、所有List请求参数，最大支持传值20条；
6、不支持查询商品库商品；

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.item.common.search/1.0.0`

**请求参数**（0 个）:

```json
{
  "type": "object",
  "properties": {},
  "required": []
}
```

**响应参数**（0 个）:

```json
{
  "type": "object",
  "properties": {}
}
```

**成功响应示例**:

```json
{}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.item.common.search/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.item.common.search/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3561)*