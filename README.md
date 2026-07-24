# Pocket Cards 上传文件帮助

Pocket Cards 支持导入 `.csv`、`.tsv`、`.json`，也支持把卡片文件和图片一起打包成 `.zip` 导入。

## CSV / TSV

第一行建议使用字段名。`front` 和 `back` 必填，`spelling` 选填：

```csv
sourceId,front,back,spelling,tags,frontImage,backImage
peppermint,薄荷,Peppermint（薄荷）,Mentha × piperita,植物;香草,images/peppermint-front.jpg,images/peppermint-back.jpg
```

字段说明：

- `front`：卡片正面，必填。
- `back`：卡片背面，必填。
- `spelling`：拼写标准答案，选填。填写后，复习正面会出现输入框。
- `tags`：标签，多个标签用分号、英文逗号或中文逗号分隔。
- `sourceId`：稳定且不重复的 ID。再次导入相同 `sourceId` 时会更新原卡片，并保留复习进度。
- `frontImage` / `backImage`：图片相对路径，选填。

也可以使用中文表头：`正面`、`背面`、`拼写`、`标签`、`正面图片`、`背面图片`。

如果卡片文字里包含英文逗号，请用英文双引号包住整个单元格。

## JSON

可以导入数组，也可以使用带 `cards` 的对象：

```json
{
  "cards": [
    {
      "sourceId": "peppermint",
      "front": "薄荷",
      "back": "Peppermint（薄荷）",
      "spelling": "Mentha × piperita",
      "tags": ["植物", "香草"],
      "frontImage": "images/peppermint-front.jpg"
    }
  ]
}
```

## 带图片的 ZIP

把 CSV 或 JSON 与图片一起放进 ZIP，路径保持一致：

```text
cards.csv
images/
  peppermint-front.jpg
  peppermint-back.jpg
```

`cards.csv` 中对应填写 `images/peppermint-front.jpg`。Pocket Cards 会在导入时把图片保存到这台设备。

## 拼写判定与复习

- 拼写比较不区分大小写，并会忽略首尾空格及连续空格。
- 有 `spelling` 的卡片必须先输入，才能点击卡面翻面。
- 也可以直接点击“显示答案”；这种情况会记为本轮拼写未通过。
- 拼错或直接显示答案时，本轮只可选择“重来”，卡片会再次进入当天复习队列。
- 拼对后仍可按“重来 / 困难 / 记得 / 简单”评价卡片内容。

## 备份

应用“管理”页面的“下载完整备份”会保存所有卡组、卡片、图片及复习进度。恢复完整备份会替换当前设备里的全部数据。
