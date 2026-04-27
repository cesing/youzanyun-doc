---
apiName: "youzan.appstore.open.user.get.1.0.0"
version: "1.0.0"
appName: "appstore"
apiGroup: "其它"
method: "getInfoByUserToken"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/707"
---

# youzan.appstore.open.user.get.1.0.0

> **所属分组**: 其它  **所属应用**: appstore

---

## 1. 场景说明

根据”去使用“newUserToken查询员工使用信息，触发场景：当店铺购买应用后，店铺员工点击”去使用“时候触发newUserToken，newUserToken值传入下方请求参数user_token中。该接口access_token调用规则：使用当前应用中下的任意有效access_token即可调用此接口，会校验店铺是否已授权给access_token对应的client_id，校验通过才会响应店铺员工操作人数据。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.appstore.open.user.get/1.0.0`

**请求参数**（1 个）:

```json
{
  "type": "object",
  "properties": {
    "user_token": {
      "type": "java.lang.String",
      "description": "请传入点击”去使用“时触发newUserToken值，不是传值access_token的值，请勿传错",
      "example": "1624430821983R2fXmLsws9tjuZdhHFSfZ6xS#/user/login"
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
      "type": "com.youzan.cloud.appstore.api.dto.response.open.UserInfoDTO",
      "description": "响应参数",
      "example": ""
    },
    "kdt_id": {
      "type": "java.lang.Long",
      "description": "店铺id",
      "example": "554134"
    },
    "app_id": {
      "type": "java.lang.Long",
      "description": "应用appid",
      "example": "43513"
    },
    "phone": {
      "type": "java.lang.String",
      "description": "操作人手机号码",
      "example": "15866666666"
    },
    "user_id": {
      "type": "java.lang.Long",
      "description": "购买者身份id（不推荐使用，推荐使用下方yz_open_id）",
      "example": "3413423"
    },
    "shop_name": {
      "type": "java.lang.String",
      "description": "店铺名称",
      "example": "测试店铺"
    },
    "shop_type": {
      "type": "java.lang.Integer",
      "description": "店铺类型： 0:微商城/教育店铺 1:微小店 6:美业 7:零售，详细店铺类型区分请使用店铺分组下【youzan.shop.basic.get.3.0.0】接口查询",
      "example": "0"
    },
    "shop_role": {
      "type": "java.lang.Integer",
      "description": "店铺角色： 0:单店 1:总店 2:分店",
      "example": "1"
    },
    "yz_open_id": {
      "type": "java.lang.String",
      "description": "有赞客户id(推荐使用)",
      "example": "LnhGm4rh576452722916618240"
    },
    "code": {
      "type": "java.lang.String",
      "description": "店铺授权授权code，工具型应用使用该code获取access_token",
      "example": "gdkhrwkgrkgjsdgvjoafoworf"
    },
    "success": {
      "type": "boolean",
      "description": "调用结果",
      "example": "true"
    }
  }
}
```

**成功响应示例**:

```json
{
  "data": "",
  "kdt_id": "554134",
  "app_id": "43513",
  "phone": "15866666666",
  "user_id": "3413423",
  "shop_name": "测试店铺",
  "shop_type": "0",
  "shop_role": "1"
}
```

---

## 3. cURL / Python 调用示例

```bash
curl -X POST 'https://open.youzanyun.com/api/youzan.appstore.open.user.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.appstore.open.user.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/707)*