# Directory Opus 13 - 详细的发行说明

# 文件夹标签

- **标签上下文菜单：**
  - 现在可以通过“自定义”、“上下文菜单”、“文件夹标签上下文”来配置文件夹标签上下文菜单。您可以根据需要添加或删除项目。
  - 之前固定的菜单上的功能现在已转换成可以自行显示或隐藏的命令，在某些情况下还可以动态地更改标签，以模仿之前菜单。
  - 无需进入配置，就可以在菜单中选择标签栏的显示位置。
- **锁定的标签：**
  - （通过配置、“文件夹标签”、“锁定”进行配置。）
  - 防止关闭锁定标签的新选项。
  - 从标签中隐藏文件夹图标的新选项。
  - 从锁定标签中隐藏挂锁图标的新选项。
  - 更改锁定标签轮廓颜色的新选项。如果标签已具有轮廓颜色，则锁定颜色也会显示（无论是棋盘格图案还是色点，具体取决于标签布局）。
  - 新选项可让您选择锁定标签在切换到其他标签时是否重置到其原始文件夹，还是仅在您切换回来，然后在锁定标签已激活的情况下再次单击时才重置。
  - 在锁定标签内，如果您双击已在同一标签栏中打开的文件夹，则 Opus 会切换到现有标签，而不是打开新标签。(存在一项新选项可恢复之前的行为。)
- **标签切换器：**
  - 与 Windows <kbd>Alt+Tab</kbd> 切换器或 Visual Studio 中的 <kbd>Ctrl+Tab</kbd> 功能相似的弹出式标签切换器。
  - 配置、“文件列表”、“选项”、“标签键：”在查看器中配置标签键的行为，包括新切换器。
  - 默认情况下，<kbd>Ctrl+Tab</kbd> 显示切换器。
  - 在双栏屏窗口中，Tab（无 <kbd>Ctrl</kbd>）的默认设置是切换侧边栏。
  - 标签会记住上次激活的顺序。切换器的默认选择是之前选定的标签。这允许您通过重复按压和释放 <kbd>Ctrl+Tab</kbd> 在两个标签间切换（类似于 Alt+Tab 在 Windows 中的工作方式）。
  - 只要触发切换器的合格键（例如 <kbd>Ctrl</kbd>）之一处于激活状态，该切换器就一直保持开启。
  - 可通过按 <kbd>Esc</kbd> 或点击切换器外部来取消。
  - 在切换器中，标签键或光标键可以移动选择。松开合格键或按回车键时，突出显示的标签会激活并作为源设置。
  - 空格键可以激活选中的标签，而无需关闭切换器。
- **标签组：**
  - 文件标签组编辑器现在在“编辑格式”按钮上有一个下拉选项，允许您将格式从一个标签复制到该组中的所有其他标签。
  - 在“标签组”内的新选项“将格式设为该标签页的默认值”。设置后，指定的格式会“粘贴”到标签上，不会随着文件夹更改而发生重置（除非已保存的格式具有优先级）。
  - 覆盖文件标签组时，如果现有组两侧都有标签，但您选择“保存”而不是“保存两侧”，系统会询问您是要仅保存一侧还是全部保存。
- **其他：**
  - 配置、“文件夹标签”、“轮廓颜色”是为特定的文件夹或文件夹类型定义标签加重色新位置。（过去是通过文件夹格式完成的。现在分离以简化不相关概念的配置。）
  - 现在当屏幕上出现过多的标签时，您可以使用鼠标滚轮滚动标签栏。（之前，这只有在标签位于左侧或右侧时才有效，现在它也适用于顶部和底部。）
  - 标签宽度过大时，现在允许用户选择将标签淡出还是用“...”进行截断。
  - 现在，对于链接的标签，会在其右侧显示一个彩色链接图标，而不是替换其主文件夹图标。（链接两个标签意味着激活一个标签会自动激活另一侧的链接标签。）
  - 自动关闭可移动驱动器标签的新选项，在这些驱动器拔出时：
    - 如果关闭（默认），文件列表将转而导航到“此电脑”。
    - 如果开启，并且“在关闭最后一个标签时关闭查看器”也处于开启状态，则如果不存在其他标签，整个窗口都会关闭。
    - 无法关闭的锁定标签将会转到其锁定的文件夹，而不是“此电脑”。
    - 不再在默认情况下加载搜索结果，但它们为标签的初始文件夹。这可以通过配置、“文件夹”、“自动加载”进行更改。
    - 现在可以将查看器窗口标题配置为显示最近加载的文件夹标签组（如果有）。
    - 改进了“当单击当前选定的标签时：转到上一个标签”选项。
- **命令：**
  - 变量可告知标签菜单中的命令是哪个标签页被右键单击的：
    - `%tab_path%` -- 标签的路径。
    - `%tab_id%` -- 标签的索引。
    - `%tab_hwnd%` -- 标签的窗口句柄（十进制）。
  - `Go TABLOCK=menu` -- 动态生成标签锁定菜单。
  - `Go TABLINK=menu` -- 动态生成标签链接菜单。
  - `Go TABNAME=!edit` -- 开始重命名标签（与 PATH 结合使用可指定其他标签的索引）。
  - `Go TABCOLOR=edit` -- 编辑标签的轮廓/加重色（与 PATH 结合使用可指定其他标签的索引）。
  - `Set TABPOSITION` -- 可以指定“save”参数来更改全局配置，而不仅仅是临时移动当前窗口的标签栏。
  - 可以在标签数量和选定的标签索引根据来禁用或隐藏命令。（请参阅[其他命令](misc_commands.zh.md)。）
  - `Go TABSWITCHER` -- 显示新切换器。可绑定到鼠标按钮或备用热键。
- **求值器：**
  - 一些变量已传递到文件夹标签上下文菜单中的求值器代码。
  - `count` -- 同一侧的标签总数。
  - `countdual` -- 另一侧的标签数量。
  - `dual` -- 如果标签作为双栏的一部分，则为 True。
  - `path` -- 标签的路径（如果有）。
  - `right` -- 如果标签位于双栏的右侧（或底部），而不是位于左侧（或顶部），则为 True。
  - `sel` - 选定标签的索引，如果右击标签栏背景，则为 -1。

------------------------------------------------------------------------

下一篇：[地址栏](/Manual/release_history/opus13_detailed/location_bar.zh.md)