---
apiName: "youzan.material.general.video.custom.upload.create.1.0.0"
version: "1.0.0"
appName: "material-center"
apiGroup: "大客CRM"
authType: "凭证式"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/689"
---

# youzan.material.general.video.custom.upload.create.1.0.0

> **所属分组**: 大客CRM

---

## 1. 场景说明

创建腾讯云视频方案的视频，该方案的视频会保存在合作方的素材库中（例如店铺后台的商家视频素材库）。在视频文件提交到上传点api后，需要立刻请求此接口进行转码和审核任务状态推进。若上传完成后没有立刻请求该接口创建视频，可能会丢弃对应的转码和审核任务，将需要等待我们的主动补偿来推进视频状态。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.material.general.video.custom.upload.create/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.material.general.video.custom.upload.create/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.material.general.video.custom.upload.create/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/689)*