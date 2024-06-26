# 进度指示器

这些选项控制 Opus 在复制或移动文件或执行其它文件操作时显示的进度指示器。

- **指示器出现之前延迟**: 此选项用于在非常快速的运算中停止 Opus 显示进度指示器。如果函数在指定时间（以毫秒为单位）内完成，则该函数的指示器将根本不会打开。
- **在工作栏可见时从任务栏中隐藏**: 当 [工作栏](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.zh.md) 可见时，进度指示器将不再在任务栏上显示“占用空间”，并且不会出现在 <kbd>Alt+Tab</kbd> 窗口列表中。这意味着，当进度指示器最小化时，它们“只能”通过工作栏访问。如果关闭工作栏，并且有隐藏的进度指示器，它们将自动再次在任务栏上显示，因此不存在“丢失”作业的风险。
- **自动最小化进度指示器**: 进度指示器对话框会在打开时自动最小化。根据之前选项的状态，这可能意味着新作业的唯一指示是在工作栏上出现一个新按钮，因此 Opus（默认情况下）会显示一个小箭头动画，指向新创建的工作栏按钮，以提供操作已成功启动的反馈。
  - **仅在工作栏可见时**: 只有当工作栏显示时，进度指示器才会最小化，如果没有，它们将像往常一样在文件窗口的前面打开。
- **在文件复制进度指示器中显示速度图表**: 如果启用此选项，进度指示器将显示表示传输速度随时间变化的图表。
  - **保留从一个作业到下一个作业的速度信息**: 当复制指示器移动到下一个作业时，现有的速度历史记录将被保留，并且图表将“持续进行”，而不是从头开始。
- **在进度指示器标题中显示完成百分比**: Opus 将在标题栏中显示函数的总体完成百分比。
- **在打开新作业时切换到队列标签页**: 当将新作业添加到队列时，将显示进度指示器的**队列**标签页。
- **作业开始时的滑动动画**: 如果在另一个作业排在其后面进行队列时进度作业完成，则旧作业将从进度对话框的顶部滑出，而新作业将从底部滑入。这将在作业之间添加一个轻微的延迟，并且可以在不需要时将其关闭。（无论此设置如何，如果使用远程桌面或在系统范围内禁用了客户端区域动画，都将自动禁止滑动动画。）