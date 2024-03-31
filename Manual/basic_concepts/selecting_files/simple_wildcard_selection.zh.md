# 简单通配符选择

**选择文件**对话框有两种模式；*简单* 和 *高级*。可通过**编辑 / 按模式选择**命令访问（或按 <kbd>Ctrl+S</kbd>）。该对话框会记住上次使用的模式，在下一次使用时将以该模式打开；你可以使用对话框底部的**高级**或**简单**按钮切换模式。

![](/Manual/images/media/13/select_files_-_simple.png) 

简单模式**选择文件**对话框允许你通过使用 [标准模式匹配语法](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md) 键入通配符字符串，选择当前文件列表中的文件。在上图所示的示例中，当单击**确定**按钮时， 字符串 `*.(mp3|m4a)` 将选择所有以 **.mp3** 或 **.m4a** 结尾的文件。

**部分匹配**选项允许对输入的字符串进行部分匹配 - 例如，如果该选项已启用，`kit` 将匹配 **Cute Kitten.jpg**。

单击 **高级** 按钮转到 [高级模式](advanced_selection.zh.md)，该模式允许你使用更复杂的过滤器来选择文件。