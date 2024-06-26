# 隐藏状态栏中的部分内容

若某个特定值不等于 0（或等于 0），那么有可能将状态栏定义的一部分内容配置为仅在该值不等于 0 时显示（或等于 0 时显示）。默认状态栏定义在显示当前文件夹中隐藏项的数量时就是这样用的。当没有隐藏项时，与其显示数目为零，不如将部分直接隐藏掉 - 只有在隐藏了一项或多项时才显示。

将有条件隐藏的部分用一对特殊代码包围起来。Opus 查看部分中所有状态栏代码的值，并应用所需的测试。

- **{h!}** ... **{h!}**  - 如果部分中的所有代码都不等于 0，则仅显示
- **{h#}** ... **{h#}** - 如果部分中的任意代码不等于 0，则显示
- **{h?}** ... **{h?}**  - 如果部分中的所有代码都等于 0，则仅显示

例如：

**{h#}{sd}/{td} 个文件夹，{sf}/{tf} 个文件{h#}**

这显示了所选文件夹和文件数量，以及它们总数。如果**根本**没有文件或文件夹，那么此部分将隐藏。

状态栏代码也能够包含在条件代码本身中。这使您能够测试状态栏值，而不必实际在状态栏中显示那些值。例如：

**{h?{si}}{ti} 个对象{h?}{h!{hi}?{si}}{h!}{si} 个对象已选择{h!}**

这里包含两个有条件隐藏的部分。每个部分都以不同的方式在测试 **{si}** 代码（已选择项的数量）的值，这意味着一次仅会显示两个部分中的一个。

- 第一个部分在隐藏代码中使用嵌入式代码来测试 **{si}**。如果所选项的数量为 0，则会显示字符串\*\* {ti} 个对象\*\*，但请注意，**{si}** 代码本身不会显示。
- 第二个部分使用 **{h!}** 代码来在所选项的数量不为 0 时显示字符串 **{si} 个对象已选择**。

您甚至可以嵌入多个条件代码来执行更复杂的测试。例如，**{h!{sf}?{sd}} ... {h!}** 将仅在 **{sf}**（所选文件）不为 0 且 **{sd}**（所选文件夹）为 0 时显示条件文本。

虽然一个隐藏的部分可以依赖于多个条件，并且您可以在同一状态栏中有多个单独的隐藏部分，但您**不能在同一位置嵌套或重叠**多个隐藏部分，否则该位置将无法正常使用。

**变量**可用于显示或隐藏状态栏的部分内容，而反过来，这样一来您便可以创建工具栏按钮或热键来切换其它信息，或编写脚本以在您更改文件夹或更改显示模式时自动更改所显示的信息，例如。请参阅 [{var:...} 代码文档](other_codes.zh.md) 以了解详细说明。

例如：

**{h!{var:glob:ShowExtraInfo}} {smp3} / {tmp3} ...其它其它信息... {h!}**

**条件测试**还可用于基于当前文件夹、是否存在特定路径或各种[内部命令](../command_reference/internal_commands/README.zh.md) 返的状态来显示或隐藏部分。有关详细信息，请参阅 [{ifpath:...}, {ifexists:...} 和 {if:...} 代码文档](other_codes.zh.md)。

例如：

**{h!{ifpath:C:\\} 您正位于 C:\\ 的根目录 {h!}**

**{h!{ifpath:/downloads}!{ifexists:.\\.dll}} 警告：下载文件夹中有 DLL！{h!}**

**{h!{if:!Set VIEW=Details}}{sel:size} {sel:write}{h!}**

请记住，某些条件测试可能会影响性能。请参阅有关它们的章节以了解详细说明。