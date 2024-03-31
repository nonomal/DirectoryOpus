# 创建文件夹

使用 Opus 有两种创建新文件夹的方法。第一种方法与在资源管理器中相同 - 右键单击文件列表背景（或树状结构中的文件夹），然后选择 **新建/文件夹**。

第二种方法是使用 *创建文件夹* 对话框，您可以使用默认工具栏上的 **新建文件夹** 按钮来获取此对话框。

除了允许你新建文件夹之外，*创建文件夹* 对话框还提供一些其他功能：

- 您可以同时创建多个文件夹
- 您可以一次创建整个子树的文件夹（例如，一个文件夹、一个子文件夹、一个子子文件夹，等等，所有这些都由一个命令完成）
- 您可以一次在同一父文件夹下创建多个子文件夹
- 您可以自动导航到新创建的文件夹

##### 创建单个文件夹

![](/Manual/images/media/13/create_folder.png) 

此示例显示单个文件夹模式下的 *创建文件夹*。

名称字段下方显示的两个数字指示输入的名称长度以及创建文件夹后的路径总长度。这有助于确保路径长度不会超出 259 个字符的正常最大值 - 尽管 Opus 可以处理比这更长的路径，但很多其他程序可能会有问题。

##### 创建文件夹树

您可以通过输入以斜杠分隔的文件夹名称来一次创建整个子文件夹树。例如：

![](/Manual/images/media/13/create_sub_folders.png) 

这将在当前位置创建一个名为 *One* 的文件夹，然后在 *One* 中创建一个名为 *Two* 的子文件夹，在 *Two* 中创建一个名为 *Three* 的子文件夹，依此类推，所有操作都只需一步。

##### 同时创建多个文件夹

如果您启用 **创建多个文件夹** 选项，则可以在当前位置同时创建多个文件夹。如果启用此选项，名称字段将变为多行文本框，允许您输入任意多个名称（每行一个）：

![](/Manual/images/media/13/create_folder_multi.png)

##### 创建多个子文件夹

在上述示例中，所有新文件夹都将相对于当前文件夹创建。您还可以使用竖线字符（`|`）来分隔子文件夹名称，从而在同一子文件夹级别创建多个子文件夹。

![](/Manual/images/media/13/makedir_multi.png)

上述示例将创建两个子文件夹（*2023* 和 *2024*），并在其下方创建 12 个子文件夹（每个代表一年中的一个月）。

##### 在多个文件夹模式下使用对话框

在 **创建多个文件夹** 模式下，<kbd>Enter</kbd> 键即可移动到文本框中的新行，但您仍然可以通过在最后一行按两次 <kbd>Enter</kbd> 或在任意一行按下 <kbd>Shift+Enter</kbd> 来快速地 *确定* 对话框。由于在末尾双击 <kbd>Enter</kbd> 只需多按一个键，即使只创建一个文件夹时也是如此，因此您可能会发现一直将对话框保留在此模式很方便。

##### 自动读取新文件夹

附加到 **确定** 按钮的下拉菜单允许你选择新建文件夹后的操作。

![](/Manual/images/media/13/new_arc_-_tristate.png)

- **创建文件夹**：创建新文件夹（或文件夹），但不会读取。
- **读取文件夹**：一旦创建新文件夹，文件列表将自动导航到其中。
- **双读取**：新文件夹将在另一个文件列表中打开（如果需要，文件窗口将被置于双栏模式）。如果您要创建多个文件夹，则只会读取第一个文件夹。
- **读取新标签**：新文件夹将在新的文件夹标签页中打开。如果您要创建多个文件夹，则将为每个新文件夹创建一个新标签页。
- **读取新标签（双）**：新文件夹将在另一个文件列表中的新文件夹标签页中打开。

单击 **确定** 按钮时，您也可以按住相应的限定符键，而不是下拉菜单。