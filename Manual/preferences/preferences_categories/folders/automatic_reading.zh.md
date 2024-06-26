# 自动读取

此页面上的选项允许您防止 Opus 自动加载特定类型的文件夹（例如，当一个文件窗口打开时，它通常会自动加载一个文件夹）。

如果您已将 Opus 设置为在运行时重新打开上次位置，或打开显示网络驱动器或其它慢速驱动器类型的特定文件窗口布局，这会非常有用。这将阻止 Opus 在文件窗口首次打开时尝试自动读取指定类型的文件夹。例如，您可以使用一个读取网络驱动器的布局 - 选中此选项后，打开该布局不会自动连接到网络驱动器，而是会提示您单击一个链接才能读取文件夹。

- **CD-ROM/DVD**：位于 CD 和 DVD 上的文件夹将不会自动加载。
- **已关闭电源的驱动器**：处于睡眠模式的硬盘驱动器（已关闭电源）将不会自动加载。这将阻止 Opus 唤醒它们，直到您手动读取文件夹为止。
- **FTP 站点**：在手动加载文件夹之前，不会自动重新连接到 FTP 站点。
- **网络驱动器**：位于网络驱动器上的文件夹将不会自动加载。
- **可移动设备**：适用于 U 盘和一些（但不是全部）外部硬盘驱动器。
- **搜索结果**：如果您关闭一个显示快速搜索结果的文件窗口，则这将阻止在它重新打开时自动重新运行搜索。
- **ZIP 文件和其它压缩包**：无论它们驻留在何种设备上，压缩包都不会自动加载。
- **所有其它驱动器类型**：应用于未单独列出的所有内容。

对于每个文件夹类型，您可以从三个选项中进行选择：

- **正常加载**：加载文件夹。
- **阻止加载**：防止自动加载文件夹。将在文件列表屏的顶部显示一条消息，其中包含一个可以单击以触发读取的链接。
- **在标签激活时加载**：如果标签不是活动标签，则最初阻止加载，但在标签首次激活时会自动加载文件夹。

### 特定文件夹

本页面的底部是一个列表，允许您将相同的选项应用于特定文件夹或通配模式。例如，您可以使用上面的选项将网络驱动器设置为通常不自动加载，但通过将路径添加到“文件夹”列表中，为一个特定服务器覆盖它。