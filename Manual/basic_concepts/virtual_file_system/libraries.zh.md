# 库

库是 Windows 7 中 Microsoft 引入的一个概念。库是一个虚拟文件夹，显示其它文件夹的内容。与可存储对各个文件和文件夹的引用的文件集合不同，库会显示一个或多个文件夹的全部内容。你无法向库中添加单个文件 - 你所能做的只是更改构成该库的文件夹。你可以像使用真实文件那样处理库中的文件（复制它们、重命名它们、删除它们等）。

### 默认库

默认情况下，Windows 创建四个库 - **文档**、**音乐**、**图片** 和 **视频**。你可随时右键单击根目录中的“库”文件夹并选择 **还原默认库** 命令，以还原这些默认库。

### 库路径

库在内部使用 URL 样式路径格式引用，其前缀为 `lib://`。例如，默认图片库的路径为 `lib://Pictures/`。你可以将此类路径键入到位置字段中，或使用内部命令集中的按钮和热键，以自动化对集合的使用。例如，你可以 [设置一个按钮或热键](/Manual/customize/creating_your_own_buttons/README.zh.md) 以使用原始命令 `Go lib://Pictures` 自动导航到图片库。

除了 Opus 之外，其它程序并不能识别 `lib://` 路径系统，因此如果你想将库路径复制到剪贴板并将其粘贴到另一个程序中，你应使用 **编辑 / 其它复制 / 文件夹路径** 菜单命令，而不是复制位置字段的内容。

### 库根文件夹

根 **库** 文件夹保存你的所有库。要访问库根目录，你可以：

- 在文件夹树中单击 **库** 项目（除非你已禁用配置中的 **[文件夹树 / 内容](/Manual/preferences/preferences_categories/folder_tree/contents.zh.md)** 页面中的该选项）
- 在桌面上双击 **库** 项目（除非在 **[虚拟文件夹 / 桌面](/Manual/preferences/preferences_categories/folders/virtual_folders/desktop.zh.md)** 配置页面中已禁用此项目）
- 在 [位置字段](../the_lister/navigation/breadcrumbs_location_field.zh.md) 中从下拉菜单中选择 **库**
- 在 [位置字段](../the_lister/navigation/breadcrumbs_location_field.zh.md) 中单击并输入路径 `lib://`

### 创建新库

你可以从库根目录中使用工具栏上的 **新建文件夹** 功能来创建新库。

新创建的库最初没有成员文件夹，因此会显示为空 - 你需要使用 *属性* 对话框在库中包含一个或多个文件夹才能使用它们。右键单击你新创建的库并选择 **属性** 命令来显示该库。

### 向库中添加文件夹

成员文件夹的列表显示在 *属性* 对话框中的 **库位置** 列表中。

单击 **包含文件夹** 按钮向库中添加新的成员文件夹。当你单击 **应用** 或 **确定** 时，新成员文件夹的内容将立即出现在库中。要删除成员文件夹，请在列表中选择该文件夹并单击 **移除** 按钮。

你还可以通过文件夹的右键单击上下文菜单（使用 **包含在库中** 子菜单）向库中添加文件夹。

### 默认保存位置

每个库都有一个用于保存新文件的位置。如果库只有一个成员文件夹，那始终是保存位置。如果库有多个成员文件夹，则在 *属性* 对话框中用复选标记指示默认保存位置。要更改哪个成员为默认保存位置，请在列表中选择该成员并单击 **设置保存位置** 按钮。

### 位置列

导航到库时，文件列表将显示所有成员文件夹的统一内容。如果你的各个成员文件夹都包含文件名相同的子文件夹或文件，那么从库中查看时可能无法明显看出哪一项是哪一项。

**位置** 列可以帮助解决此问题。它显示库中每个项目的真实位置，使得判断它们的来源变得更加容易。你可以使用 **[文件夹格式](../folder_options/README.zh.md)** 对话框添加 **位置** 列（和其它列） - 或使用 **[文件夹格式](../folder_options/folder_formats.zh.md)** 系统设置库的默认格式。

### 文件夹树

如果已启用配置中的 **[文件夹树 / 内容](/Manual/preferences/preferences_categories/folder_tree/contents.zh.md)** 页面上的 **单独显示成员文件夹** 选项，则文件夹树将为每个成员文件夹显示一个额外的分支级别。这使你可以使用拖放操作将新文件保存到特定的成员文件夹中，而不是默认保存位置。

你可以通过右键单击并选择 **不在导航窗格中显示** 选项，来从树中隐藏单独的库。要将其添加回树，请使用库的 *属性* 对话框中同名的选项。