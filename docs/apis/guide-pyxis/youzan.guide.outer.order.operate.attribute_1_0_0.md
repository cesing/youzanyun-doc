---
apiName: "youzan.guide.outer.order.operate.attribute.1.0.0"
version: "1.0.0"
appName: "guide-pyxis"
apiGroup: "其它"
method: "triggerAttributeWithOuterOrder"
timeout: 3000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4157"
---

# youzan.guide.outer.order.operate.attribute.1.0.0

> **所属分组**: 其它  **所属应用**: guide-pyxis

---

## 1. 场景说明

外部系统需要推送单据到导购助手进行业绩提成计算之前，需要通过本接口进行归因，记录业绩提成所需的基本快照数据，然后再进行业绩和提成的计算。
调用接口前需要先查询业绩通用配置，判断当前单据是否使用有赞业绩提成规则，如果不是，则不能使用本接口。
相关接口：
导购业绩计算：youzan.guide.achievement.operate.calculate.1.0.0
导购业绩明细创建：youzan.guide.achievement.detail.create.1.0.0
导购商品提成计算：youzan.guide.item.commission.operate.calculate.1.0.0
导购商品提成明细创建：youzan.guide.item.commission.detail.create.1.0.0

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.outer.order.operate.attribute/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.outer.order.operate.attribute/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.outer.order.operate.attribute/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4157)*