\<evalcmd\> DateDiff && int && 返回两个日期之间的差值。 && units && 字符串 && 要返回的单位类型。有效的单位类型包括：

|      |                                    |
|------|------------------------------------|
| yyyy | 年                               |
| q    | 季度                               |
| m    | 月                                |
| y    | 天                                |
| d    | 天                                |
| w    | 整周                               |
| ww   | 日历周（周日数）                 |
| h    | 小时                               |
| n    | 分钟                               |
| s    | 秒                                |

&& date1 && 日期 && 第一个日期。 && date2 && 日期 && 第二个日期。 \</evalcmd\>

以*units*形式返回提供的两个日期之间的差值。

//<Example://>

    Output(DateDiff("yyyy", "2021-01-01", "2023-01-01"))
    --> 2