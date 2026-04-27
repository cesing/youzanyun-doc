---
apiName: "youzan.guide.trial.list.goods.1.0.0"
version: "1.0.0"
appName: "guide-pyxis"
apiGroup: "其它"
method: "listGoodsPaged"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4808"
---

# youzan.guide.trial.list.goods.1.0.0

> **所属分组**: 其它  **所属应用**: guide-pyxis

---

## 1. 场景说明

分页查询导购可以替用户下单的商品接口

返回的商品需满足以下条件：
  1）商品类型为普通实物商品（不包含虚拟商品、群团购等特殊商品类型）
  2）销售状态为“全部在售”或“部分售罄”
  3）商品必须是已上架状态，且未被锁定
  4）商品支持快递发货

针对连锁店铺的处理规则如下：
   1）如果入参店铺id对应的是门店，则返回该门店绑定的网店商品，如果该门店没有绑定网店，则接口会报错
   2）如果入参店铺id对应的是网店，则返回该网店的商品

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.trial.list.goods/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.trial.list.goods/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.trial.list.goods/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4808)*