---
apiName: "youzan.guide.summary.operate.repairTag.1.0.0"
version: "1.0.0"
appName: "guide-pyxis"
apiGroup: "其它"
method: "operateSummaryRepair"
timeout: 2000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4336"
---

# youzan.guide.summary.operate.repairTag.1.0.0

> **所属分组**: 其它  **所属应用**: guide-pyxis

---

## 1. 场景说明

面对订单因打通传参问题或定制等问题导致的订单业绩提成错误，修复明细数据后，需要系统自动修复对应的统计数据，通过此接口进行标记，标记完成后会在次日自动修复历史的业绩和提成统计数据。注: 1.使用接口前请先找对应负责人进行开白，否则接口默认无权限；2.调用接口标记前，需要确认所有明细数据均已修复。否则会出现部分明细数据在后续修复，导致统计数据修复时，无法覆盖该部分数据。相关明细修复接口：1. youzan.guide.order.operate.thirdFix.1.0.0；2.youzan.guide.order.operate.fix.1.0.0

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.summary.operate.repairTag/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.summary.operate.repairTag/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.summary.operate.repairTag/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4336)*