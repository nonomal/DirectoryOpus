# 复选框模式

复选框模式是一种模式，可以在文件列表中启用（它不是像 [单击模式](single-click_mode.zh.md) 那样的全局设置），在每个项目旁边显示复选框。

![](/Manual/images/media/13/check-box_2.png) 

复选框模式可以通过 **文件夹** 下拉菜单中的命令来启用。它是 [文件夹格式](/Manual/basic_concepts/folder_options/README.zh.md) 的一部分，可以使用文件夹格式系统永久启用某些文件夹的复选框模式。

### 复选框模式的作用

复选框模式改变了在文件操作中考虑的文件（比如，当你点击 **复制文件** 按钮时）：

- 通常情况下（不在复选框模式时），**复制文件** 等功能的作用对象是所有 ***选定的*** 文件。
- 在复选框模式时，**复制文件** 等功能的作用对象是所有 ***勾选的*** 文件。

所以，在上面的截图中，点击 **复制文件** 按钮将把文件 **IMG2154.JPG** 和 **Spectrum.mp3** 复制到目标位置，但不会复制 **What's New.docx**。

### 更容易选择文件

复选框模式的主要好处在于它提供了视图模式中的选择持久性，在这些模式中通常很容易意外地取消文件选择。点击文件列表的空白区域（或者确实，点击任何文件）仍然会导致取消所有文件的选中，但它们的 *勾选状态* 不会受到干扰。这一个实际结果是，你可以双击一个文件来打开它，或者选择文件并拖放它们，而无需修改列表中任何其它文件的勾选状态。

### 使用复选框模式：案例研究

让我们看一个实际案例：想象一下，你想要浏览一个包含你度假照片的文件夹，找出你想要发送给朋友的照片。

1.  在文件列表中打开复选框模式，然后通过点击工具栏中的按钮（或按下 <kbd>F7</kbd>）打开 [查看器窗格](../../the_lister/viewer_pane.zh.md)。
2.  点击文件夹中的第一个文件以选择它。它将显示在查看器窗格中。
3.  如果你要保留该图片，就用鼠标点击它的复选框（或者，按下 <kbd>空格</kbd> 键）以勾选它。
4.  点击文件夹中的下一张图片（或者，按下 <kbd>向下</kbd>）以预览下一张图片，以此类推。

在这一过程的最后，你将浏览文件夹中的所有图片，而你想要保留的图片仍然会被勾选。然后，你可以使用 **复制文件** 将它们复制到另一个文件夹（或者，使用 **编辑 / 反转选择** 命令反转勾选状态，然后删除你不想保留的文件）。

如果没有复选框模式，你将不得不边查看边复制或删除每个文件 - 通过这种方式，你可以专注于查看图片，然后在最后批量复制或删除它们。

### 需要记住的要点

关于复选框模式，需要记住的主要要点如下：

- 在复选框模式下，通常对选定文件起作用的功能将对勾选的文件起作用。
- **编辑 / 全选** 或 **编辑 / 反转选择** 等选择命令将影响文件的勾选状态，而不是选定状态。
- 你可以双击一个文件打开它，而不会丢失其它文件的勾选状态。
- 拖放仍然适用于选定文件，而不是勾选文件。
- 按下 <kbd>空格</kbd> 切换所有当前选定文件的勾选状态。

### 从选择到复选框，再返回选择

**编辑 / 不同选择** 菜单中有两个命令，在复选框模式下很有用：

- **选择到复选框**：此命令将每个文件的当前选择状态复制到其勾选状态（因此，选定的文件将被勾选，未选定的文件将不被勾选）。如果你在运行此命令时文件列表不在复选框模式，它将自动打开。如果你已经开始选择多个文件并决定复选框模式是完成任务的更好方法，这可能很有用。
- **复选框到选择**：上述命令的反向操作 - 每个文件的当前勾选状态将被复制到其选择状态。如果你已经勾选了一些文件，然后想选择它们进行拖放，这很有用。

### 复选框模式的另一种用途

[独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中的 [图像标记](/Manual/additional_functionality/viewing_images/image_marking.zh.md) 功能可以使用复选框模式（如果关闭了使用文件集合的默认选项）。 当你通过此模式中的查看器对文件进行标记时，它所在的文 件显示将自动放入复选框模式，并且所讨论的文件将被勾选。