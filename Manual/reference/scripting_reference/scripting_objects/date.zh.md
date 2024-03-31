# 日期

提供了 **Date** 对象，以便更容易地处理表示日期的变量。它会自动转换为 ActiveX *VT_DATE* 值，因此可以作为脚本语言的原生日期变量的插入式替换。它的主要优势在于保留毫秒，而 *VT_DATE* 具有 1 秒分辨率。它还提供了一些用于处理日期的实用方法。**[Item](item.zh.md)** 对象**有许多返回**Date** 对象的属性。

可以使用 **[DOpusFactory](dopusfactory.zh.md).Date** 方法创建一个新的 **Date** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*date*</td><td>

返回一个表示此 **Date** 对象的值（不包括毫秒）的 *VT_DATE*。
</td></tr><tr><td>
day</td><td>

*int*</td><td>

获取或设置日期的 *day* 值。
</td></tr><tr><td>
hour</td><td>

*int*</td><td>

获取或设置日期的 *hour* 值。
</td></tr><tr><td>
min</td><td>

*int*</td><td>

获取或设置日期的 *minute* 值。
</td></tr><tr><td>
month</td><td>

*int*</td><td>

获取或设置日期的 *month* 值。
</td></tr><tr><td>
ms</td><td>

*int*</td><td>

获取或设置日期的 *milliseconds* 值。
</td></tr><tr><td>
sec</td><td>

*int*</td><td>

获取或设置日期的 *seconds* 值。
</td></tr><tr><td>
wday</td><td>

*int*</td><td>

获取日期的 *day-of-the-week* 值。
</td></tr><tr><td>
year</td><td>

*int*</td><td>

获取或设置日期的 *year* 值。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>
**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<int:value\>  
\<string:type\></td><td>

*无*</td><td>

将指定的值添加到日期。指定值的解释由 *type* 字符串控制：

|       |              |
|-------|--------------|
| **l** | 毫秒 |
| **s** | 秒      |
| **m** | 分钟      |
| **h** | 小时        |
| **d** | 天         |
| **w** | 周        |
| **M** | 月       |
| **y** | 年        |
</td></tr><tr><td>
Clone</td><td>

*无*</td><td>

*对象：***Date**</td><td>

返回一个新的 **Date** 对象，设置为与该对象相同的日期。
</td></tr><tr><td>
Compare</td><td>

\<date:other\>  
\[\<string:type\>\]  
\[\<int:tolerance\>\]</td><td>

*int*</td><td>

将此日期与 *other* 日期进行比较。返回值为 **0**（相等）、**1**（大于）或 **-1**（小于）。

可选的 *type* 字符串控制如何执行比较：

|        |                                                                                                                |
|--------|----------------------------------------------------------------------------------------------------------------|
| **s**  | 忽略秒数。如果指定了，可选的 *tolerance* 参数将指定以秒为单位的比较容差。 |
| **sD** | 忽略秒数，并自动补偿夏令时。                                             |
| **t**  | 仅比较时间                                                                                             |
| **d**  | 仅比较日期                                                                                             |
</td></tr><tr><td>
Format</td><td>

\[\<string:format\>\]  
\[\<string:flags\>\]</td><td>

*string*</td><td>

返回一个格式化的日期或时间字符串。*format* 和 *flags* 参数都是可选的。

如果不提供 *format*，结果将包括日期和时间，格式与文件列表中的日期时间列相同。

如果您提供的 *format* 仅为“**"d"**”或**"t"**”，那么结果将只是日期或时间部分，格式与文件列表中的日期或时间列相同。

文件列表的格式取决于用户的语言环境和 Windows 设置。如果您希望以用户期望的方式向用户呈现日期/时间，应该使用这些选项，但如果您需要将它们存储在特定格式中，则不应使用这些选项。

当使用文件列表的格式时（即 *format* 参数为空、**"d"** 或 **"t"**），您还可以在第二个 *flags* 参数中传递一个或多个区分大小写的标志，以覆盖一些设置：

|       |                                                                                                                    |
|-------|--------------------------------------------------------------------------------------------------------------------|
| **N** | 强制在过去一周内的日期中显示星期几名称。“今天”、“星期一”等。                                          |
| **n** | 强制不显示星期几名称。                                                                                               |
| **S** | 强制在时间中显示秒数。                                                                                         |
| **s** | 强制不显示秒数。                                                                                                 |
| **M** | 强制在时间中显示毫秒。（如果存储的时间没有毫秒精度，则毫秒将为零。） |
| **m** | 强制不显示毫秒。                                                                                            |
| **P** | 强制时间小时数填充为两位数。                                                                       |
| **p** | 不强制时间小时数填充。                                                                              |

例如，要仅获取日期（使用用户的语言环境），但强制关闭星期几名称：

    myDate.Format("d","n")

要获取日期和时间（使用用户的语言环境），但强制打开星期几名称和关闭秒数：

    myDate.Format("","Ns")

*format* 还可以使用 [日期和时间的代码](../../command_reference/external_control_codes/codes_for_date_and_time.zh.md) 中所示的语法，从而允许采用任意格式。例如，

    myDate.Format("D#yyyy-MM-dd T#HH:mm:ss")

这将返回一个类似 **2023-07-28 15:45:26** 的字符串。

当显式指定格式时，不应使用 *flags* 参数，它将被忽略。
</td></tr><tr><td>
FromUTC</td><td>

*无*</td><td>

*对象：***Date**</td><td>

返回一个新 **Date** 对象，其中日期已从 UTC 转换（基于本地时区）。
</td></tr><tr><td>
Reset</td><td>

*无*</td><td>

*无*</td><td>
将日期重置为当前的本地日期/时间。
</td></tr><tr><td>
Set</td><td>

\<date:newdate\></td><td>

*无*</td><td>

将此 **Date** 对象的值设置为提供的日期。*newdate* 可以是：

- 另一个 **Date** 对象
- 格式为“yyyymmdd”的字符串
- 格式为“yyyy-mm-dd hh:mm:ss.mmm”（或其一部分）的字符串
- JScript **Date** 对象
- unix epoch 时间值（自 1/1/1970 以来经过的秒数）。
- 字符串“now”（设置为当前时间）
</td></tr><tr><td>
Sub</td><td>

\<int:value\>  
\<string:type\></td><td>

*无*</td><td>

从日期中减去指定的值。参数与 **Add** 方法的参数相同。
</td></tr><tr><td>
ToUTC</td><td>

*none*</td><td>

*object:***Date**</td><td>

返回一个新的 **Date** 对象，该对象的日期已转换为 UTC（基于本地时区）。
</td></tr></tbody>
</table>