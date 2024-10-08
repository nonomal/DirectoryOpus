# 日期和时间代码

以下代码用于向外部程序传递格式化的日期和时间字符串。它们也经常用于向内部命令传递日期字符串 - 例如，要创建一个以当前日期命名的文件夹，可以使用类似 **CreateFolder {date\|yyyyMMdd}** 的命令。

<table>
<thead><tr><th>
代码</th><th>
描述
</th></tr></thead><tbody><tr><td>

**{date\|***\<格式\>***}**</td><td>
当前日期（本地时间）。
</td></tr><tr><td>

**{dateu\|***\<格式\>***}**</td><td>
当前日期（UTC）。
</td></tr><tr><td>

**{time\|***\<格式\>***}**</td><td>
当前时间（本地时间）。
</td></tr><tr><td>

**{timeu\|***\<格式\>***}**</td><td>
当前时间（UTC）。
</td></tr></tbody>
</table>

*\<格式\>* 值是一个由各种 *标记* 组成的字符串，用于格式化日期和时间字符串。如果未指定格式，则使用您的默认系统日期和时间格式。

例如，**{date\|yyyy-MM-dd}** 将以 *2016-09-22* 的格式格式化日期，而 **{time\|HHmmss}** 将以 *084450* 的格式格式化时间。

虽然此页面主要介绍 **{date}**、**{dateu}**、**{time}** 和 **{timeu}** 代码，但下面描述的语法也用于其它使用日期和时间格式的地方。该语法基于 Windows 使用的语法，并添加了一些内容，如果您曾经自定义过 Windows 日期时间格式，应该很熟悉。

**D#、T# 和 A# 前缀：**日期格式可能以 **D#** 开头。时间格式可能以 **T#** 开头。统一格式（包含日期和时间字段的格式）可能以 **A#** 开头。虽然这些前缀对于 **{date}**、**{dateu}**、**{time}** 和 **{timeu}** 是可选的，因为格式类型是隐式的，但这些前缀在代码一起返回日期和时间的场景中是必需的。例如，在重命名文件时，文件的修改年份可以使用 **{modified\|D#yyyy}** 插入。

**特殊标志：** 一些特殊标志可以出现在格式字符串的开头，在任何 **D#**、**T#** 或 **A#** 前缀之后，以修改格式执行的方式。与主要格式标志一样，这些标志是 **区分大小写的**。如果同时使用两个或多个特殊标志，它们的顺序并不重要。

- **I** - **系统不变区域设置：**您的系统的语言设置（区域设置）会影响日期和时间格式。例如，**MMM** 和 **MMMM** 日期代码将以您的语言生成月份名称。**tt** 时间代码输出您的区域设置的“AM”和“PM”版本，甚至可能在不使用它们的地方完全缺失（例如法国）。您可以通过在格式字符串的开头放置一个 **I**（大写 i）来覆盖此行为并使用 **系统不变区域设置**。系统不变区域设置类似于北美区域设置，并在所有机器和设置上产生相同的结果。这可以与日期和时间格式一起使用。例如，在 6 月 23 日下午 10:52 运行 **{date\|Idd-MMM} {time\|Ihh:mm tt}** 将始终输出“23-Jun 10:52 PM”。

- **N** - **星期名称：**如果您希望一周内的日期被替换为星期名称（“星期一”、“今天”、“明天”等），类似于 *显示友好日期* 偏好选项，请在日期格式的开头使用 **N**（大写 n）。这只能与日期格式一起使用。例如，**{date\|Ndd-MMM-yyyy}** 将输出“今天”，如果 Opus 正在英文环境下运行。您可能不希望在 **{date}** 中使用星期名称，但它们也适用于重命名时的文件时间戳；例如，在重命名对话框中使用 **{modified\|D#Nyyyy-MM-dd}**。虽然可以组合 **I** 和 **N** 标志，但它们不会相互作用；星期名称始终以您配置 Opus 使用的语言输出。

- **M** - **毫秒：**如果您希望包含毫秒，类似于 *显示毫秒* 偏好选项，请在时间格式的开头使用 **M**（大写 m）字符。这只能与时间格式一起使用。包含毫秒时，它将始终添加到秒之后，并填充到三位数。例如，**{time\|MHH:mm:ss}** 将返回类似于“08:45:32.021”的时间。如果时间值没有毫秒精度，则毫秒部分将为零。

**日期代码** 使用以下标记 - 请注意，这些标记区分大小写！*ISO 周* 和 *ISO 年* 标记指的是 [ISO 周日期系统](http://en.wikipedia.org/wiki/ISO_week_date)。

<table>
<thead><tr><th>
日期标记</th><th>
描述
</th></tr></thead><tbody><tr><td>
d</td><td>
月份中的日期，以数字表示，一位数的日期不带前导零。
</td></tr><tr><td>
dd</td><td>
月份中的日期，以数字表示，一位数的日期带前导零。
</td></tr><tr><td>
D</td><td>
星期中的日期，以数字表示（1 = 星期日，7 = 星期六）。
</td></tr><tr><td>
DD</td><td>
星期中的日期，以数字表示（1 = 星期一，7 = 星期日）。
</td></tr><tr><td>
ddd</td><td>

星期中的日期，以三个字母的缩写表示（例如 *Wed*）。
</td></tr><tr><td>
dddd</td><td>

星期中的日期，以完整的名称表示（例如 *Wednesday*）。
</td></tr><tr><td>
w</td><td>
ISO 周数，不带前导零。
</td></tr><tr><td>
ww</td><td>
ISO 周数，带前导零。
</td></tr><tr><td>
W</td><td>
简单周数，不带前导零。
</td></tr><tr><td>
WW</td><td>
简单周数，带前导零。
</td></tr><tr><td>
M</td><td>
月份，以数字表示，不带前导零。
</td></tr><tr><td>
MM</td><td>
月份，以数字表示，带前导零。
</td></tr><tr><td>
MMM</td><td>

月份，以三个字母的缩写表示（例如 *Jan*）。
</td></tr><tr><td>
MMMM</td><td>

月份，以完整的名称表示（例如 *January*）。
</td></tr><tr><td>
y</td><td>

年份，以最后两位数字表示，但小于 10 的年份不带前导零（例如 *2009* -\> *9*）。
</td></tr><tr><td>
yy</td><td>

年份，以最后两位数字表示，带前导零（例如 *2009* -\> *09*）。
</td></tr><tr><td>
yyyy</td><td>
年份，以四位数字表示。
</td></tr><tr><td>
Y</td><td>
ISO 年份，以最后两位数字表示，不带前导零。（通常只与 ISO 周一起使用。如果您只需要普通年份，请勿使用。）
</td></tr><tr><td>
YY</td><td>
ISO 年份，以最后两位数字表示，带前导零。（通常只与 ISO 周一起使用。如果您只需要普通年份，请勿使用。）
</td></tr><tr><td>
YYYY</td><td>
ISO 年份，以四位数字表示。（通常只与 ISO 周一起使用。如果您只需要普通年份，请勿使用。）
</td></tr><tr><td>
gg</td><td>

纪元/年代字符串 - 如果要格式化的日期没有关联的年代，则忽略。
</td></tr></tbody>
</table>

**时间代码** 使用以下标记 - 这些标记也区分大小写。

<table>
<thead><tr><th>
时间标记</th><th>
描述
</th></tr></thead><tbody><tr><td>
h</td><td>
小时，不带前导零，12 小时制。
</td></tr><tr><td>
hh</td><td>
小时，带前导零，12 小时制。
</td></tr><tr><td>
H</td><td>
小时，不带前导零，24 小时制。
</td></tr><tr><td>
HH</td><td>
小时，带前导零，24 小时制。
</td></tr><tr><td>
m</td><td>
分钟，不带前导零。
</td></tr><tr><td>
mm</td><td>
分钟，带前导零。
</td></tr><tr><td>
s</td><td>

秒，不带前导零。（如果指定了特殊的 **M** 标志，则包含毫秒。见上文。）
</td></tr><tr><td>
ss</td><td>

秒，带前导零。（如果指定了特殊的 **M** 标志，则包含毫秒。见上文。）
</td></tr><tr><td>
t</td><td>

一个字符的 AM/PM 字符串（例如 *A* 或 *P*）。参见上面有关区域设置的说明。
</td></tr><tr><td>
tt</td><td>
多个字符的 AM/PM 字符串。参见上面有关区域设置的说明。
</td></tr></tbody>
</table>