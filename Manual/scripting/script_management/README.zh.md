**脚本管理**

*“脚本管理*”对话框会显示你所安装的所有 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)。你可以创建新脚本或从这里管理你的现有脚本。

要转到“脚本管理”对话框，请使用默认“设置”菜单中的 **脚本** 命令。如果你使用的是未包含该命令的旧工具栏，可以从**自定义/默认工具栏**标签页中添加它。原始命令是 `Prefs SCRIPTS`。

**脚本列表**

已安装的脚本会显示在列表中，其中有数列：

- **名称**：脚本的名称（由脚本本身设定）。你可以使用其名称前面的复选框禁用脚本。
如果脚本有配置选项，它会以齿轮图标显示 - 你可以点击这个图标，或使用工具栏中的 **配置** 按钮编辑配置。

- **状态**：表示脚本是否已成功加载，或是否遇到错误。
- **版本**：脚本的版本号（由脚本本身设定）。
- **文件**：实现该脚本的文件名称。

脚本可以在其初始化中指定一个组 - 如果有任何脚本执行此操作，脚本列表将被分成两个或更多个组。

默认情况下，[包含文件脚本](script_add-ins/include_files.zh.md) 也显示在列表中，但是你可以使用 **文件** 菜单中的命令隐藏它们。

**安装新脚本**

安装新脚本最简单的方法是使用 **文件 > 安装** 命令（或点击工具栏中的 **安装** 按钮）。

[脚本安装程序](/Manual/scripting/script_management/installer.zh.md) 会打开以指导你完成安装过程。你可以通过这种方式安装单个脚本文件（例如 `.js` 或 `.js.txt`）、脚本程序包（`.osp` 文件）和脚本安装文件（`.opusscriptinstall` 文件）。

**创建新脚本**

点击 **新建** 按钮创建新脚本。*“[创建新脚本](/Manual/scripting/script_management/new_script.zh.md)*”对话框将打开。

**脚本管理**

从列表中选择一个脚本以查看对话框底部的相关信息。

你可以右键点击脚本，或使用 **脚本** 下拉菜单管理选定的脚本。其中一些功能也可以在工具栏上找到。

- **启用** / **禁用**：允许你启用或禁用脚本，与点击其名称前面的复选框效果相同。
- **关于**：显示有关脚本的信息（如果脚本提供）。
- **配置**：配置脚本参数（如果脚本有的话）。
- **编辑**：打开 [脚本编辑器](script_editor/README.zh.md) 来编辑脚本。
- **转换为程序包**：将独立的脚本文件转换为 [脚本程序包](script_add-ins/script_package.zh.md)。
- **分享**：将脚本转换为 [脚本安装文件](/Manual/scripting/script_management/installer.zh.md) 以与其它 Opus 13 用户分享。
- **删除**：删除选定的脚本。