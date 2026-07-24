
### CSV 格式

推荐使用以下表头：

```csv
sourceId,front,back,tags,frontImage,backImage
mint-001,Peppermint,薄荷是一种芳香多年生草本植物,植物;香草,images/mint-front.jpg,images/mint-back.jpg
distill-001,Distillation,利用沸点差异分离液体混合物,工艺,,
```

字段说明：

* `front`：正面，必填
* `back`：背面，必填
* `tags`：标签，可用分号分隔
* `sourceId`：稳定且唯一的编号，强烈建议填写
* `frontImage`：正面图片路径
* `backImage`：背面图片路径

也支持中文表头：`正面、背面、标签、正面图片、背面图片、id`。

### JSON 格式

可以直接使用数组：

```json
[
  {
    "sourceId": "mint-001",
    "front": "Peppermint",
    "back": "薄荷是一种芳香多年生草本植物。",
    "tags": ["植物", "香草"],
    "frontImage": "images/mint-front.jpg",
    "backImage": "images/mint-back.jpg"
  },
  {
    "sourceId": "distill-001",
    "front": "Distillation",
    "back": "利用沸点差异分离液体混合物的方法。",
    "tags": ["工艺"]
  }
]
```

也支持外面包一层：

```json
{
  "cards": [
    {
      "sourceId": "mint-001",
      "front": "Peppermint",
      "back": "薄荷",
      "tags": ["植物"]
    }
  ]
}
```

### 带图片时

图片和 CSV/JSON 必须一起压缩成 ZIP：

```text
cards.csv
images/
  mint-front.jpg
  mint-back.jpg
```

然后在 Pocket Cards 的管理页选择这个 ZIP。单独导入 CSV/JSON 时，相对图片路径无法读取。

导入前记得先选择目标卡组。没有 `sourceId` 的卡片每次导入都会新增，可能产生重复。
