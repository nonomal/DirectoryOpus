# 拆分文件

**拆分文件**工具允许您将单个文件拆分成多部分。例如，您可以将一个大文件拆分成适合存储在 CD 中或通过电子邮件发送的小块。**[合并文件](joining_files.zh.md)** 工具可用于将拆分的文件重新合并到一起。

![](/Manual/images/media/split.png) 

若要访问 **拆分文件** 工具，请选择您想要拆分的文件，然后从 **工具** 菜单中选择 **拆分文件** 命令。

**到文件夹** 字段能让您定义拆分的目标地 - 默认的目标地为[目标文件夹](/Manual/basic_concepts/source_and_destination.zh.md)（如果不存在目标文件夹，它将默认为包含源文件的文件夹），但是您可以使用 **浏览** (![](/Manual/images/media/browse.png)) 按钮对它进行更改。

**块大小** 字段能让您选择拆分后的块的大小。您可以从下拉列表中选择预定义的大小，或者输入您自己的大小。如果您输入手动大小，可以通过在数字后输入相应的后缀来指定块的大小，单位为千字节 (**KB**)、兆字节 (**MB**) 或千兆字节 (**GB**)。例如，**1.87 MB**。如果没有给出后缀，块大小将默认为字节。

如果 **块大小** 设置为 **自动**，则会使用目标地的可用空间（如果它是一个可移动设备），否则将使用固定的 100 MB 大小。

如果 **UU 编码** 选项已启用，则拆分后的块将被 [uuencode](http://en.wikipedia.org/wiki/Uuencoding)。Uuencode 是一种用于将二进制文件（如程序或视频文件）作为纯文本 ASCII 文件进行传输的编码形式。例如，一些 UseNet 新闻组用于分发已经 uuencode 的二进制文件。