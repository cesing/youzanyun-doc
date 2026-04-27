---
apiName: "youzan.message.courier.hosting.list.conversation.1.0.0"
version: "1.0.0"
appName: "courier-cp"
apiGroup: "其它"
method: "listByCursor"
timeout: 5000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/5070"
---

# youzan.message.courier.hosting.list.conversation.1.0.0

> **所属分组**: 其它  **所属应用**: courier-cp

---

## 1. 场景说明

分页查询店铺的托管会话记录列表。支持按时间范围过滤，采用游标分页方式，适用于大数据量场景下的高效翻页查询。

使用场景：
1. 查询店铺在托管模式下产生的所有会话记录
2. 按时间范围筛选特定时段的托管会话
3. 数据同步或报表统计时批量拉取会话数据

注意事项：
- 单次查询最多返回100条记录，建议使用游标翻页获取全量数据
- 时间参数为秒级Unix时间戳
- 返回结果按会话ID升序排列

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.message.courier.hosting.list.conversation/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.message.courier.hosting.list.conversation/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.message.courier.hosting.list.conversation/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/5070)*