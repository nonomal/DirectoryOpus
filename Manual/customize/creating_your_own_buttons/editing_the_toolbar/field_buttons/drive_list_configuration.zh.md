# 驱动器下拉配置

**驱动器列表** 字段提供直接位于工具栏的驱动器下拉列表。可使用此下拉列表从一个驱动器切换至另一个。

![](/Manual/images/media/drive_list.png) 

通过将其拖动至工具栏来创建 **驱动器列表** 字段时，将自动分配 **curdir** 参数，使其以“当前目录”模式运行。在此模式下，Opus 将记住每个驱动器上上次使用的目录，并且如果您通过下拉列表选择了新的驱动器，则会将您带到最近使用的位置。备用模式只读所选驱动器的根文件夹，没有“当前目录”概念。您可以在 [自定](/Manual/customize/README.zh.md) 模式下编辑字段以选择此行为。

如果您将参数更改为 **curdir,rootmode**，则控件将作为两种模式的组合运行；选择新的驱动器将带您到该驱动器上的当前目录，但再次选择它（即您当前所在的驱动器）将带您到该驱动器的根目录。

![](/Manual/images/media/edit_drives_list_001.png)

从 **设置** 菜单选择 **自定**，然后右键单击过滤器字段（它将还原为一个简单框架 - 有关对此的更多信息，请参见有关 [字段按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/README.zh.md) 的讨论），选择 **编辑**，然后从 **参数** 字段中移除 **curdir** 关键字，然后单击 **确定**。

在双栏文件窗口中，驱动器列表字段通常适用于当前源文件列表。您可以使用以下参数关键字来更改此设置：

- **left**：驱动器列表字段将始终适用于双栏器文件窗口的左侧文件列表，而不是源。
- **right**：驱动器列表字段将始终适用于右侧文件列表，而不是源。
- **dest**：驱动器列表字段将始终适用于目标文件列表，而不是源。
- **nofocus**：防止受驱动器列表字段影响的文件列表获取焦点（即源/目标状态保持不变）。

下拉列表通常显示系统中的所有驱动器，但您也可以使用以下参数配置显示哪些驱动器或驱动器类型：

- **fixed**：显示固定磁盘（硬盘）。
- **network**：显示网络驱动器。
- **cdrom**：显示 CD/DVD 驱动器。
- **removable**：显示可移动驱动器（例如 USB 闪存驱动器）。
- **ramdisk**：显示 RAM 驱动器。
- **offline**：仅显示离线（断开连接）网络驱动器。
- **online**：仅显示在线（已连接）网络驱动器。
- **hideempty**：隐藏为空的可移动驱动器（无插入的介质或磁盘的驱动器）。
- **+***\<字母\>*: 仅显示指定驱动器。例如，+def 将仅在下拉列表中列出驱动器盘符 D、E 和 F。
- **-***\<字母\>*: 不显示指定驱动器。例如，-gz 将不显示驱动器 G 或 Z。

  
默认情况下，此下拉列表显示驱动器标记，但下拉控件本身不显示标记（如本页顶部所示）。如果您将关键字 **labels** 添加到按钮的 **参数** 字段，则驱动器标记也将显示在下拉控件中。 # 驱动器下拉配置 ![](/Manual/images/media/drivelist_labels.png) 您可以在 **参数** 字段中通过逗号分隔来合并多个参数关键字。例如：

**left,fixed,cdrom,-e,hideempty** - 控制左侧文件列表，仅显示固定和 CD/DVD 驱动器，不要显示驱动器 E，并隐藏所有空驱动器。

**curdir,right** - 控制右侧文件列表并跟踪每个驱动器的当前目录。