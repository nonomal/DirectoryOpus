\<evalcmd\> Format && 字符串 && 格式化后的字符串。&& fmtstring && 字符串 && 包含插入代码的字符串。代码对于第一个参数为**%1**，第二个参数为**%2**，以此类推。

要在输出字符串中包含一个文字百分号字符，请使用特殊代码 **%%**。&& arg1 && 任意 && 要插入的代码 **%1** 的参数。&& \[arg2...\] && 任意 && 要插入的代码 **%2** 等 的参数…\</evalcmd\>

返回格式化的输出字符串。

//<示例://>

    Output(Format("Hello %1!", "Jon"))
    --> Hello Jon!

*请参见：* [as](as.zh.md)