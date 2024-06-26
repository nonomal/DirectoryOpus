# 静态文本属性

适用于*静态文本*控件的特定属性如下：

- **省略号**：此选项配置了省略号（...），当标题字符串不能完全容纳在控件中时将会显示此选项。选项包括：
  - **无**：不显示省略号，不适合的文本将被裁剪。选择**无**还会启用自动换行（因此文本会在被剪裁之前自动换行到额外的行）。你还可以使用**\n**字符序列手动插入换行符。
  - **结尾**：如果字符串的结尾不适合矩形，则该字符串将被截断并且添加省略号。如果不在字符串结尾的单词超出了矩形的限制，则该词将被截断并且不添加省略号。使用此样式将强制控件的文本单行显示且不自动换行。
  - **单词**：截断任何不适合矩形的单词并添加省略号。使用此样式将强制控件的文本单行显示且不自动换行。
  - **路径**：用省略号替换字符串中间的字符，以便结果适合指定矩形。如果字符串包含反斜杠（\\ 字符，则此样式尽可能保留反斜杠之后的文本。使用此样式将强制控件的文本单行显示且不自动换行。
- **编辑控件**：静态控件复制了多行编辑控件的文本显示特征。具体来说，平均字符宽度是以与编辑控件相同的方式计算的，并且该函数不显示部分可见的最后一行。
- **无前缀**：设置 **“True”** 后，可以防止将控件文本中的任何&（和）字符解释为助记前缀字符。这些字符显示为去掉了&，并且字符串中的下一个字符带有下划线。当文件名或其它可能包含&（和）的字符串必须显示在对话框中的静态控件中时，这将非常有用。
- **图像**：设置 **“True”** 后，该控件将显示图像文件，而不是文本字符串。**标题** 属性的值将被用作要显示的图像文件的路径名称（因此，在脚本中，可以通过更改控件的标题来加载新图像）。该图像将自动缩放至适合控件的大小。
- **报告点击**：设置 **“True”** 后，该控件会在鼠标单击时报告**click**（单击）、**dblclk**（双击）和**rclick**（右键单击）事件。设置 **“False”** 后，该控件将完全忽略鼠标点击。
- **拖拽源**：设置 **“True”** 后，当用户单击控件并用鼠标拖动时（例如，开始拖放操作），该控件会发送**drag**（拖放）事件。