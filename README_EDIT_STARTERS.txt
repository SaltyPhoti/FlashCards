Pocket Cards · 修改首次启动的默认卡片

需要修改的文件：starter-cards.json

示例结构：

{
  "deckName": "植物拉丁名",
  "dailyNewLimit": 5,
  "cards": [
    {
      "sourceId": "starter-peppermint",
      "front": "薄荷",
      "back": "Peppermint",
      "spelling": "Mentha × piperita",
      "tags": ["植物", "香草"],
      "state": "new"
    }
  ]
}

字段说明：
- deckName：默认卡组名。
- dailyNewLimit：每天的新卡上限，范围 1–100。
- sourceId：每张卡稳定且不重复的 ID。
- front / back：正面和背面，必填。
- spelling：拼写标准答案，可省略。
- tags：标签数组，可省略。
- frontImage / backImage：图片地址，可省略。
- state："new" 或 "review"，可省略，默认是 "new"。
- intervalDays / repetitions / lapses：复习状态，可省略。

重要：
- 这个文件只决定“这个浏览器第一次打开、尚无本地卡片数据”时看到什么。
- 已经使用过应用的人，其卡片和复习进度不会被默认卡片覆盖。
- 想更新已有用户的卡片，请在应用里编辑，或用带稳定 sourceId 的 CSV/JSON 导入。
- JSON 最后一个字段后面不能有多余逗号。
