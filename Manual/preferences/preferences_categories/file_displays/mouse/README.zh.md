# 鼠标

此页面包含与文件列表中鼠标行为相关的各种选项。

- **单击激活文件窗口时允许选择文件**：如果文件窗口不是活动窗口，单击文件列表以将其激活可能会意外地更改文件选择状态。关闭此选项可防止单击激活文件窗口选择或取消选择文件。
- **单击切换源/目标状态时允许选择文件**：此选项本质上与 **单击激活文件窗口时允许选择文件** 选项类似。如果已启用，且你在目标文件列表中单击文件，则文件列表将设置为源，并且该文件将被选择。如果此选项已关闭，则文件列表仍将设置为源，但该文件列表中的文件选择将保持不变。
- **允许拖动到子文件夹**：通常，当你将文件拖动到子文件夹上时，你可以将其放下以将其移动或复制到该文件夹中。如果你关闭此选项，则子文件夹不会显示为目标位置，除非你也按住 <kbd>Shift</kbd>（移动）、<kbd>Ctrl</kbd>（复制）或 <kbd>Alt</kbd>（创建快捷方式）键。例如，如果由于身体残疾而导致拖放困难，此功能非常有用——没有比意外将其放置在未知子文件夹中导致文件消失更糟糕的事情了。
- **鼠标光标热跟踪**：使用视觉样式时，当你移动鼠标时文件列表通常会高亮鼠标指针下的项目（称为“热”项目）。如果你觉得这会分散注意力，可以在此处将其关闭。
- **悬停以切换源/目标状态**：在双栏文件窗口中，将鼠标悬停在目标文件列表上指定时间，将自动切换源和目标状态。
- **鼠标滚轮 + <kbd>Ctrl</kbd> 调整字体和缩略图大小**：

![zoom_text.png](/Manual/images/media/13/zoom_text.png)

按住 <kbd>Ctrl</kbd> 键并在文件列表上转动鼠标滚轮，将会像缩放功能一样。执行此操作时，地址栏中将显示一个图标。
  这将向你显示当前缩放级别，并允许你重置缩放级别或使其永久化（通过更新配置字体配置）。

- **鼠标滚轮 + <kbd>Shift</kbd> 向后和向前导航**：如果你的鼠标没有专门的后退/前进按钮，你可以按住 <kbd>Shift</kbd> 并转动滚轮来模拟它们。
- **单击打开项目**：此选项会激活“单击”模式。在此模式下，你可以通过用鼠标悬停在文件上选择文件，并单击它们（如单击网页上的链接）打开文件或文件夹。
  - **<kbd>Alt</kbd> + 单击选择而不打开**：而不是打开文件或文件夹，如果你在单击时按住 <kbd>Alt</kbd> 键，则它只选择该项目。
  - **仅单击图标**：让你可以同时享受“两全其美”；当鼠标悬停在文件的图标上时享受单击便利，而当鼠标悬停在文件标签上时则享受正常单击行为。
  - **悬停时给项目加下划线**：当单击模式处于启用状态时，此选项让你控制是否在用鼠标悬停项目时给这些项目的标签加下划线。
- **单击中键切换选择状态**：让你可以单击中键选择或取消选择项目，而无需按住 <kbd>Ctrl</kbd> 或 <kbd>Shift</kbd> 键以防止其它项目取消选择。
- **单击中键触发文件和文件夹中间双击事件**：Opus 允许你分配在中间双击时执行的 [文件类型事件](/Manual/file_types/filetype_editor/events.zh.md)；启用此选项后，单击中键将触发这些事件。
- **使用鼠标滚轮/键盘平滑滚动**：此选项启用文件列表平滑滚动。