# 重复文件查找器

此工具可让您在驱动器中搜索重复文件。此功能具有两种不同的模式：

1. 搜索多次出现的所有文件（即*全部*重复文件）。
2. 搜索一个或多个特定文件的副本。

要访问重复文件查找器，从**工具**菜单中选择**查找重复文件**命令。重复文件查找器显示在文件窗口底部的[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)中。

重复文件查找器面板的顶部部分可让您指定搜索位置。您可以一次搜索一个或多个文件夹（或整个驱动器），方法是在**查找位置**列表中添加条目。

![](/Manual/images/media/dupe_files_1.png)

列表中的每个条目都对应一个要搜索的文件夹。要将文件夹添加到列表，请双击*添加要搜索的文件夹*项。您还可以使用工具栏上的**选择要搜索的文件夹**(![](/Manual/images/media/dupe_files_-_select.png))按钮 - 此按钮会显示带有复选框的文件夹选择对话框，以便您可以同时选择多个文件夹。您可以通过双击列表中的文件夹路径来编辑路径（或选择它并按 **F2**，如果您想使用键盘输入路径）。

要从列表中删除文件夹，请选择它并单击**删除文件夹**(![](/Manual/images/media/dupe_files_-_delete.png))按钮。**重置文件夹列表**(![](/Manual/images/media/dupe_files_-_reset.png))按钮会清除文件夹列表，而**锁定文件夹**(![](/Manual/images/media/dupe_files_-_lock.png))按钮会将**查找位置**锁定到当前文件列表中显示的文件夹。当文件夹被锁定时，每当您在文件列表中导航时，**查找位置**列表将自动重置到当前位置。

面板的底部部分可让您指定要搜索重复文件的对象。如果此列表为空，查找器将搜索*所有*重复文件（模式一）。如果您在此列表中指定一个或多个文件，查找器将只搜索这些文件的副本（模式二）。

![](/Manual/images/media/dupe_files_2.png)

列表中的每个条目都代表查找器将搜索其副本的文件。要将文件添加到列表，请双击*添加要搜索重复项的文件*项，或单击工具栏上的**浏览**(![](/Manual/images/media/dupe_files_-_browse.png))按钮。您可以通过双击列表中的文件路径来编辑路径（或选择它并按 **F2**，如果您想手动输入路径）。使用**删除文件**(![](/Manual/images/media/dupe_files_-_delete_file.png))按钮从列表中删除文件，并使用**清除文件列表**(![](/Manual/images/media/dupe_files_-_reset_files.png))按钮清除它。

面板的右侧包含可用于控制 Opus 搜索重复文件的选项。

- **显示结果：**这可让您指定搜索结果显示其中的[文件集](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)的名称。搜索开始后，当前的文件列表将自动导航以显示此集合，且在查找文件时，它们将出现在显示中。显示将自动分组以使重复文件保持在一起。如果指定的集合不存在，则会自动创建该集合。
- **比较方法**下拉列表可让您指定 Opus 用于确定两个文件是否为重复文件的比较方法：
  - **仅文件名：**此比较仅基于文件名。如果两个文件具有相同名称，则将它们视为重复文件。
  - **文件名（无扩展名）：**此选项会搜索具有相同文件名主干的文件，而忽略其文件扩展名。例如，“grandma.mp3”和 “grandma.jpg”将匹配。
  - **文件名和大小：**此比较基于文件名和大小。如果两个文件具有相同名称并且大小相同，则将它们视为重复文件。
  - **大小：**此比较仅基于文件大小。如果两个文件具有相同大小，则将它们视为重复文件。
  - **MD5 校验和：**此方法是最慢但最准确的比较方法。此方法不考虑文件名；相反，对于任何两个文件，Opus 首先比较其大小。如果大小相同，Opus 会为两个文件计算 MD5 校验和；如果校验和匹配，则这两个文件被视为重复文件。您可以使用**MD5 准确性**滑块来降低比较准确性并加快搜索速度。
- **清除以前的结果：**如果此选项打开，**显示结果**文件集合的内容将在搜索开始前自动清除。
- **删除模式：**如果您搜索重复文件的原因是要消除浪费空间，此模式可能会派上用场。当此选项打开，并且您执行搜索时，显示结果的文件列表将自动进入[复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)。搜索完成后，Opus 将自动选择每个重复文件组的第一个文件除外的所有文件。然后，您可以使用面板底部的**删除**按钮来删除已标记的文件。**选择**按钮可让您重新运行删除选择流程，而无需重新运行搜索。如果要对列表重新排序以影响要删除的文件，此功能可能很有用。
- **过滤器：**过滤器字段可让您定义过滤器以控制要搜索的文件和位置。您可以通过两种方式使用此功能：
  - 您可以输入[简单通配符模式](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md)来控制重复搜索将考虑哪些文件。例如，输入 **\*.jpg** 以仅搜索重复的**JPG**文件。
  - 您可以单击**定义过滤器**按钮 (![](/Manual/images/media/dupe_files_-_filter.png))以使用高级过滤器控件来定义过滤器（或使用下拉列表选择以前保存的过滤器）。您可以使用它来指定要搜索的文件以及控制（使用**子文件夹**条款）要搜索的子文件夹。请参见[过滤操作](/Manual/file_operations/filtered_operations/README.zh.md)页面了解有关过滤器的更多信息。
- **对重复组编号：**重复文件查找器针对找到的每组重复文件创建组，且通常将这些组以用于重复搜索的条件来命名。如果您打开此选项，则每组重复文件将被编号（从 1 到 *X*，按其找到的顺序）。
- **在压缩包内搜索：**此功能还将搜索在指定位置中找到的任何压缩包文件的内容。
- **在子文件夹内搜索：**此功能将搜索指定位置的所有子文件夹的内容以及位置本身。您可以使用下面的**过滤器**选项来控制要搜索的子文件夹。
- **MD5 准确性：**根据校验和搜索时，您可以选择仅计算文件百分比的哈希。这可让您以准确性为代价加快大型文件的操作速度。使用滑块控件将百分比从 1% 调整到 100%。
![](/Manual/images/media/md5_accuracy.png)

- **使用 MD5 缓存**: 对位于 NTFS 分区上的大文件使用 MD5 校验和缓存。如果计算了大文件的校验和，它将会被缓存，如果文件看似没有改变，将未来使用缓存值。

在为重复项搜索指定了位置和参数后，单击 **查找** 按钮以开始。

使用 **删除模式** 选项时，可以在删除任何选定的重复文件时覆盖主偏好设置回收站。

![](/Manual/images/media/dupe_delete.png)

位于面板右下方的 **删除** 按钮附带有下拉菜单，它可让你选择你希望如何删除重复文件。