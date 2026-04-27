---
apiName: "youzan.material.image.actual.delete.1.0.0"
version: "1.0.0"
appName: "material-center"
apiGroup: "其它"
method: "deleteActualImage"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/3581"
---

# youzan.material.image.actual.delete.1.0.0

> **所属分组**: 其它  **所属应用**: material-center

---

## 1. 场景说明

素材中心图片资源永久批量删除
1、接口使用前，需联系素材中心产品或开发进行配置白名单（需要提供店铺kdt_id）。 
2、该接口属于高风险接口请谨慎操作，接口执行删除后，图片素材在有赞系统中永久删除且无法恢复，请谨慎使用。
3、应用想获取该接口调用权限，需要提供向素材中心申请通过证明，同步提供应用appid联系有赞云开发者运营单独挂载该权限，通过后方可调用。


---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.material.image.actual.delete/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.material.image.actual.delete/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.material.image.actual.delete/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/3581)*