# 过滤条款

一个过滤从一个或多个*条款*构建：将文件的特定属性与提供的值进行比较的指令。当 Opus 向一个操作应用一个过滤器时，每个操作可能影响的潜在文件都会与过滤器中的条款进行比较，只有那些匹配过滤器的文件会被处理。

过滤器实际上是以人类可读的形式表达的布尔操作。

- 单个条款可以设置为 *匹配*（真）*或 *不匹配*（假），它给出了一个 **非** 运算符的效果。
- 条款与布尔运算符 **且** 或 **或** 相连接。
- 一个过滤器也可以具有子条款，以在布尔运算中产生括号的效果。

例如，考虑以下布尔表达式。它的效果是匹配所有大于 100KB 的 **.jpg** 文件或所有小于 50KB 的 **.gif** 文件（为什么要这样做是另外一个问题）：

    匹配 ( 
        名称 匹配 *.jpg
        且 大小 匹配 > 100 kb
    )
    或 匹配 ( 
        名称 匹配 *.gif
        且 大小 匹配 < 50 kb
    )

它将在一个过滤控件中由以下条款表示：

![](/Manual/images/media/13/complex_filter.png) 

括号中包含的两个表达式由子条款表示。每个子条款都包含由 **且** 运算连接的两个条款；一个 **名称** 匹配（它基于一个通配符模式来比较文件名）和一个 **大小** 匹配（它比较文件的大小和给定值）。最后，两个子条款由 **或** 运算相互连接。您可以在过滤控件中看到，子条款的内容缩进于它们的上级条款。

### 否定条款

在上面的例子中，所有条款都设置为 *匹配*，这意味着条款中的条件必须为 **真** 才可以匹配。如果一个条款设置为 *不匹配*，那么它必须为 **假** 才可以匹配。想象一下，如果我们希望匹配大于 100KB 的所有 **.jpg** 文件，但 **不** 匹配大于 1MB 的文件或名称中带有“马”字的文件。其人类可读形式如下：

    名称 匹配 *.jpg
    且 大小 匹配 > 100 kb
    且 不匹配 ( 
        大小 匹配 > 1 mb
        或 名称 匹配 *马*
    )

在过滤控件中，您可以按如下方式表示它：

![](/Manual/images/media/13/complex_filter_2.png) 

上述示例中的子条款设置为 *不匹配*，这意味着除非子条款 **未能** 匹配，否则过滤器将不会匹配文件。子条款包含两个子条款，这两个子条款都设置为 *匹配* 并由 **或** 运算符相连接。因此，对于相关文件，如果其 **大小** 大于 1 MB 或其 **名称** 中包含“马”，那么其中一个或另一个（或两者）条款都将匹配，这意味着它的上级子条款将匹配，这意味着（因为子条款设置为 *不匹配*）过滤器将失败。感到困惑了吗？ :)