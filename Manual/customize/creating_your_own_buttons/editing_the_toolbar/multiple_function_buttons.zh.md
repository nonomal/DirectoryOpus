# 多功能按钮

多功能按钮有一个多达三个不同功能的按钮附加在按钮上（因此也被称为“三按钮按钮”）。

- 第一个或主要功能通过**左键**单击按钮来执行，就像普通方式一样
- 第二个功能通过**右键**单击按钮来执行
- 第三个功能通过**中键**单击按钮来执行。如果您没有中鼠标按钮，则配置中“**[工具栏/选项](/Manual/preferences/preferences_categories/toolbars/toolbar_options.zh.md)**”页面上的“**用 `Control` + 左键单击模拟中键单击**”选项可以帮助您充分利用此功能。

要制作一个多功能按钮，您必须从一个常规的单功能按钮开始。有关如何根据需要创建新按钮的信息，请参阅[编辑工具栏]()。在自定义模式下，鼠标右键单击按钮并从其上下文菜单中选择**三按钮**选项。这会立即将单按钮变成一个多功能按钮，而按钮的原始功能将成为新的*主要*功能。

![](/Manual/images/media/three_button_1.png) 

在自定义模式下，多功能按钮的行为与[下拉菜单](drop-down_buttons_and_menus.zh.md)非常相似（除菜单中的功能数量限制为三个外）。上面的图像显示了如果您将标准工具栏上的**双栏**按钮变成一个多功能按钮，最初会看到什么。实际上，原始按钮将成为下拉菜单，并且原始功能被复制，并成为新菜单中的第一个按钮。

您现在可以使用[编辑工具栏]()页面中描述的技术向下拉菜单中添加一个或两个附加按钮。

![](/Manual/images/media/three_button_2.png) 

在这里，我们已经从自定义对话框中拖动**文件夹树**按钮并将其放入菜单中 - 它已成为按钮的第二个功能。同样，**元数据窗格**按钮已作为按钮的第三个功能被添加。多功能按钮现在已经“满”了 - 尝试向菜单中添加其它功能将失败。

当您退出自定义模式时，工具栏按钮会像之前一样显示 - 并且，事实上，左键单击它会执行与之前相同的操作（即打开或关闭[双栏](/Manual/basic_concepts/the_lister/dual_display/README.zh.md)模式）。只有当您将鼠标悬停在按钮上方以显示工具提示时，差异才变得明显。

![](/Manual/images/media/three_button_3.png) 

工具提示明显表明此按钮附有多个功能。与每个函数关联的按钮由**LMB**（左鼠标按钮）、**RMB**（右鼠标按钮）和**MMB**（中鼠标按钮）前缀指示。因此，在此示例中，对按钮左键单击将开启或关闭双栏模式，对按钮右键单击将开启或关闭文件夹树，对按钮中键单击将开启或关闭元数据窗格。