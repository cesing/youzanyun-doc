---
apiName: "youzan.message.courier.hosting.config.update.1.0.0"
version: "1.0.0"
appName: "courier-cp"
apiGroup: "其它"
method: "updateHostingConfig"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/5068"
---

# youzan.message.courier.hosting.config.update.1.0.0

> **所属分组**: 其它  **所属应用**: courier-cp

---

## 1. 场景说明

更新店铺的客服托管配置开关。

功能说明：
开启或关闭店铺的客服托管功能。开启托管后，店铺的客服咨询将由AI或第三方系统接管处理；关闭后恢复人工客服模式。

请求参数说明：
- enable：托管开关，true开启托管，false关闭托管

返回说明：
- 该接口为写操作，成功时不返回业务数据，通过success和code判断操作结果

使用场景：
1. 商家通过第三方系统开启/关闭AI客服托管
2. 批量管理多店铺的托管配置
3. 第三方客服系统接入时启用托管模式

注意事项：
- 连锁子店更新时，配置会同步到总部
- 配置变更实时生效
- 建议在非高峰期进行配置切换

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.message.courier.hosting.config.update/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.message.courier.hosting.config.update/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.message.courier.hosting.config.update/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/5068)*