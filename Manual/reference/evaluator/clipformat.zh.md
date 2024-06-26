\<evalcmd\> ClipFormat 和字符串或布尔值 && 剪贴板内容格式。 && \[类型\] && 字符串 && 测试的内容类型。 && \[希望剪切\] && 布尔值 && 传递 **真** 以区分剪切文件和复制文件。 \</evalcmd\>

如果没有参数，则返回一个字符串来标识当前剪贴板上的数据类型。

可能的剪贴板数据类型为：

|        |                |       |                                         |       |
|--------|---------------|-------|------------------------------------------|-------|
|        | *files*        |       | （如果 **希望剪切** 为 **假** 或省略） |       |
|        | *files_copy*   |       | （如果 **希望剪切** 为 **真**）         |       |
|        | *files_cut*    |       | （如果 **希望剪切** 为 **真**）         |       |
|        | *image*        |       |                                         |       |
|        | *text*         |       |                                         |       |
|        | *other*        |       |                                         |       |
|        | *none*         |       |                                         |       |

您还可以通过将要测试的类型作为字符串传递为第一个参数来测试剪贴板上是否存在特定类型的数据，在这种情况下，返回值为 **真** 或 **假**。

*示例：*

    Output(ClipFormat());
    Output(ClipFormat(True));
    if (ClipFormat("text")) { ... }
    if (ClipFormat("files")) { ... }
    if (ClipFormat("files_cut",True)) { ... }