# 简单通配符重命名

“简单重命名”对话框使用一个简单的通配符系统，可批量重命名文件。字符 \*（星号）用于指定现有文件名中保留在新名中的一个或多个部分。它基本上等同于“高级重命名”对话框中的“[标准通配符重命名](advanced_rename/rename_modes/standard_wildcard_rename.zh.md)”模式。此通配符系统还用于“以……复制”和“以……移动”的功能，有关更多示例，请参阅[复制时使用通配符](../copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md) 文档。

访问“简单重命名”的最简单方法是在“重命名”下拉菜单中选择该选项，这使其成为默认模式，之后点击“重命名”按钮将默认以简单模式显示此模式。您可以随时切换回高级模式。

您还可以使用原始命令 `Rename SIMPLE` 访问它。

![](/Manual/images/media/13/simple_rename.png) 

在这个示例中，我们希望重命名以 **Img\_** 开头并以 **.jpg** 结尾的任何文件。匹配不区分大小写，因此将匹配 **Img_2481.jpg**、**img_2481.jpg** 等。“\*”表示要保留前缀和后缀之间的任何文本，“\*”在“新名称”字段中表示放置该文本的位置。给定以下输入文件名，最终生成的新名称为：

    Img_2481.jpg    IMG2481.jpg

    IMG_2483.JPG    IMG2483.jpg

    Img_2486.jpg    IMG2486.jpg

重命名操作将对调用命令时选择的所选文件和文件夹进行操作，但子文件夹中的文件将不会被重命名（您需要使用“高级重命名”才能做到）。

如果您没有输入通配符模式，而是只提供一个文字新名称，则此功能将依次重命名每个所选文件 - 将重命名第一个文件，并且对话框将重新打开，显示第二个所选文件的名称，依此类推。