---
apiName: "youzan.salesman.settlemen.manualorders.set.orderstate.1.0.0"
version: "1.0.0"
appName: "java-salesman-web"
apiGroup: "分销与供货"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/1614"
---

# youzan.salesman.settlemen.manualorders.set.orderstate.1.0.0

> **所属分组**: 分销与供货

---

## 1. 场景说明

异步修改待结算人工订单为已结算订单，本接口是订单发起转结算状态的任务入口，一般会返回本次任务成功状态，具体订单的状态变更，需要用户查询销售员结算订单详情才能确认是否变更成功。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.salesman.settlemen.manualorders.set.orderstate/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.salesman.settlemen.manualorders.set.orderstate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.salesman.settlemen.manualorders.set.orderstate/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/1614)*