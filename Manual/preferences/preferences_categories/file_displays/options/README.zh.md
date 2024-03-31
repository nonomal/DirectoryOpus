# 选项

本页包含各种选项，供您调整文件列表的行为。

- **自动选择文件夹中的第一个文件**：导航到新文件夹后，此选项会自动选择列表中的第一个项目。此选项不适用于增强模式文件列表 - 在[Power Mode](../file_display_modes/power_mode/README.zh.md)页面上有一个单独的选项。
- **在文件列表排序时重置焦点项目**：如果你不想在更改文件列表排序方式（例如点击列标题）时让文件列表滚动，请开启此选项。关闭此选项，排序会导致文件列表滚动，以便之前获取焦点的文件在其新位置保持可见。启用此选项后，文件列表不会滚动，而会将焦点给予最终出现在之前有焦点的文件所在位置的任何文件。
    如果在更改之前文件焦点已经被滚动到视图之外，它将被忽略，并且焦点将重置到可见的第一个项目。举例来说，如果你滚动到文件列表的顶部，点击第五个项目，然后按日期排序： 如果该选项开启，你仍将位于文件列表表的顶部，而焦点将放在现在的第五个项目上。如果选项关闭，则焦点将放在与之前相同的文件上，并且文件列表将滚动以确保其仍然可见。

- **在文件夹之间保留文件夹格式编辑**：通常情况下，当你在一个文件列表中修改文件夹格式，然后更改文件夹，修改的格式将保留（除非新文件夹有自己的已保存格式会覆盖）。如果你关闭此选项，临时更改将不保留，并且格式在你每次更改文件夹时都将重置。
- **在图标模式中显示排序表头**：通常情况下，列表头仅在详细信息和增强模式中显示。如果你开启此选项，列表头也会在图标模式（如缩略图）中显示。虽然这些模式中没有列，但你仍然可以使用表头作为一种便捷的方式对文件列表进行排序或分组。

##### 单显示

- **单显示列表程序设有源文件/目标文件模式**：当一个列表程序处于双栏模式时，总有一边是源文件，而另一边则是目标文件。当一个列表程序处于单显示模式时，有可能整个列表程序都是源文件，而另一个列表程序是目标文件。当禁用此选项时，单显示列表程序不参与源文件/目标文件。有关更多信息，请参阅[源文件和目标文件](/Manual/basic_concepts/source_and_destination.zh.md)。

##### 双栏

- **切换到双栏时将新面板设置为源文件**：当你将一个列表程序切换到双栏模式时，此选项会导致新打开的文件列表成为源文件，而原来的文件列表成为目标文件。
- **切换到双栏时指定初始文件夹**：通常，当您将文件窗口切换到双栏模式后，已打开的文件夹将显示在第二个文件列表中。此选项允许你指定一个特定的文件夹，作为新打开显示的默认值（例如，你可以始终将第二个文件列表打开以显示“桌面”）。“标签页组”选项允许你在切换到双栏模式时自动打开一个标签页组（而不是只打开一个文件夹）。