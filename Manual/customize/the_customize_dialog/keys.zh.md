# 按键

“按键”页面允许您查看和配置可用于运行命令或启动程序的“键盘快捷键”或“热键”（按键组合）。Opus 允许您将一个或多个按键分配给工具栏按钮或菜单命令，而按下该按键的作用与单击该按钮相同。您还可以创建“仅限热键”功能，这些功能仅存在于按键分配中，且未链接到工具栏。

### 类别

分类列表允许您按类别查看按键或同时显示所有按键。类别包括：

- **冲突**：显示任何冲突（即同时将同一按键分配给两个或更多操作）。
- **列表按键**：这些按键仅在列表内有效（通常在文件列表处于活动状态时）。
  - **热键**：仅限热键功能（未分配给按钮或菜单）。
  - **工具栏**：分配给工具栏或菜单按钮的按键。
  - **非活动工具栏**：来自已关闭工具栏的按键（按键本身仍然处于活动状态）。
  - **文件夹树**：仅在文件夹树处于活动状态时有效的仅限热键功能。
  - **快速按键**：[配置](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.zh.md) 中配置的按键，用于激活 [即时查找字段](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md)。
  - **最喜爱的文件夹**：分配给 [收藏列表](/Manual/preferences/preferences_categories/frequently_used_paths/favorites_list.zh.md) 中文件夹的按键。
- **系统级按键**：这些热键可在系统中的任何位置使用（Opus 处于运行状态时）。您不需要打开列表即可使用它们——Opus 只需在后台运行即可。
  - **热键**：仅限热键功能。
  - **浮动工具栏**：分配给浮动工具栏上按钮的按键。
  - **托盘菜单**：分配给 [托盘图标菜单](context_menus.zh.md) 中按钮的按键。
- **查看器按键**：仅在 [独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中有效的热键。
  - **热键**：仅限热键功能。
  - **工具栏**：分配给图像查看器工具栏上按钮的按键。

### 按键

此列表针对已分配的每个按键组合显示一个条目。列表中在每个按键旁显示的复选框允许您暂时禁用热键，而不必将其删除。

如果一个功能具有多个按键分配，那么它们将单独显示（并且可以单独启用/禁用）。

![](/Manual/images/media/13/hotkey_multiple.png)

例如，定位栏上的路径字段默认有三个按键分配——<kbd>F4</kbd>、<kbd>Alt+D</kbd> 和 <kbd>Ctrl+L</kbd>。这里列出了所有三个按键，并且您可以看到它们在视觉上都链接到 *文件列表* 工具栏上的 *定位* 字段。

在页面底部有两个字段，可用于过滤热键列表。您可以按按键和命令分别搜索。

### 编辑按键

使用页面顶部的工具栏来操作热键。**新建** 下拉菜单允许您在此创建四种类型的按键：

- **新建列表热键**：对应于 *列表按键/热键* 类别。
- **新建系统级热键**：对应于 *系统级按键/热键* 类别。
- **新建文件夹树热键**：对应于 *列表按键/文件夹树* 类别。
- **新建查看器热键**：对应于 *查看器按键/热键* 类别。

无法从这里创建其它类型的按键——相反，您在“就地”创建它们（例如对于工具栏按钮，您可以通过编辑按钮本身为其分配按键）。同样，仅能从这里删除这四种类型的按键。

但是，大多数现有按键都可以修改——唯一例外是配置（*最喜爱的文件夹* 和 *快速按键*）中配置的按键——使用页面顶部的 **更改按键** 字段。

### 导入和导出

对话框右上角的 ![](/Manual/images/media/13/prefs_menu.png) 页面菜单中包含用于导出和导入热键列表的命令。

您可以使用三种不同的格式导出您的热键列表（在保存对话框中使用 **另存为类型** 下拉列表选择要使用的类型）。

- *可导入热键格式* 是一种格式，您可以使用该格式导出您的热键，以便将它们重新导入到 Directory Opus 中（例如在另一台计算机上，或与朋友分享您的按键）。选择此格式实际上导出了功能以及按键信息。选择此格式时，仅导出“真正的”热键——不会导出工具栏按键分配等。
- *逗号分隔列表* 导出所有热键及其名称和描述（但不导出它们运行的功能）的列表，作为 **.csv** 文件。例如，如果您想为自己制作一个可打印的按键参考，可以使用它。您可以在 Excel 或 Word 中导入此文件并在打印前对其执行进一步操作。在此模式下，导出所有类型的热键。
- *文本格式* 将所有热键的列表导出为纯文本文件。与 *逗号分隔列表* 选项类似，在此模式下导出所有类型的热键。