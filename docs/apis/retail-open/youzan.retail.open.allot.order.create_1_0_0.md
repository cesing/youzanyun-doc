---
apiName: "youzan.retail.open.allot.order.create.1.0.0"
version: "1.0.0"
appName: "retail-open"
apiGroup: "零售门店"
method: "createAllotOrder"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3299"
---

# youzan.retail.open.allot.order.create.1.0.0

> **所属分组**: 零售门店  **所属应用**: retail-open

---

## 1. 场景说明

调拨单创建，支持在零售单店、零售连锁总部/门店创建。主要功能用于创建调拨单，将货品库存从一个仓库/门店调拨到另一个仓库/门店。调拨单创建之后，通过出库接口（youzan.retail.open.stockoutorder.create.3.0.0）将货品从仓库/门店调拨出库，再通过入库接口（youzan.retail.open.stockinorder.create.3.0.0）将货品从仓库/门店调拨入库，至此整个调拨作业流程完成。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.retail.open.allot.order.create/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.retail.open.allot.order.create/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.retail.open.allot.order.create/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3299)*