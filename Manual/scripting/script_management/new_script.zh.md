# 创​​建新脚本

*创建新脚本* 对话框通过 [脚本管理]() 对话框的 **新建** 命令访问。

![](/Manual/images/scripting/new_script.png)

- **脚本语言**：在此处从 *JScript* 和 *VBScript* 中选择。请注意，您可以在 Opus 中使用其它与 Active Scripting 兼容的脚本语言，但您需要手动创建脚本文件（只需在 `/dopusdata/Script AddIns` 文件夹中创建它们，Opus 将自动加载它们）。
- **脚本名称**：为您的脚本命名。这将显示在脚本管理对话中的脚本列表中。
- **说明**：您的脚本的更详细说明。这将在选中脚本时显示在脚本列表下方。
- **版权**：版权声明，也会显示在选定脚本的脚本列表下方。
- **创建一个包含文件脚本**：如果您想创建一个 [包含文件脚本](../script_add-ins/include_files.zh.md)，请勾选此框。
  - **共享包含文件**：如果您希望您的包含文件脚本可以轻松地被多个脚本使用，请选中此框。共享包含文件可以使用它们的单纯文件名来包含。
- **新样式命令和列**：如果您的脚本针对 Opus 12 及更高版本，请选中此框以使用较新（且更好）的脚本命令和列定义方法。
- **创建为脚本包**：脚本将作为一个 `.osp` 程序包创建，而不是作为一个单一脚本文件创建。
- **创建一个 .txt 扩展名**：如果您不是在创建一个脚本程序包，您可能希望选中此框，以便为脚本文件名添加 `.txt` 后缀（`.txt` 文件比 `.js` 文件更容易在网络上共享）。

右侧的列表使您可以选择各种 [脚本事件](/Manual/reference/scripting_reference/scripting_events/README.zh.md)，您想在您的新脚本中实现它们。Opus 将为所有选定的事件创建样板代码。如果需要，您可以稍后添加其它事件。

在事件列表的底部，是 **NewScriptCommand** 和 **NewScriptColumn** 条目。这些是脚本中要实现的命令和列的占位符。如果您启用其中一个，Opus 将提示您输入新命令或列的名称。然后它将以自己的身份添加到事件列表中，**NewScriptCommand** / **NewScriptColumn** 条目将再次可用以添加更多命令或列。您在此处指定的任何命令/列的样板代码都将自动创建。

一旦创建了新脚本，[脚本编辑器](../script_editor/README.zh.md) 将自动打开。