---
apiName: "youzan.message.courier.hosting.config.get.1.0.0"
version: "1.0.0"
appName: "courier-cp"
apiGroup: "其它"
method: "getHostingConfig"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/5069"
---

# youzan.message.courier.hosting.config.get.1.0.0

> **所属分组**: 其它  **所属应用**: courier-cp

---

## 1. 场景说明

查询店铺的客服托管配置状态。

功能说明：
查询指定店铺当前的客服托管开关是否开启。开启托管后，店铺的客服咨询将由AI或第三方系统接管处理。

返回字段说明：
- kdt_id：实际生效的店铺ID（连锁子店会返回总部ID）
- enable：托管开关状态，true表示已开启，false表示已关闭

使用场景：
1. 第三方客服系统查询店铺托管状态，决定是否接管会话
2. 管理后台展示托管配置信息
3. 业务流程中判断是否走托管链路

注意事项：
- 连锁子店查询时，返回的是总部的托管配置
- 未配置过的店铺默认返回enable=false

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.message.courier.hosting.config.get/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.message.courier.hosting.config.get/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.message.courier.hosting.config.get/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/5069)*