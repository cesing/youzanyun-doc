---
apiName: "youzan.logistics.waybill.apply.1.0.0"
version: "1.0.0"
appName: "delivery"
apiGroup: "物流配送"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4244"
---

# youzan.logistics.waybill.apply.1.0.0

> **所属分组**: 物流配送

---

## 1. 场景说明

电子面单批量取号，支持有赞订单或者非有赞订单取号(非有赞订单仅支持使用有赞寄件取号)。
1、批内取号数量上限为10。
2、允许部分取号成功，isv需要根据结果明细判断取号是否成功。
3、取号接口不能控制是否使用隐私小号，是否使用隐私小号根据商家是否开通隐私面单以及用户下单是否勾选号码保护决定。
4、面单打印可增加自定义区域。
5、支持合并取号。可通过merge_retrieval_order_nos字段传合并取号时剩余订单号
6、apply_id是取号的业务唯一标识，无论取号成功与否，都会保留第一次的取号结果（网络异常等系统问题不会导致apply_id被占用）
7、支持连锁，连锁订单取号需要传trade_order_info_list->package_info->items->oid
8、连锁体系下任何分店或总部开通的电子面单，均可以给同一连锁体系下的所有订单取号。连锁店铺不能给连锁体系外的其他连锁店铺或者单店取号。
9、支持自定义区，自定义区必需要传trade_order_info_list->package_info->items->oid，否则不会返回自定义区打印报文字段。自定义区打印报文需要与正常打印报文合成数组使用

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.logistics.waybill.apply/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.logistics.waybill.apply/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.logistics.waybill.apply/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4244)*