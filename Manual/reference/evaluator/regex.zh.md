\<evalcmd\> RegEx && bool 或字符串 && 匹配或替换结果。 && 字符串 && 字符串 && 要匹配的字符串。 && 模式 && 字符串 && 要进行匹配的模式。 && \[替换\] && 字符串 && 可选的替换模式。 && \[模式...\] && 字符串 && 可选的其它匹配模式... && \[替换...\] && 字符串 && 可选的其它替换字符串... && \[0\] && 值 && 字面值 0。在不使用 *replace* 的情况下，仅需要这样才能指定 *flags*。 && \[标志\] && 字符串 && 可选标志有：

|        |                                                                             |
| ------- | -------------------------------------------------------------------------- |
| **c**    | 在执行操作时考虑大小写（区分大小写）                                   |
| **e**    | 如果模式不匹配替换操作，则返回一个空字符串                             |

\</evalcmd\>

对提供的字符串执行正则表达式 **match**。此模式必须与字符串完全匹配。

如果 **未**指定 *replace* 模式，则此函数会在提供的 *string* 匹配 *pattern* 时返回 **True**，否则返回 **False**。

如果指定了 *replace* 模式，则返回替换结果。您可以指定多个 *string/pattern* 对，以便一次执行多个替换。如果输入字符串与模式不匹配，则原样返回。您还可以在每个搜索模式的末尾添加 **\#** 来重复搜索并尽可能多地进行替换（即“全部替换”）。

必须最后指定可选的 *flags* 参数。如果没有提供 *replace* 模式，并且您想提供 *flags*，则您必须为第三个参数传递一个字面 **0**。

//<示例：//</>

        path = "C:\Projects\contoso_staging\2023\June";
        Output(RegEx(path, "(.*)_staging\\(.*)", "\1\\\2"));
        --> C:\Projects\contoso\2023\June

*另请参阅：*

[正则表达式](regexs.zh.md)