# 查看器窗格

查看器窗格是一个集成的图像和文档查看器，它可以在文件窗口中显示。当它被启用时，它将自动显示（如果可能）最近选定文件的内容。它提供了非常快速的文件预览方式 - 只需导航到相关文件夹，然后点击文件即可显示。使用光标键，您可以轻松地移动穿梭于文件列表，查看文件内容。

![](/Manual/images/media/13/viewer_pane.png)

### 访问查看器窗格

在文件窗口中显示查看器窗格的最简单方法是用默认工具栏上的 ![](/Manual/images/media/13/menu_toolbar_-_viewer_pane.png) 按钮。您还可以按 <kbd>F7</kbd>，或从 **文件窗口** 下拉菜单中选择 **查看器窗格** 命令。

### 查看文件

在查看器窗格显示的情况下，查看文件就像在文件列表中选择它一样简单。Opus 本机可以显示许多类型的图像文件，并带有 [插件](/Manual/preferences/preferences_categories/viewer/viewer_plugins.zh.md) 来显示常见文档格式，如 Word 和 PDF 文件（只要系统中安装了合适的查看器）。查看器窗格的标题栏显示当前查看的文件的名称，以及一些关于它的信息 - 如果它是图像格式，它通常会显示分辨率和图像类型。对于需要使用插件的文件，通常会显示插件的名称。

### 查看器窗格标题栏

![](/Manual/images/media/13/viewerpane_titlebar.png)

查看器窗格的标题栏中有许多按钮：

- **前一个文件**：将文件列表中的选择移动到前一个文件（并在查看器窗格中显示）。
- **下一个文件**：将选择移动到下一个文件。
- **向左旋转**：将当前显示的图像向左旋转 90 度。请注意，这不会修改磁盘上的图像 - 旋转不是永久的，它只影响查看器窗格中的当前显示。如果您想要永久旋转图像，可以使用 **[图像转换](/Manual/additional_functionality/image_conversion/README.zh.md)** 功能。
- **向右旋转**：将当前显示的图像向右旋转 90 度。
- **放大**：放大（显示较大）当前显示的图像。您也可以通过按住 <kbd>Ctrl</kbd> 键并转动鼠标滚轮来放大。
- **缩小**：缩小当前显示的图像。您还可以通过按住 <kbd>Ctrl</kbd> 键并转动鼠标滚轮来缩小。
- **原始大小**：以其原始（完整）大小显示当前图像。
- **适应窗口**：缩放图像以适应窗口的大小。此设置仅将较大的图像缩小以适合窗口 - 它不会将小于窗口的图像放大。
- **扩展到窗口**：缩放图像以匹配窗口的大小。与 **适应窗口** 相比，此设置将放大一个较小的图像以填充窗口，以及缩小一个较大的图像。
- **切换布局**：这将在查看器窗格的垂直（显示在文件窗口的右侧，如上图所示）和水平（显示在文件窗口的底部）之间切换布局。
- **关闭**：关闭查看器窗格。

**滚动查看器**

在查看器窗格上使用**鼠标滚轮**将上下移动图像和文档（如果适用，并假设第三方查看器不会将滚轮用于其它用途）。按住 <kbd>Alt</kbd> 键，您还可以使用 Opus 的内置图像查看器和支持它的插件，使用鼠标滚轮向左和向右滚动。

### 控制栏

![](/Manual/images/media/13/viewerpane_controlbar.png)

除了标题栏中的按钮之外，您还可以打开查看器底部的控制栏。**显示控件栏** 选项在配置中的 **[查看器 / 查看器窗格](/Manual/preferences/preferences_categories/viewer/viewer_pane.zh.md)** 页面上。

控制栏中的按钮是：

- **前一个文件**：将文件列表中的选择移动到前一个文件（并在查看器窗格中显示）。
- **下一个文件**：将选择移动到下一个文件。
- **向左旋转**：将当前显示的图像向左旋转 90 度。请注意，这不会修改磁盘上的图像 - 旋转不是永久的，它只影响查看器窗格中的当前显示。如果您想要永久旋转图像，可以使用 **[图像转换](/Manual/additional_functionality/image_conversion/README.zh.md)** 功能。
- **向右旋转**：将当前显示的图像向右旋转 90 度。
- **放大**：放大（显示较大）当前显示的图像。您也可以通过按住 <kbd>Ctrl</kbd> 键并转动鼠标滚轮来放大。
- **缩小**：缩小当前显示的图像。您还可以通过按住 <kbd>Ctrl</kbd> 键并转动鼠标滚轮来缩小。
- **原始大小**：以其原始（完整）大小显示当前图像。
- **适应窗口**：缩放图像以适应窗口的大小。此设置仅将较大的图像缩小以适合窗口 - 它不会将小于窗口的图像放大。
- **扩展到窗口**：缩放图像以匹配窗口的大小。与 **适应窗口** 相比，此设置将放大一个较小的图像以填充窗口，以及缩小一个较大的图像。
- **十六进制视图**：这将当前文件列表切换为十六进制视图。十六进制视图使用提供的文本插件（在十六进制模式中）来显示文件的二进制内容。再次单击该按钮以切换回图像的常规显示。
- **幻灯片放映**：此按钮启用幻灯片放映模式。Opus 将在当前文件夹中开始播放文件（在查看器窗格中）的幻灯片放映，从当前选择开始。您可以从配置中的 **[查看器 / 查看器窗格](/Manual/preferences/preferences_categories/viewer/viewer_pane.zh.md)** 页面来调整幻灯片放映的速度。
- **全屏**：此命令清理查看器窗格中当前的文件，并在全屏模式下的 [独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中重新打开它。您可以通过按 <kbd>Enter</kbd> 键来离开全屏模式（并留在独立查看器中），或按 <kbd>Esc</kbd> 键来关闭单独的查看器并返回到文件窗口。
- **打印**：可打印当前查看的图像或文档。
- **设置**：这是一个快捷方式，它将带您到配置中的 **[查看器 / 查看器窗格](/Manual/preferences/preferences_categories/viewer/viewer_pane.zh.md)** 页面。

### 并非所有插件都支持所有功能

根据用于查看特定文件的插件（如果有），并非所有上述功能都受支持。例如，有些插件可能不支持旋转显示，在这种情况下，向左旋转和向右旋转函数将不可用。

### 查看器窗格上下文菜单

![](/Manual/images/media/13/viewer_pane_context_menu.png)

查看器窗格还有一个上下文菜单 - 虽然它也会根据插件而有所不同，但它可以通过右键单击当前显示的图像来访问。
在上下文菜单中可用的命令：

- **查看大小**：这可用于更改当前显示图像的放大倍率 - 提供各种预设级别以及上述两种“适合”模式。还提供了 **平铺** 图像的选项。
- **旋转视图**：旋转当前显示的图像。
- **伽玛校正**：调整当前图像的伽玛校正 - 如果需要补偿较暗或较亮的显示器，这很有用。
- **背景颜色**：对于具有透明度的图像，这允许您在黑色和白色以及配置中的任何默认值之间切换背景颜色。
- **全选**：选择整个图像以复制到剪贴板。您还可以使用鼠标选择图像的区域 - 默认情况下，您需要按住 <kbd>Shift</kbd> 键并单击并拖动以选择图像的矩形部分。如果您禁用 **[查看器窗格](/Manual/preferences/preferences_categories/viewer/viewer_pane.zh.md)** 配置页面上的 **用鼠标左键滚动** 选项，那么您无需按住 <kbd>Shift</kbd> 键。
- **重新选择**：如果您选择一个区域然后清除该选择，这将重新选择您之前选择的区域。
- **全部复制**：将整个图像复制到剪贴板。当选择了图像的一个区域（如 **全选** 命令中所述或如上使用鼠标所述）时，此命令会更改为 **复制**，且仅复制所选区域。
- **打印**：打印当前显示的图像。
- **设置为桌面墙纸**：将图像设置为您的桌面墙纸。您可以从子菜单中选择多种墙纸样式。
- **属性**：显示当前显示图像的属性。
- **刷新**：刷新图像。如果图像或文档在后台不断修改（例如日志文件），这可能很有用。
- **使用插件**：这使您可以修改正在显示图像的插件（如果有）。当然，并非所有插件都能处理所有类型的文件，但您可能会安装多个可以处理同一文件的插件，因此此菜单可以试验在它们之间切换。您可以在配置的**[查看器/查看器插件](/Manual/preferences/preferences_categories/viewer/viewer_plugins.zh.md)**页面中修改用于插件的默认顺序（以及控制各个插件的设置）。
- **文件**：这会显示当前显示文件的标准系统上下文菜单。