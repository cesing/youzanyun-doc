---
apiName: "youzan.guide.shoppingguide.add.1.0.1"
version: "1.0.1"
appName: "guide-pyxis"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3689"
---

# youzan.guide.shoppingguide.add.1.0.1

> **所属分组**: 其它

---

## 1. 场景说明

添加导购员。连锁店铺仅支持总部调用。需要店铺购买导购插件（需要升级到新版的销售员插件能力，详情见：https://help.youzan.com/displaylist/detail_4_4-2-57122?page=1）Ps. 该接口已废弃，请用youzan.guide.shoppingguide.create.2.0.0代替

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.guide.shoppingguide.add/1.0.1`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.guide.shoppingguide.add/1.0.1' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.guide.shoppingguide.add/1.0.1"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3689)*