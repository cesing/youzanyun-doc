---
apiName: "youzan.material.general.video.custom.read.generateVideoPlayInfo.1.0.0"
version: "1.0.0"
appName: "material-center"
apiGroup: "大客CRM"
method: "generateVideoPlayInfo"
timeout: 1000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/693"
---

# youzan.material.general.video.custom.read.generateVideoPlayInfo.1.0.0

> **所属分组**: 大客CRM  **所属应用**: material-center

---

## 1. 场景说明

合作方的素材库中（例如店铺后台的商家视频素材库）视频播放信息生成接口。该接口请求成功时会返回视频的播放信息和视频的基础信息，无法播放的视频将会抛出异常。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.material.general.video.custom.read.generateVideoPlayInfo/1.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.material.general.video.custom.read.generateVideoPlayInfo/1.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.material.general.video.custom.read.generateVideoPlayInfo/1.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/693)*