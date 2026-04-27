---
apiName: "youzan.cardvoucher.card.list.commission.1.0.0"
version: "1.0.0"
appName: "yz-cardvoucher-biz"
apiGroup: "储值卡"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3927"
---

# youzan.cardvoucher.card.list.commission.1.0.0

> **所属分组**: 储值卡

---

## 1. 场景说明

根据交易单号查询提成信息，如果这个单子没有获得提成的人，则返回空。
下单后非即时返回结果，一般5秒内出结果，建议做个兼容操作，如果未查询到结果，可以1分钟，5分钟，10分钟再进行结果查询。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.cardvoucher.card.list.commission/1.0.0`

**认证方式**: 凭证式

**请求参数**（3 个）:

```json
{
  "type": "object",
  "properties": {
    "request": {
      "type": "com.youzan.pay.cardvoucher.biz.api.valuecard.request.CardCommissionOpenRequest",
      "description": "请求参数",
      "example": ""
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺在有赞的id标识，有赞平台生成，在有赞平台唯一，用于判断信息属于哪一个店铺",
      "example": "96991937"
    },
    "out_trade_no": {
      "type": "java.lang.String",
      "description": "交易单号充值就是充值单号，购卡就是订单号，退卡就是退卡的业务单号",
      "example": "RN221110201143000018"
    }
  },
  "required": []
}
```

**响应参数**（11 个）:

```json
{
  "type": "object",
  "properties": {
    "data": {
      "type": "java.util.List<com.youzan.pay.cardvoucher.biz.api.valuecard.response.CardCommissionOpenResponse>",
      "description": "查询返回数据",
      "example": ""
    },
    "accept_kdt_id": {
      "type": "java.lang.Long",
      "description": "受理店铺Id",
      "example": "101438086"
    },
    "principal_amount": {
      "type": "java.lang.Long",
      "description": "本金变动金额，单位分",
      "example": "10000"
    },
    "take_commissions_id": {
      "type": "java.lang.Long",
      "description": "该字段已经废弃，不在透出有效值，切勿使用",
      "example": "0"
    },
    "commissions_amount": {
      "type": "java.lang.Long",
      "description": "提成金额应退提成金额",
      "example": "10000"
    },
    "guide_kdt_id": {
      "type": "java.lang.Long",
      "description": "导购所属门店网店id",
      "example": "101438086"
    },
    "template_name": {
      "type": "java.lang.String",
      "description": "卡模板名称",
      "example": "YZ-测试连锁L版-导购专用余额"
    },
    "template_no": {
      "type": "java.lang.String",
      "description": "卡模版号",
      "example": "110202622134533"
    },
    "operate_type": {
      "type": "java.lang.Integer",
      "description": "操作类型0：充值1：购卡2：退卡3：充值退款",
      "example": "0"
    },
    "yz_open_id": {
      "type": "java.lang.Long",
      "description": "提成人id对应的yzOpenId",
      "example": "QEcp8wef856822440347590656"
    },
    "count": {
      "type": "int",
      "description": "总的记录数",
      "example": "2"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "accept_kdt_id": "101438086",
  "principal_amount": "10000",
  "take_commissions_id": "0",
  "commissions_amount": "10000",
  "guide_kdt_id": "101438086",
  "template_name": "YZ-测试连锁L版-导购专用余额",
  "template_no": "110202622134533"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.cardvoucher.card.list.commission/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.cardvoucher.card.list.commission/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3927)*