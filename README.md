# ChemDraw 与 Word 基础绘图标准

这是一个用于绘制、返修和检查可编辑 ChemDraw 结构及 Word 图稿的 Codex skill。当前版本为 **2.0.0**。

它涵盖普通键长、二维键角、原生字体、编号与产率、甲基表示、图间显示尺度，以及 Word 中 ChemDraw OLE 对象的验证。

## 下载与安装

1. 在仓库中打开 [chemdraw-word-standard.zip](chemdraw-word-standard.zip)，点击下载。
2. 解压后得到 `chemdraw-word-standard` 文件夹，其中包含 `SKILL.md`、`scripts`、`references` 和 `assets`。
3. 在 Windows 文件资源管理器地址栏输入 `%USERPROFILE%\.codex\skills` 并回车，把解压得到的文件夹放进去。已有同名文件夹时，先备份旧版，再替换。
4. 重新打开 Codex，要求它使用 `chemdraw-word-standard` 绘图或检查图稿。

本版本 ZIP 的 SHA-256：

```text
09379c6acc8a3ed4fcc4009bd0c132bf13453d76e1b51ff3c4169f0bbbc7400c
```

## 2.0.0 更新

- 修复键角检查计划中命令行容差被忽略的问题，并增加拓扑角度建议和源文件绑定的检查计划。
- 新增只读 CDXML 检查，分别报告键长、字体、Me 和编号格式的结果；新增结构、编号、产率及标记的对应检查。
- 新增 Windows 原生保存和 Word OLE 嵌入工具、实际宽高检查及环境预检。工具报告与 Word 页面、双击打开的原生图和 PDF 的视觉验收分别记录。
- 增加版本号、文件哈希清单和回归测试；精简入口，详细规则与测试说明放在 `references`。

复杂立体结构、投影、配位结构及无法确定的语义会列为待复核。检查脚本不修改输入文件，也不能单独证明 Word 缓存、OLE 可编辑性或 PDF 页面正确。

## 验证与环境

解压后，在技能文件夹中可运行：

```text
python -B scripts/verify_manifest.py .
python -B -m unittest discover -s scripts -p "test_*.py" -v
```

纯 Python 检查脚本使用 Python 3.10 及以上版本的标准库。本版的 79 项回归测试已通过。`geometry-negative-control` 以及编号、产率对调示例是故意设置的反例，仅用于测试；示例中的编号和产率均为格式测试数据。

没有 ChemDraw 和 Word 时，只能交付候选 CDXML 等阶段成果；验证原生结构需要可用的 ChemDraw，制作并验收可编辑 Word OLE 对象还需要 Microsoft Word。Windows 自动化流程已在 ChemDraw 25.0.2.14 与 Word 16.0.14334 上实测；其他版本应自行验证。此 skill 不包含这些商业软件。

## 2.1.0 发布证据

[下载 2.1.0 发布证据包](chemdraw-word-standard-2.1.0-release-evidence.zip)。证据包包含迁移记录和测试结果，不包含 2.1.0 安装包；上方提供的安装包仍为 2.0.0。
