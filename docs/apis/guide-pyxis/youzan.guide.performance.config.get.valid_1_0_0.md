---
apiName: "youzan.guide.performance.config.get.valid.1.0.0"
version: "1.0.0"
appName: "guide-pyxis"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4154"
---

# youzan.guide.performance.config.get.valid.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

外部系统需要推送单据到导购助手进行业绩提成计算之前，需要查询配置，根据配置结果决定是使用导购助手的业绩提成计算接口推送还是在外部系统计算好结果后再调用创建接口推送业绩。
相关接口：
导购外部单据归因：youzan.guide.outer.order.operate.attribute.1.0.0
导购业绩计算：youzan.guide.achievement.operate.calculate.1.0.0
导购业绩明细创建：youzan.guide.achievement.detail.create.1.0.0
导购商品提成计算：youzan.guide.item.commission.operate.calculate.1.0.0
导购商品提成明细创建：youzan.guide.item.commission.detail.create.1.0.0

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.performance.config.get.valid/1.0.0`

**认证方式**: 凭证式

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.performance.config.get.valid/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.performance.config.get.valid/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4154)*