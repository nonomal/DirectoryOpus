# 打印文件夹

打印文件夹功能可让您打印某个目录的内容列表。除了打印到打印机之外，它还可以打印到文件或是剪贴板。在这些情况下，您可以从多种导出格式（纯文本、制表符分隔或逗号分隔）中进行选择，然后就可以将列表导入到类似 Excel 这样的程序中。

如需访问打印文件夹对话框，请从“工具”菜单选择“打印/导出文件夹列表”命令。

![打印文件夹](/Manual/images/media/print_folder.png)

打印文件夹对话框被分成三部分；**来源**（指定要打印的文件夹）、**目标**（指定打印或导出到的位置）、**格式**（指定要包含在输出中的信息）。

**来源**部分包含以下选项：

- **文件夹**：指定您要打印其内容的文件夹。在运行打印文件夹命令时，它将默认显示文件列表中当前显示的文件夹，但您可以使用“浏览”按钮更改此设置。
- **计算子文件夹大小**：如果您希望计算列表中任何文件夹的总大小，请选择此选项。如果关闭，则不会显示文件夹大小。此选项还控制当将列（如“文件计数”和“子文件夹计数”）添加到“打印文件夹”对话框的**格式**部分时，它们是否起作用。任何需要递归枚举文件夹内容的列仅当启用**计算子文件夹大小**选项时才能按预期工作。
- **平面视图**：与文件窗口的**[平面视图](/Manual/basic_concepts/flat_view.zh.md)** 模式类似，这可以打印子文件夹的内容以及选定的文件夹。通过下拉菜单，您可以选择以下模式：
  - **混合**：所有子文件夹（及其子文件夹，以此类推）的内容都显示在父级，好像目录树只是一个大的文件夹一样。
  - **混合（无文件夹）**：与**混合**相同，但仅将文件包含在列表中，不包括文件夹。
  - **分组**：将文件夹打印为嵌套树结构。子文件夹的内容将缩进显示在父文件夹下方。

- **使用过滤器**：可让您指定过滤器来控制列表中包含哪些文件和文件夹。您可以直接输入[通配符模式](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md)、从下拉菜单中选择[预先配置的过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)，或者单击“定义”按钮来[定义新过滤器。](/Manual/file_operations/filtered_operations/README.zh.md)

**目标**部分指定您希望将文件夹列表放置的位置。

- **打印机**：文件夹列表将打印到所选打印机。下拉菜单显示已安装打印机的列表，而“设置”按钮可让您配置打印机属性。
- **文件**：文件夹列表将保存到文件中。单击“浏览”按钮以指定输出文件名（或手动输入该 filename）。文件扩展名（或您在浏览对话框中为**另存为类型**下拉菜单选择选项）定义了导出的文件的格式。您可以从以下格式中进行选择：
  - **文本文件**：将文件夹列表导出到纯文本（**.txt**) 文件。
  - **逗号分隔列表**：将文件夹列表导出到逗号分隔（**.csv**) 文件。然后可以将其导入到类似 Excel 的程序中以进一步处理。
  - **制表符分隔列表**：这是**csv** 的替代格式，此格式还可以导入到 Excel 和类似软件中。

- **剪贴板**：文件夹列表将放置在剪贴板中，然后您可以像任何复制/粘贴操作一样将其粘贴到另一个程序中。**剪贴板**下拉菜单可让您从与上述**文件**选项相同的格式中进行选择。

**格式**部分定义打印输出的格式，包括包含在列表中的列。

- **编辑**：单击**编辑**按钮编辑用于打印输出的文件夹格式。这会显示一个标准的[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md) 类型的对话框，使您可以选择列、配置显示和排序选项等。
- **当前**：打印文件夹对话框会记住其格式，以供重复使用。**当前**按钮可让您使用来自您为其启动打印文件夹命令的文件列表中的文件列表对打印文件夹对话框中的格式设置进行更新。因此，如果您在文件列表中设置了特定的文件夹格式，并想打印外观相同的列表，您可以单击**当前**按钮，避免必须手动重新配置打印文件夹格式。
- **重置**：这会将格式重置为在调用打印文件夹对话框时设置的格式。这让您可以撤消对格式所做的任何更改（或如果您意外单击了**当前**按钮等）。
- **字体**：此命令可让您选择用于打印列表的字体。字体仅在打印到打印机时使用；在导出到文件或剪贴板时，字体设置被忽略。
- **列宽**：打印文件夹对话框显示格式中为打印而指定列的“预览”。通过单击标题项之间的分隔线并将它们拖动来调整大小，您可以控制每列的宽度。指定的列宽用于输出到打印机，以及使用“常规”格式将结果发送到文本文件或剪贴板时。（在使用逗号分隔或制表符分隔输出格式时，将忽略宽度设置。）

![打印文件夹 - 宽度](/Manual/images/media/print_folder_-_widths.png)

在标题下方有两行信息；第一行显示每列的宽度，第二行显示总宽度。

在打印时，宽度以“标称字符”（根据指定的字体计算的平均字符宽度）表示，您可以使用此宽度作为指南，以确保您的文件夹列表水平适合页面。

在使用“常规”格式输出到文本文件或剪贴板时，宽度是每一列使用的固定宽度字符数，并且向上取整到 8 个字符的倍数（以匹配大多数文本编辑器中的制表位）。