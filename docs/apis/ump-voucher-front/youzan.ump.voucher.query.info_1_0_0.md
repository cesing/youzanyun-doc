---
apiName: "youzan.ump.voucher.query.info.1.0.0"
version: "1.0.0"
appName: "ump-voucher-front"
apiGroup: "营销优惠"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4247"
---

# youzan.ump.voucher.query.info.1.0.0

> **所属分组**: 营销优惠

---

## 1. 场景说明

获取买家优惠凭证基础信息( 不支持优惠码查询 )
1. youzan.ump.voucher.query.detail 区别： 参数不同，当前接口使用 code 查询优惠券信息
2. youzan.ump.coupon.consume.get  区别: 返回结果不同，性能不同，当前接口返回接口数据较少，但性能比较好。
   - 如：不需要优惠券凭证的使用规则、适用规则，只需要根据优惠券凭证号码获取优惠券凭证ID 时可以使用当前接口以便更快速的获取到结果。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.ump.voucher.query.info/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.ump.voucher.query.info/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.ump.voucher.query.info/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4247)*