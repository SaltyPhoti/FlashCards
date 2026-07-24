Pocket Cards · GitHub Pages 上传说明

1. 解压 Pocket_Cards_GitHub_Pages.zip。
2. 把解压后的全部文件上传到 GitHub 仓库根目录。
3. 必须保留 .nojekyll、README.md、index.html、app.js、app.css、sw.js、
   manifest.webmanifest、starter-cards.json 和图标文件。
4. 不要把 ZIP 文件本身上传到仓库。
5. 已经启用过 GitHub Pages 时，只需覆盖同名文件并提交，不用重新设置 Pages。

手机中的卡片、图片和复习进度保存在该浏览器的本地数据库里。
更新网站文件不会删除或覆盖它们。

“管理”页面中的“重置本端数据”只会清空当前浏览器或设备。
重置数据无法恢复，建议先在确认窗口中导出完整备份。

如果更新后仍看到旧界面，请完全关闭这个 PWA/Safari 页面后重新打开；
GitHub Pages 发布和浏览器缓存更新有时需要几分钟。

已有卡片不会被新默认值覆盖：
- 如果现有卡片是 abandon / brief / maintain，请导入
  ADD_SPELLING_TO_VOCAB_STARTERS.csv。
- 如果现有卡片还是 Peppermint / Distillation / Rhizome，请导入
  MIGRATE_OLD_STARTERS.csv。
