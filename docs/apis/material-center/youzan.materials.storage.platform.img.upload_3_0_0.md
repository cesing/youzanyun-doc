---
apiName: "youzan.materials.storage.platform.img.upload.3.0.0"
version: "3.0.0"
appName: "material-center"
apiGroup: "其它"
method: "uploadOpenPlatformBinaryPublicImage"
timeout: 60000
authType: "凭证式"
type: "Dubbo"
detailUrl: "https://doc.youzanyun.com/detail/content/API/0/193"
---

# youzan.materials.storage.platform.img.upload.3.0.0

> **所属分组**: 其它  **所属应用**: material-center

---

## 1. 场景说明

开发者使用的图片上传接口，可以支持上传5MB以内的图片到店铺素材库，并支持分组上传(店铺后台-素材中心-图片)，支持 .jpg, .gif, .png, .bmp 格式。上传成功后，可将图片id和图片链接存下，便于后续复用。 如需上传多张图片，建议采用并发请求接口上传，每次发起10个以内请求最佳。仅支持本地上传，不支持网络图片。
请求该接口前，先校验上传文件大小是否超限。

---

## 2. 请求

**请求方法**: `POST`

**请求地址**: `https://open.youzanyun.com/api/youzan.materials.storage.platform.img.upload/3.0.0`

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
curl -X POST 'https://open.youzanyun.com/api/youzan.materials.storage.platform.img.upload/3.0.0' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

```python
import requests
url = "https://open.youzanyun.com/api/youzan.materials.storage.platform.img.upload/3.0.0"
payload = {}
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Content-Type': 'application/json'}
response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

---

## 4. 能力包权限

**INFO: 接口计费状态请以官网实际披露为准。**

---

*原文地址：[doc.youzanyun.com](https://doc.youzanyun.com/detail/content/API/0/193)*