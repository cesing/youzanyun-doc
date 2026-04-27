---
apiName: "youzan.saleschannel.setting.specified.operate.1.0.0"
version: "1.0.0"
appName: "salesman-open"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/4615"
---

# youzan.saleschannel.setting.specified.operate.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

批量保存或编辑人维度渠道商结算配置（如果有赞的用户id存在指定结算 即为编辑数据；不存在保存数据）（最大限制200）

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.saleschannel.setting.specified.operate/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.saleschannel.setting.specified.operate/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.saleschannel.setting.specified.operate/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/4615)*