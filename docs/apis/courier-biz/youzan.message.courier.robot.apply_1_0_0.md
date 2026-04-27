---
apiName: "youzan.message.courier.robot.apply.1.0.0"
version: "1.0.0"
appName: "courier-biz"
apiGroup: "其它"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/2142"
---

# youzan.message.courier.robot.apply.1.0.0

> **所属分组**: 其它

---

## 1. 场景说明

一、功能描述
发送机器人消息
二、使用说明
1、需要三方机器人服务商接入<多客服机器人扩展点>
2、从<多客服机器人扩展点>中同步获取 当前接口的调用凭证Token。(Token的获取参见:<多客服机器人扩展点>文档)
3、使用获取到的token调用当前接口
三、接口规则
每个Token只能在5秒内回复3条消息



---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.message.courier.robot.apply/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.message.courier.robot.apply/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.message.courier.robot.apply/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/2142)*