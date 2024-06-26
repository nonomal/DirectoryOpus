# 重命名宏

**宏**功能提供了一种方法，可以向文件名中添加和删除文本，而无需使用通配符。您可以使用宏来添加字符、删除字符以及移动文件名中的字符。

重命名对话框的“操作”部分中的**宏**字段显示实际的宏定义，但幸运的是，您无需了解宏语言即可使用它。除了显示重命名操作的预览，对话框底部的预览列表还可以作为宏构建器。您可以在预览列表中直接编辑文件名，此操作将生成宏，以使用相同的方式批量重命名所有文件。

如果您对重命名宏语言感兴趣，可以在本手册的[参考部分](/Manual/reference/rename_macro_language.zh.md)中进行描述。还要注意，宏构建器使用的字体（必须是等宽字体）可以通过[字体](/Manual/preferences/preferences_categories/colors_and_fonts/fonts.zh.md)配置页面进行配置。

### 使用宏构建器

要使用宏构建器，请确保启用了 **使用预览列表构建宏** 选项。

例如，假设我们有一堆文件，其名称格式为 *YYYY-MM-DD_draft.txt*，且我们希望将它们重命名为 *Final DD.MM.YYYY.txt* - 删除“\_draft”后缀，互换日期字段的顺序然后在每个文件名的开头插入“Final”。

使用通配符执行此操作需要复杂的正则表达式，但宏使它变得容易。您只需从预览列表中选择一个文件名并在其中内联编辑它，就像重命名单个文件一样 - 选择文本区域，将其剪切到剪贴板，将其粘贴到其它位置，选择另一个区域，删除它，键入一些新字符，依此类推。

![宏构建器](/Manual/images/media/13/rename_macro_builder.png)

宏构建器会将您的操作记录为宏表达式，并将相同的更改应用于所有选定的文件。

要构建宏，只需单击预览列表的 **新名称** 列中的文件名（或按 <kbd>F2</kbd> 键）。此时，您按下的任何键都会作为表达式记录在 **宏操作** 字段中（尽管您无需了解宏语言，但它在参考部分中描述得很完整）。

### 宏锚点

每个文件名的左侧或右侧的铅笔图标表示当前锚点位置，即后续操作将相对于该文件名的哪一端。在上面的屏幕截图中，锚点被设置为右侧，这意味着所有操作都相对于字符串的右侧。例如，这使您可以从文件名的末尾删除一定数量的字符，而无需使所有文件名都具有相同长度。

要更改锚点位置，您可以用鼠标双击铅笔图标，或将光标定位在名称的另一端，然后按相应于该方向的光标键（<kbd>左</kbd> 或 <kbd>右</kbd>）。您还可以连续按两次 <kbd>Home</kbd> 或 <kbd>End</kbd> 键。

### 选择范围

当您使用鼠标或 <kbd>Shift</kbd> 加光标键选择一段字符时，预览列表中的所有其它文件中也会显示为选中的等效范围 - 因此您可以在提交之前检查您的选择是否正确。无论名称的长度如何，您都可以按两次 <kbd>Shift+End</kbd>（当锚点设置为右侧时按 <kbd>Shift+Home</kbd> 以选择到所有名称的末尾。

在上面的示例中，您可以看到原始的 *\_draft* 后缀已被删除 - 我们通过将锚点放在名称的右端，向左选择 6 个字符并按 <kbd>Del</kbd> 键来完成此操作。

在截取屏幕截图时，我们通过按两次 <kbd>Shift+Left</kbd> 选中名称中的最后两个字符，下一步是按 <kbd>Ctrl+X</kbd> 将这些字符剪切到剪贴板。这将生成下一个宏命令，依此类推，直到宏完成。您可以在所有阶段检查预览列表，以确保宏对所有选定文件名产生了所需的效果 - 如果某些文件列表结果不正确，您始终可以通过关闭其复选框来跳过它们。

### 使用剪贴板

在宏构建器中，标准的剪贴板键 <kbd>Ctrl+C</kbd>、<kbd>Ctrl-X</kbd> 和 <kbd>Ctrl-V</kbd> 会在宏中记录这些操作，并且这些操作将针对每个文件名分别处理。如果您想将剪贴板上的文本“原样”粘贴到宏中（而不是记录粘贴操作本身），则需要按 <kbd>Ctrl+Shift+V</kbd>。

### 直接编辑名称

如果 **使用预览列表构建宏** 选项已关闭，则预览列表允许您逐个编辑新文件名。这非常适合对宏（或其它批量操作）可能没有完全正确捕获的名称进行少量更改。直接编辑文件名称后，它将显示为红色，并且该名称将被锁定，直到重命名操作发生（或直到您清除自定义名称）。