# 即时查找字段

即时查找字段 (*即时查找*) 是个多用途文本字段，在你输入一个键（字母或数字）时会出现在文件列表区的底部，该键未被分配给其它热键。

即时查找最初是资源管理器功能的可视化实现，让你能通过简单输入文件名的第一个或多个字母来跳转到特定文件。在其默认模式中，它执行的就是此操作，除了你能看到自己所输入的内容外，它的行为与资源管理器的相同。

除了输入内容来跳转到文件外，即时查找还有许多其它模式，其中大部分可以通过首先按下特定的键来触发。

### 调出即时查找

要启动即时查找字段，只需在文件列表区内开始输入即可（你可能需要首先让其获取输入焦点）。如果你按下的第一个键是分配的模式键中的一个，则即时查找会被设置到相应的模式，这通过其背景颜色来表示。

如果你按下的第一个键不是分配的键中的一个，则即时查找会默认为 **查找** 模式 - 这会提供与在资源管理器窗口中输入内容以跳转到特定文件相同的功能。

分配的键和默认模式可以从 **[快速键](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.zh.md)** 配置页面中进行配置。

### 查找

默认的即时查找模式；输入文件名的一部分，以跳转到当前目录中第一个匹配的文件。与你所输入内容匹配的任何名称都会在文件列表区中高亮显示，同时也会在滚动条中显示，然后将选择移动到第一个（然后是后续的）匹配名称。

即时查找的 **查找** 模式与资源管理器中传统的“输入内容来跳转到文件”功能之间有一个小区别，这个区别在你要跳过以相同字母开头的多个文件时会显现出来。

例如，在资源管理器中，如果你想要跳过所有以 `N` 开头的文件，只需按 `N N N N...` 即可在文件间跳转。

在 Opus 中，这样做实际上会搜索以“nnnnn”开头的文件。相反，要在 Opus 中跳到下一个匹配项，请按 <kbd>F3</kbd>（你可以按 <kbd>Shift+F3</kbd> 跳回到前一个匹配项）。配置中有一个选项可以将此行为更改为与资源管理器相同。你也可以在即时查找本身中按 <kbd>Ctrl+T</kbd> 来切换此设置。

默认情况下，**查找** 模式将在文件名中的任何位置匹配输入的文本，但你可以在配置中将其更改为仅在名称开头匹配。配置中还有一个选项是忽略重音符号（变音符号），这意味着按 `e` 也将匹配包含 `é` 的文件，例如。

[即时查找/查找模式](/Manual/preferences/preferences_categories/filtering_and_sorting/find_as_you_type/find_mode.zh.md) 配置页面中提供了许多控制 **查找** 模式的选项。

### 跳转

在即时查找中输入文件夹路径（例如 `C:\Windows`）或文件夹别名（例如 `/home`）以导航到该位置，而不必激活路径字段。

如果你在 **查找** 模式中输入的内容被识别为文件夹路径或别名的开头，则即时查找将切换到 **跳转** 模式。然后，即时查找将像一个路径字段，在你按下回车时提供自动路径补全并导航到指定的路径，其优势在于无需首先激活路径字段便可立即开始输入路径。你甚至可以根据需要从工具栏中移除路径字段。

### 命令

默认键：`>`。输入命令并立即执行，而不必设置按钮。

**命令** 模式让你能够输入命令并立即执行。你可以运行任何 Opus 内部命令或启动外部程序。任何你可以通过按钮或热键运行的功能都可以作为临时命令通过即时查找运行。

你也可以在命令中使用任意 [外部控制代码](/Manual/reference/command_reference/external_control_codes/README.zh.md)。作为输入命令时的快捷方式，你还可以按 <kbd>Ctrl+Enter</kbd> 以自动在命令行中插入任何选定文件的名称。命令模式记录了你最近执行的命令历史记录 - 按 <kbd>向上</kbd> 或 <kbd>向下</kbd> 光标键以访问它。

### DOS 命令

默认键：`?`。类似于命令模式，但命令将在 DOS 窗口中运行，让你查看任何文本输出。

**DOS 命令** 模式与 **命令** 模式非常相似，不同之处在于它允许你运行 DOS 命令，并将显示一个 DOS 窗口，显示任何此类命令的输出。

### Everything（本地）

默认键：`-`。使用 ([Everything](https://www.voidtools.com)) 执行本地 [快速搜索](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md)。

假设已安装了 voidtools 的 *Everything*，则此模式将在当前文件夹下执行索引搜索。

### Everything（全局）

默认键：`+`。使用 ([Everything](https://www.voidtools.com)) 执行全局 [快速搜索](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md)。

假设已安装了 voidtools 的 *Everything*，则此模式将在所有索引位置执行全局索引搜索。

### 过滤

**过滤** 模式让你过滤显示内容，以排除所有与你输入的文本或通配符模式不匹配的项目。

> [!NOTE]
> 默认情况下，**过滤** 模式并未启用即时查找- 相反，[过滤栏](../searching_and_filtering/filter_bar.zh.md) 用于执行类似功能。专用的过滤栏具有额外的功能，使其在这项任务中比即时查找更强大。

你可以通过在 [快速键](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.zh.md) 配置页面上为其配置一个键来启用即时查找中的过滤模式。

要反转过滤（即隐藏所有与字符串不匹配的文件），请在开头输入波浪号字符（~）。

如果你已使用即时查找（或过滤栏）过滤了显示内容，则可以通过按 <kbd>Esc</kbd> 键来快速清除过滤并重新显示原始内容。

### Opus 搜索

默认键：`'`。使用 Opus 查找工具执行 [快速搜索](/Manual/basic-concepts/searching_and_filtering/windows_search.zh.md)。

使用 Opus 的内置查找文件功能在当前文件夹下进行搜索。

如果输入了纯字符串或通配符，则将其视为通配符名称匹配。如果输入的字符串以 `=` 开头，则它将被 [求值器](/Manual/evaluator/README.zh.md) 处理，并且可以执行更复杂的查询（例如 `=size>100kb`）。

### 范围

默认键：`#`。让你通过索引选择一系列文件。

**范围** 模式仅在文件列表区处于详细信息或高级模式时使用。它允许你通过索引或一系列索引选择文件。如果你在使用此模式时尚未显示 **索引** 列，则会自动添加它（并在即时查找字段关闭时再次将其移除）。

范围给出以下格式 `#a-b`，例如 `#5-10` 将选择 5 到 10 之间的文件。你也可以选择单个文件 - `#5` 仅选择 5 号文件。你可以使用逗号组合一个或多个单独的数字和范围。例如，`#12,14,16-18` 将选择 12、14、16、17、18 号文件。
您还可以基于当前焦点位置选择一个范围。例如，**\#+10** 将从当前位置选择后面 10 个文件，**\#-5** 将选择前面 5 个文件。您还可以使用例如 **\#-5+5** 选择任一边的 5 个文件。

### 文件夹

默认键：`]`。显示从各种来源绘制的文件夹弹出列表（例如最近使用的文件夹、收藏夹和别名）。

您可以从 [即时查找/ 文件夹模式](/Manual/preferences/preferences_categories/filtering_and_sorting/find_as_you_type/folders_mode.zh.md) 配置页面选择来源。

### Windows 搜索

默认键：`=`。在当前文件夹下方执行 Windows 搜索索引搜索。

**搜索** 模式允许您在当前文件夹内发起索引 [Windows 搜索](../searching_and_filtering/windows_search.zh.md)。它相当于在工具栏搜索字段中输入搜索字符串 - 但如果您希望移除搜索字段以节省工具栏空间，您仍然可以通过即时查找访问搜索功能。

### 选中

默认键：`:`。通过输入通配符模式选中文件。

**选中** 模式允许您选中当前文件夹中与您输入文本匹配的所有项目。

匹配会自动在 *部分匹配* 模式下执行 - 这意味着您可以输入子字符串或完整的通配符模式来匹配。例如，要快速选中所有 JPEG 文件，您可以输入 `:*.jpg` 也可简单地输入 `:.jpg`（不过后者还将匹配包含 `.jpg` 作为文件名或扩展名的任何文件）。要反转选择（即选中与字符串不匹配的所有文件），请在开头输入波形字符 (`~`)。

### 标签页

默认键：`@`。按路径或标题搜索并切换到已打开的文件夹标签页。

**标签页** 模式允许您按文件夹路径和标签页标题搜索所有已打开的文件夹标签页。匹配会自动在 *部分匹配* 模式下执行 - 这意味着您可以输入子字符串或完整的通配符模式来匹配。

匹配的标签页将显示在弹出列表中，您可以从列表中选择某个匹配的标签页来切换到它（可使用鼠标或键盘）。

### WSL 命令

默认键：`|`。在 shell 窗口中运行 Linux 命令。

如果已从 Windows 商店安装了适用于 Linux 的 Windows 子系统，则**WSL 命令** 模式允许您在 Linux shell 中运行 Linux 命令，就像可以在 DOS 窗口中运行 DOS 命令一样。