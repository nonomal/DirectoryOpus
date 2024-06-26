# Directory Opus 13 - 详细发行说明

# 边打字边查找 (即时查找)

- 新模式：
  - 有关默认键的列表，请参阅配置/过滤和排序/快捷键”。
  - Opus 搜索——使用 Opus 的内置“查找文件”功能在当前文件夹下方进行搜索：
    - 如果输入一个简单字符串或一个通配符，它将被视为通配符名称匹配。
    - 如果输入一个以“=”开头的字符串，它将由求值器处理，并且可以执行更复杂的查询（例如 `=size>100kb`）。
  - Everything (本地)——使用 Voidtools Everything 对当前文件夹下方进行索引搜索。
  - Everything (全局)——搜索整个机器的 Everything 索引。
  - 文件夹——显示从各种来源提取的文件夹弹出列表（例如最近、收藏和别名）。可以在配置/过滤和排序/边打字边查找/文件夹模式”下选择来源。
- 命令模式：
  - 与完整命令编辑器类似，在键入命令和参数时，建议的自动完成将显示。
  - 按 <kbd>Ctrl+Space</kbd> 强制显示光标下单词的建议。
- 查找模式：
  - （通过配置/过滤和排序/边打字边查找/查找模式”进行配置。）
  - 在使用基本的即时查找查找模式时，现在通过滚动条上的标记指示匹配文件名的位置，因此你可以判断视野之外是否有更多结果。
  - 在键入一个字符串后，你现在可以按 <kbd>Ctrl+S</kbd> 来选择所有匹配文件。
  - 新选项，“字段关闭后保持高亮可见（按 <kbd>Esc</kbd> 清除）”：
    - 启用后，即使在即时查找字段关闭后，匹配的高亮显示仍保持可见。
    - 在高亮显示保持可见时，<kbd>F3</kbd> 和 <kbd>Shift+F3</kbd> 将跳至下一个/上一个匹配项，覆盖其上的任何正常热键。
    - 按 Esc 键可清除高亮显示并返回正常状态。
  - 当 *不* 显示高亮显示时，<kbd>Shift+F3</kbd> 现在会重复上一次查找，使用与上次相同的字符串再次在当前文件夹中搜索匹配项。
    - 如果在同一文件夹中重复，焦点将放在上次匹配的文件上。
    - 可以通过自定义更改热键。
    - *命令：* `CLI QUICKFINDREPEAT` 是 Shift+F3 的默认运行方式。你还可以使用 `QUICKFINDREPEAT=next` 和 `QUICKFINDREPEAT=prev` 来将焦点放在下一个或上一个匹配项上。
  - 将旧的“fayt_firstchar_repeat”高级选项提升为“查找模式”页面上的复选框。
- 搜索引擎：
  - 现在可以通过配置在“快捷键”页面上设置即时查找如何使用不同的搜索引擎（Opus、Windows、Everything）的选项。
-即时查找脚本：
  - 脚本加载项现在可以使用新模式扩展即时查找。
  - 例子包括能够按一个键，然后键入一个字符串，以在指定的文件夹集下搜索匹配项，而不管起点是什么。我们将在支持论坛上发布一些示例。
  - 为脚本提供了搜索字符串，然后可以对其执行任何操作，包括将其传递给内部命令或外部工具。
  - 脚本可以根据你的键入内容进行响应，或稍作延迟，或在你按回车键时进行响应。这取决于查询运行的成本。
  - 与某些内置即时查找模式类似，脚本可以将结果反馈给 Opus，这些结果显示在弹出列表中，并会在你键入更多内容时缩小列表。
  -即时查找脚本可以有开关，类似于内置模式，并使用 `Script.Update即时查找Flags()` 方法来更新它们。
- 命令：
  - 当通过命令触发快速搜索时，可以指定搜索引擎。例如：`CLI QUICKSEARCH global:kittens QUICKSEARCHENGINE=everything`
  - `CLI QUICKFOLDERS=Cat` 将在文件夹模式下打开即时查找，显示以“Cat”开头的文件夹列表。

------------------------------------------------------------------------

下一个：[搜索字段](/Manual/release_history/opus13_detailed/search_field.zh.md)