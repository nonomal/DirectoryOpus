# 结果

**结果**对象提供了由**[命令](command.zh.md)**对象运行的函数结果的信息。它从**Command.results**属性获取。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
结果</td><td>

*int*</td><td>
指示命令是否成功运行。零表示命令无法运行或中断；任何其它数字表示命令已对至少某些文件运行。（请注意，它不是外部命令的“退出代码”。对于外部命令，它仅表示 Opus 是否启动了该命令。如果您需要外部命令的退出代码，请使用 WScript.Shell Run 或 Exec 方法运行命令。）
</td></tr><tr><td>
新标签页</td><td>

*集合:***[标签页](tab.zh.md)**</td><td>

此属性返回一个集合，其中包含表示命令创建的任何新标签页的**[标签页](tab.zh.md)**对象。
</td></tr><tr><td>
新列示器</td><td>

*集合:***[列表](lister.zh.md)**</td><td>

此属性返回一个集合，其中包含表示命令创建的任何新列表的**[列表](lister.zh.md)**对象。
</td></tr><tr><td>
新查看器</td><td>

*集合:***[查看器](viewer.zh.md)**</td><td>

此属性返回一个集合，其中包含表示命令创建的任何新图像查看器的**[查看器](viewer.zh.md)**对象。（仅适用于独立查看器，不适用于查看器窗格。）
</td></tr></tbody>
</table>