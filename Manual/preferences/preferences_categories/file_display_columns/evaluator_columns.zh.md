# 求值器列

此页面允许您创建自己的列，它们可以使用 [求值器](/Manual/evaluator/README.zh.md) 来操作文件名或其它元数据以生成它们显示的文本。

例如，您可以使用求值器的 [RegEx()](/Manual/reference/evaluator/regex.zh.md) 函数来提取文件名的一部分并将其显示在单独的列中。

您的已配置列显示在列表中。使用列表上方的工具栏按钮添加、编辑或删除列。您也可以使用共享按钮将列的定义复制到剪贴板，或者粘贴到剪贴板中。

底部有一个标记为 **示例文件** 的字段。这允许您选择一个将被馈送至列表中所有已定义列的文件，以填充 **示例** 列。这能使您实时查看您的列如何工作。

单击 **添加** 或 **编辑** 按钮将显示列编辑器。

### 列编辑器

![evalcolumn_editor.png](/Manual/images/media/13/evalcolumn_editor.png)

上图显示了内置示例求值器列之一的默认 **图像字节** 列的定义。

- **标题**：定义您的列的标题。这显示在 Opus 中的列列表中。
- **标题标题**：允许您提供一个可选项标题，它用于列表中的列标题。如果您将其留空，则使用 **标题** 代替。
- **关键字**：定义一个允许以编程方式控制您的列的关键字。所有求值列关键字都以前缀 `eval:` 开始，后跟指定的关键字。例如，可以使用命令 <nobr>`Set COLUMNSTOGGLE=eval:imagebytes`</nobr> 启用上述列。
- **求值器代码**：您可以在此处输入生成列内容的求值器代码。有关更多详细信息，请参阅 [求值器](/Manual/evaluator/applicable_contexts/evaluator_columns.zh.md) 部分。
- **类型**：列的类型决定它如何显示您的代码生成的内容。
  ^类型^说明^

  |           |                                                                                                |
  |-----------|------------------------------------------------------------------------------------------------|
  | 日期      | 使用当前语言环境设置将提供的值显示为日期。                       |
  | 日期/时间 | 使用当前语言环境设置将它显示为日期和时间。                              |
  | 双精度型    | 显示一个双精度数字。小数位数将受到限制。              |
  | 图形     | 将值显示为图表（预计值在 0 到 100 之间）。                                 |
  | 百分比   | 将值显示为百分比。                                                            |
  | 评级    | 将值显示为一个或多个星号。星号的最大数目单独配置。 |
  | 有符号    | 显示一个有符号值。                                                                       |
  | 大小      | 将值显示为文件大小，并带有适当的后缀。                                 |
  | 文本      | 显示纯文本。                                                                           |
  | 时间      | 使用当前语言环境设置将值显示为时间。                                |
  | 无符号  | 显示一个无符号值。                                                                    |

- **图形颜色**：当类型设置为 *图形* 时，这允许您为图形配置“填充”颜色。
- **最大星号**：当类型设置为 *评级* 时，这允许您配置列中星号的最大数目。
- **类别**：定义列在列列表中出现的类别。
- **对齐**：定义列对齐方式（左对齐、右对齐或居中对齐）。
- **默认宽度**：列的可选默认宽度，可以用像素或字符指定。
- **默认按相反顺序排序**：为日期字段等列启用此选项，您希望默认按相反的排序顺序（例如，最新的文件位于顶部而不是底部）。
- **如果文件更改则刷新**：如果启用，当检测到文件已更改时，Opus 会为给定文件重新生成您的列内容。只有当唯一更改是文件属性（而不是其大小或时间戳）时，**包括属性** 选项才会使此操作发生。
- **如果名称更改则刷新**：如果启用此选项，则在文件重命名时，Opus 会重新生成您的列内容。对于基于文件名的任何求值器列，您会希望这样做。
- **仅限文件系统文件夹**：如果启用，此列将仅在普通文件系统文件夹（例如 C:) 中可用，而不能在 FTP 站点或压缩包等位置中使用。如果您的列依赖于仅对实际文件可用的元数据，则会希望启用此选项。
- **自定义分组**：如果启用，求值子句将单独调用，其中变量 `operation` 设置为值 `"group"`。这允许您返回您希望将项默认放入的组的名称。

有关可以在何处使用求值器，请参阅有关 [求值器](/Manual/evaluator/README.zh.md) 的部分。