# Directory Opus 13 - 详细发行说明

# 拆分/合并

- 改善了用户界面。
- 添加了用于 Base64 编码的选项（带或不带拆分）。
- 在拆分时，显示文件数据开头，以帮助选择最合适的拆分方法。
- 现在可以在行边界上拆分文本文件。在此模式下，使用每个文件的一行计数，而不是字节计数。
- 在拆分时，以透明方式处理 ANSI/UTF8/UTF16。
- 在合并时，新的 *规范文本编码* 模式允许您合并不同编码的文本文件。
  - 如果所有文件使用相同的编码，则按原样保留（除了移除额外的 BOM）。
  - 在有多个编码的情况下，输出将转换为 UTF-8。
- 在所有输出文件中复制原始文件第一行的选项（例如，用于 CSV 数据）。
- 命令：
  - `Split LINES SIZE=n`——将文件拆分为 *n* 行块。
  - `Join CONVERT`——指定编码/转换模式，如同用户界面中的下拉列表。

------------------------------------------------------------------------

下一步：[archives](/Manual/release_history/opus13_detailed/archives.zh.md)