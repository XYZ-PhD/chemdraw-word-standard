# ChemDraw 与 Word 基础绘图标准

这是为 ChemDraw 化学结构和 Word 图稿制作的 Codex skill，涵盖普通键长、二维键角、原生字体、编号、甲基表示、跨图显示尺度和可编辑对象检查。

## 下载与使用

1. 在仓库中打开 `chemdraw-word-standard.zip`，点击下载。
2. 解压后，得到 `chemdraw-word-standard` 文件夹；文件夹里应能看到 `SKILL.md`、`scripts`、`references` 和 `assets`。
3. 在 Windows 文件资源管理器地址栏输入 `%USERPROFILE%\.codex\skills` 并回车，把解压出的 `chemdraw-word-standard` 文件夹放进去。已有同名文件夹时，先备份旧版，再替换。
4. 重新打开 Codex，要求它使用 `chemdraw-word-standard` 绘图或检查图稿。

此版本提供原生 ChemDraw 测试示例、键角覆盖检查和回归测试。`geometry-negative-control` 包含故意绘错的结构，仅用于验证检查器，不是合格的绘图模板。示例中的产率是格式测试数据。

制作用于 Word 的 ChemDraw 可编辑对象需要安装且能够运行 ChemDraw 和 Microsoft Word。此 skill 不包含这些商业软件。
