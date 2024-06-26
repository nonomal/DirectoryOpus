# 标签

Directory Opus 允许在文件窗口的每个文件列表中支持多个标签，这意味着您可以同时打开多个文件夹，并且可以在它们之间快速切换以比较内容、从一个文件夹将文件复制或移动到另一个文件夹中，或者仅仅快速访问多个位置。

![](/Manual/images/media/13/tabs_-_make_default_001.png) 

在上面的屏幕截图中，打开了两个标签 - 可见标签显示了 **已保存的图片** 文件夹，不可见标签（如果您切换到它）显示了 **图片** 库。

要切换标签，只需单击您希望激活的标签即可。使用键盘时，您可以按 <kbd>Ctrl+向左</kbd> 和 <kbd>Ctrl+向右</kbd> 从一个标签移动到下一个标签。您还可以通过按 <kbd>Ctrl+Tab</kbd> 使用 [标签切换器](/Manual/basic_concepts/the_lister/tabs/tab_switcher.zh.md)。

默认情况下会启用文件夹标签 - 即使实际上只打开了一个标签，*标签栏* 也会显示在文件列表的底部（或者在双栏文件窗口中显示在每个文件列表的底部）。**[文件夹标签](/Manual/preferences/preferences_categories/folder_tabs/README.zh.md)** 配置类别中包含许多选项，允许您控制文件夹标签系统。例如，您可以将其配置为仅当打开多个标签时才显示标签栏，或者在文件列表的左侧或右侧垂直显示标签。

### 打开新标签

有多种方式可以打开新标签。

- 单击显示在最后一个标签右侧的 `+` 按钮。
- 双击标签栏的空白部分（`+` 按钮的右侧）。
- 右键单击文件夹，然后从上下文菜单中选择 **在新文件夹标签中打开**。
- 双击文件夹时按住 <kbd>Alt</kbd> 键，在新标签中将其打开。

您可以从 [文件夹标签 / 文件夹标签栏](/Manual/preferences/preferences_categories/folder_tabs/folder_tab_bar.zh.md) 配置页面配置这些内容（例如，您可以关闭 `+` 按钮，或更改默认打开的文件夹）。

<kbd>Alt</kbd> 双击行为是通过 [文件类型](/Manual/file_types/README.zh.md) 系统配置的。

### 标签颜色

标签可以单独着色，以便更容易识别。如果您右键单击文件夹标签，便可以从上下文菜单中选择 **设置标签颜色** 命令，该命令允许您更改颜色。

![](/Manual/images/media/13/colorful_tabs.png)

### 标签组

文件夹标签组是预定义标签（文件夹）的集合，可以在同一操作中打开。例如，你可能有一组特定项目的工作文件夹，你总是需要快速访问。您可以定义一个打开文件夹标签中所有文件夹的标签组，然后当您准备好处理该项目时，您只需要在该组中选择即可打开所有这些文件夹。

标签组会保留您分配给各个标签的颜色和名称。

您可以从 [文件夹标签 / 组](/Manual/preferences/preferences_categories/folder_tabs/groups.zh.md) 配置页面创建和管理标签组。

### 默认菜单命令

![](/Manual/images/media/13/tab_menu.png)

默认工具栏中的 **文件夹 / 文件夹标签** 菜单包含用于控制标签的命令：

- **当前的新标签**：在新标签中打开当前文件夹。
- **父项的新标签**：在新标签中打开当前文件夹的父项。
- **选定的新标签**：在新标签中打开任何选定的文件夹（例如，选中当前文件夹中的三个子文件夹并运行此命令，将导致打开三个新标签，显示这些文件夹）。
- **父级的标签**：在新标签中打开任何选定项目的父项。这在集合（例如查找结果）中非常有用，其中所选项目的父项不一定是当前文件夹。
- **关闭标签**：关闭当前文件夹标签。
- **撤消关闭标签**：重新打开最近关闭的文件夹标签。
- **管理标签组**：将配置打开到 [标签组](/Manual/preferences/preferences_categories/folder_tabs/groups.zh.md) 页面。
- **保存标签**：将当前源文件列表中的标签另存为标签组。
- **保存标签（两侧）**：将来自两个文件列表的标签另存为单个标签组。

### 使用鼠标操作标签

您可以通过以下方式使用鼠标操作文件夹标签：

- 您可以通过单击左键在标签之间切换。
- 使用左键双击标签将关闭标签（可以通过配置禁用此功能）。
- 您还可以使用鼠标中键单击标签以关闭标签。
- 从当前文件夹中将文件拖动到另一个标签上，将复制或移动它们到该标签的文件夹。如果您在不释放鼠标按钮的情况下将鼠标悬停在另一个标签上，该标签将处于活动状态，这允许您将文件放入该标签内的子文件夹中。
- 您还可以拖放文件夹标签本身 - 这可以让您更改它们在文件列表中出现的顺序，您还可以通过这种方式将标签从一个文件列表移动到另一个文件列表（或从一个列表移动到另一个列表）。通过在拖放标签时按住 <kbd>Ctrl</kbd> 键，您可以创建标签的副本。您还可以将标签从列表中拖出并将其放在桌面上，以便在新列表中打开文件夹。
- 标签通常显示它们显示的文件夹的名称，但是如果您单击当前活动标签的标签上的左键，您可以为标签分配自己的名称。一旦标签分配了名称，即使您更改标签中的文件夹，它也不会更改。
- 右键单击标签会显示标签的上下文菜单。

### 文件夹标签上下文菜单

![](/Manual/images/media/13/tab_context_menu.png)

右键单击文件夹标签以查看其上下文菜单。请注意，菜单中的命令会因您处于单显示模式还是双栏模式而异。还可以通过 [自定义](/Manual/customize/README.zh.md) 系统编辑菜单。

- **组**：此子菜单允许您访问您已定义的任何 [标签组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md)。您还可以使用它将当前标签集另存为一个新组。
  从该菜单中选择一个组时，您可以按住 <kbd>Shift</kbd> 或 <kbd>Ctrl</kbd> 键来覆盖标签组的 **关闭现有文件夹标签** 设置；<kbd>Shift</kbd> 意味着不会关闭现有标签，<kbd>Ctrl</kbd> 意味着将关闭标签。

- **打开新标签**：使用配置中的设置打开新标签。
- **复制标签**：打开当前标签的副本。
- **在右侧复制标签**：打开当前标签的副本，在另一个文件列表中（取决于您从哪个文件列表访问该命令，“右侧”可能是“左侧”、“上方”或“下方”）。
- **将标签移动到右侧**：将当前标签移动到另一个文件列表。
- **将父项作为标签打开**：在新标签中打开当前文件夹的父项。
- **在新文件窗口中打开**：在新文件窗口中打开标签的文件夹。
- **拆分为双栏**：切换到双栏模式，并将此标签和任何后续标签拆分为新打开的显示。
- **拆分到新文件窗口**：将此标签和任何后续标签拆分为一个新文件窗口（关闭现有标签，打开一个新文件窗口，并在新文件窗口中重新打开标签）。
- **重命名标签页**：为标签页指定您自己的名称。
- **设置标签页颜色**：为标签页指定颜色以便更容易识别。
- **锁定标签页**：锁定或解锁标签页 - 有关锁定标签页的更多信息，请参见下方。
- **链接标签页**：链接或取消链接标签页 - 有关链接标签页的更多信息，请参见下方。
- **关闭左侧标签页**：关闭此标签页左侧的所有标签页。（除非您在选择此选项时按住 <kbd>Shift</kbd> 键，否则不会影响锁定的标签页。）
- **关闭右侧标签页**：关闭此标签页右侧的所有标签页。（锁定的标签页：如上所示。）
- **关闭所有其它标签页**：关闭此标签页之外的所有打开的标签页。（锁定的标签页：如上所示。）
- **关闭标签页**：关闭此标签页。（如果标签页已锁定并且已禁用关闭锁定的标签页，则仅当您在打开菜单时按住 <kbd>Shift</kbd> 键时才会显示此标签页。）
- **位置**：更改标签页栏的位置。
- **设置**：提供指向配置中的标签页栏设置的快速链接。

### 自定义标签页标签

当您自定义标签页的标签（通过重命名它）时，可以使用几个特殊的“标记”在标签页标签中插入信息：

|          |                                                                             |
|----------|----------------------------------------------------------------------------|
| **%P**     | 当前文件夹的完整路径                                               |
| **%N**     | 当前文件夹的名称                                                    |
| **%R**     | 当前文件夹的驱动器根目录                                          |
| **%%%%%%** | 插入一个字面的百分号字符                                            |
| **%!**     | 隐藏 `%!...%!` 中的空块（请参见下方） |

`%!` 代码是特殊的，应该用来包裹您想要隐藏的内容。如果块中的所有标记扩展为空值，它们将被隐藏。

例如，考虑 `%!(%R) %!%N`。如果 `%R` 扩展为空，而 `%P` 扩展为 *我的文件夹*，那么您将只获得 *我的文件夹*，而不是 *“(我的文件夹)”*。

如果您需要更自定义或更动态的内容，还可以通过命令和脚本来覆盖各个标签页的标签。

### 链接标签页

在双栏文件窗口中，文件窗口一侧的文件夹标签页可以与另一侧的标签页链接。当文件窗口中的两个标签页被链接时，选择其中一个标签页使其处于活动状态会自动使链接的标签页也处于活动状态。已链接的标签页与未链接的标签页显示的不同颜色，您可以在配置中的 **[Directory Opus 颜色](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.zh.md)** 页面中配置这些颜色。

当您单击标签页时，可以按住各种限定键来修改标签页的链接状态：

- <kbd>Ctrl</kbd> + 单击标签页以将其与另一个文件列表中的活动标签页链接（或者如果已链接，则取消链接）。
- <kbd>Ctrl+Shift</kbd> + 单击标签页以打开或关闭导航锁定模式（请参见下方）。
- <kbd>Shift</kbd> + 单击标签页以覆盖单击链接标签页时的正常行为（例如，其对应的标签页不会像往常一样显示在前）。

### 导航锁定标签页

您还可以使用上下文菜单中的 \*\*导航锁定 \*\* 选项将链接标签页置于导航锁定模式。当链接的标签页处于此模式时，与 **[导航锁定](dual_display/navigation_lock.zh.md)** 类似，目标标签页将始终在文件夹更改时跟随源标签页。

### 锁定的标签页

可以以多种不同的方式锁定文件夹标签页。主要是，当一个标签页被锁定后，它总是显示相同的文件夹。它还可以防止关闭，尽管这是可选的。

要锁定标签页，请右键单击它并从上下文菜单的 **锁定标签页** 菜单中选择一个命令。您还可以按住 <kbd>Alt</kbd> 并单击标签页以循环遍历其锁定模式。

标签页可以被锁定的不同方式是：

- **![](/Manual/images/media/13/tab_unlocked.png) 已解锁**：标签页未锁定，这意味着您可以自由地导航到初始文件夹之外。 
- **![](/Manual/images/media/13/tab_-_locked.png) 已锁定**：标签页已被锁定。尝试导航到初始文件夹之外（即锁定标签页时显示的文件夹）将导致打开一个新标签页，而不会更改原始标签页。
- **![](/Manual/images/media/13/tab_-_allow.png) 已锁定（允许更改文件夹）**：标签页已锁定，但您可以导航到初始文件夹之外。如果您在该标签页已经是活动标签页时单击它，则将恢复原始文件夹。您可以通过 [文件夹标签页/锁定](/Manual/preferences/preferences_categories/folder_tabs/locking.zh.md) 中的设置，在切换到其它标签页时恢复原始文件夹。（您还可以运行 `Go TABSELECT=home` 以通过按钮或热键恢复文件夹。）
- **![](/Manual/images/media/13/tab_-_reuse.png) 已锁定（重用未锁定的标签页）**：标签页已锁定。尝试导航到初始文件夹之外将重用现有的未锁定标签页（如果存在），否则将打开一个新标签页。

可以通过 [文件夹标签页/锁定](/Manual/preferences/preferences_categories/folder_tabs/locking.zh.md) 中的设置来防止意外关闭锁定的标签页。

这将阻止大多数关闭单个锁定标签页的方法，并且还会隐藏它们的关闭按钮。除非另有说明，这通常不会影响关闭多个标签页的操作，例如关闭整个窗口、关闭双栏或加载新的标签页组。

您还可以使用锁定命令一次锁定或解锁多个标签页；按住以下键的同时从菜单中选择命令：

- <kbd>Shift</kbd>：锁定或解锁所有标签页
- <kbd>Ctrl</kbd>：锁定或解锁活动标签页和右侧的所有其它标签页
- <kbd>Ctrl+Shift</kbd>：锁定或解锁活动标签页和左侧的所有标签页

更多：

[标签页组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md)