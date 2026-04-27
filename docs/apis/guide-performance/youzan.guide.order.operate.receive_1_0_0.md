---
apiName: "youzan.guide.order.operate.receive.1.0.0"
version: "1.0.0"
appName: "guide-performance"
apiGroup: "其它"
method: "receiveOrder"
timeout: 3000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4220"
---

# youzan.guide.order.operate.receive.1.0.0

> **所属分组**: 其它  **所属应用**: guide-performance

---

## 1. 场景说明

当商家有一种类型的单据，无法转化为有赞交易中心的单据模型，但是又需要在导购助手插件中做数据统计或业绩提成计算的，可以通过此接口推送单据到导购助手。同时为了保证对应单据信息在导购助手的单据列表和详情页能够完整展示，需要同步实现扩展点 ”com.youzan.cloud.extension.api.guide.ListOuterOrderInfos“。
接口支持同一个单据重复调用，重复调用注意事项如下：
1. 当前接口支持同一个单据重复推送，但是每次推送的单据信息必须是一致的，从第二次推送开始，每次推送会基于第一次推送的信息对后续推动的内容做校验，如果推送的单据信息不一致，则拒绝推送请求，此处的单据信息校验不包含业务操作字段operate。
2. 业绩和提成的计算仅执行一次，如果多次推送标记计算业绩或提成，则以第一次推送时计算的结果为准。
当前可接入单据：无原单退款单(biz_type=3, system_from=2)；
当前版本已废弃，新接入的商家请对接接口 youzan.crm.out.order.create.2.0.0

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.order.operate.receive/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.order.operate.receive/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.order.operate.receive/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4220)*