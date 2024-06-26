# 展开/折叠

此页包含有关在文件夹树中展开和折叠分支的选项。

### 文件夹内容填充

**自动展开到当前文件夹**选项控制树在您浏览文件列表时展开文件夹的方式。

如果此选项已启用，在您浏览文件列表时，树将展开来跟踪您的位置。如果已禁用，树将不会自动跟踪您的位置 - 您仍然可以通过自己展开和选择文件夹来使用树导航，但当您通过其它方法导航时，它不会跟随您。

请注意，此选项仅适用于树中分支*从未*被展开时（它旨在允许您控制树尝试读取子文件夹内容的时间）。如果已手动展开分支，则树已经知道其内容，因此此选项将不适用。要阻止树自动展开文件夹，请从 [文件夹树/外观](appearance.zh.md) 页中启用锁定按钮，然后在您想要保留树的当前状态时启用锁定。

您可以选择在文件夹自动展开以便显示您当前位置时如何填充文件夹：

- **完全填充内容**: 所有自动展开的文件夹都已完全填充 - 此树将显示从当前位置导出的所有文件夹的完整内容。
- **仅填充本地设备的内容**: 只有本地设备（硬盘驱动器、USB 驱动器等）上的文件夹将完全填充。网络驱动器或 FTP 站点上的文件夹只会显示构成当前位置一部分的成员文件夹。
- **不填充内容**: 没有自动展开的文件夹将被完全填充 - 您需要通过单击其展开按钮手动填充这些文件夹以显示其完整内容。

树将始终向您显示您的当前文件夹（及其通往它的路径），因此填充选项仅影响已展开文件夹中其它项目的显示。当您手动展开项目时，其内容将始终被完全填充 - 因此，如果树已经部分展开了项目，您可以单击其展开按钮，以便完全展开项目并显示其其余内容。当在诸如网络等慢速设备上浏览文件夹时，这些选项可以显著提高性能 - 树将仅显示通向您当前路径的文件夹（并且因为它已经知道这些文件夹是什么，所以它不必从网络中读取任何信息），而不是必须读取导出您当前位置的所有文件夹的完整内容（这可能通过网络非常缓慢）。\</WRAP\>

### 其它选项

- **动画展开的分支**: 当分支展开时，其内容将滑动展开，而不是立即出现。
- **折叠未选中的分支**: 树将自动折叠为您显示当前位置不需要的所有已展开分支。这有助于保持树的紧凑和方便在文件系统中移动时导航。
  - **如果在其它标签页中已打开除外**: 如果分支包含当前在其它文件夹标签页中显示的文件夹，则不会折叠分支。
- **展开已选中的分支**: 树将自动展开表示您当前位置的分支。通常，只有通向您当前位置的文件夹会被展开 - 启用此选项后，当前位置的分支也将被展开。
  - **在更改标签页时展开已选中的分支**: 当您更改哪个标签页处于活动状态时，树将自动展开当前标签页的分支。没有此选项，只有当您实际上导航到标签页中的新文件夹时，分支才会展开。
- **双击父级时展开/折叠所有子分支**: 当您双击文件夹的展开/折叠图标时，也将展开或折叠其子文件夹的第一级。
- **分支展开时防止滚动**: 阻止树在分支展开时跳下来（尽可能多地显示展开的分支）。
- **在布局中记住展开的根项目**: 在 [文件窗口布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md) 中，包括 [默认文件窗口](/Manual/basic_concepts/the_lister/the_default_lister.zh.md) 中，将记住根项目的展开状态。
  - **记住所有展开的项目**: 将记住所有展开的文件夹状态，而不仅仅是根项目。
  - **仅记住已固定的项目**: 仅记住固定文件夹 - 其它文件夹将不会保留其展开状态。
- **为标签页记住展开的项目**: 将保留文件夹树中文件夹的展开状态在标签页之间。也就是说，当您切换离开标签页时，Opus 就会记住文件夹树中哪些文件夹已展开，哪些文件夹已折叠，并且在您切换回该标签页时恢复此状态。

### 拖放

- **在树上拖动时展开分支**: 当您将文件拖到树上时，树将自动展开您将鼠标悬停在上面的所有已折叠文件夹。这允许您将文件拖放到在拖放开始时不一定可见的子文件夹中。
- **拖放后折叠（弹簧式）**: 在拖放过程中自动展开的文件夹将在拖放完成后再次折叠。
- **展开延迟**: 配置在拖放过程中鼠标悬停在文件夹上的时间（单位为毫秒），然后该文件夹才会展开。