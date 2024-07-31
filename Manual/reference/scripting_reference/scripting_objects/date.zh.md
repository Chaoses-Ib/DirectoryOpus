# Date

**Date** 对象旨在简化日期变量的处理。它会自动转换为 ActiveX *VT_DATE* 值，因此可以作为脚本语言的原生日期变量的直接替代。主要优势在于它保留了毫秒，而 *VT_DATE* 的精度仅为秒。它还提供了一些用于操作日期的实用方法。**[Item](item.zh.md)** 对象** **包含多个返回 **Date** 对象的属性。

可以使用 **[DOpusFactory](dopusfactory.zh.md).Date** 方法创建新的 **Date** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*date*</td><td>

返回一个代表此 **Date** 对象值的 *VT_DATE*（不包括毫秒）。
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

获取日期的 *day-of-the-week* 值。0 = 星期日，1 = 星期一，2 = 星期二，等等。
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
描述
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<int:value\>  
\<string:type\></td><td>

*none*</td><td>

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

*none*</td><td>

*object:***Date**</td><td>

返回一个新的 **Date** 对象，其值与当前对象相同。
</td></tr><tr><td>
Compare</td><td>

\<date:other\>  
\[\<string:type\>\]  
\[\<int:tolerance\>\]</td><td>

*int*</td><td>

将此日期与 *other* 日期进行比较。返回值将为 **0**（相等）、**1**（大于）或 **-1**（小于）。

可选的 *type* 字符串控制比较方式：

|        |                                                                                                                |
|--------|----------------------------------------------------------------------------------------------------------------|
| **s**  | 忽略秒。如果指定，则可选的 *tolerance* 参数指定以秒为单位的比较容差。                                    |
| **sD** | 忽略秒，并自动补偿夏令时。                                                                             |
| **t**  | 仅比较时间                                                                                             |
| **d**  | 仅比较日期                                                                                             |
</td></tr><tr><td>
Format</td><td>

\[\<string:format\>\]  
\[\<string:flags\>\]</td><td>

*string*</td><td>

返回格式化的日期或时间字符串。*format* 和 *flags* 参数都是可选的。

如果不提供 *format*，则结果将包含日期和时间，格式与文件列表中的日期时间列相同。

如果将 *format* 设置为 **"d"** 或 **"t"**，则结果将仅为日期或时间部分，格式与文件列表中的日期或时间列相同。

文件列表的格式取决于用户的区域设置和 Windows 设置。如果您希望以用户期望的方式向用户呈现日期/时间，则应使用这些选项，但如果您需要以特定格式存储日期/时间，则不应使用这些选项。

当使用文件列表的格式（即，*format* 参数为空、**"d"** 或 **"t"**）时，您可以在第二个 *flags* 参数中选择性地传递一个或多个区分大小写的标志，以覆盖一些设置：

|       |                                                                                                                    |
|-------|--------------------------------------------------------------------------------------------------------------------|
| **N** | 强制在过去一周内的日期中显示星期名称。"今天"、"星期一" 等。                                          |
| **n** | 强制关闭星期名称。                                                                                               |
| **S** | 强制在时间中显示秒。                                                                                         |
| **s** | 强制关闭秒。                                                                                                 |
| **M** | 强制在时间中显示毫秒。（如果存储的时间没有毫秒精度，则毫秒将为零。）                                      |
| **m** | 强制关闭毫秒。                                                                                            |
| **P** | 强制将时间小时数填充为两位数字。                                                                       |
| **p** | 不强制填充时间小时数。                                                                              |

例如，要仅获取日期，使用用户的区域设置，但强制关闭星期名称：

    myDate.Format("d","n")

要获取日期和时间，使用用户的区域设置，但强制打开星期名称并强制关闭秒：

    myDate.Format("","Ns")

*format* 还可以使用 [日期和时间代码](../../command_reference/external_control_codes/codes_for_date_and_time.zh.md) 中所示的语法，允许使用任意格式。例如，

    myDate.Format("D#yyyy-MM-dd T#HH:mm:ss")

这将返回一个类似 **2023-07-28 15:45:26** 的字符串。

在显式指定格式时，不应使用 *flags* 参数，它将被忽略。
</td></tr><tr><td>
FromUTC</td><td>

*none*</td><td>

*object:***Date**</td><td>

返回一个新的 **Date** 对象，其日期已从 UTC（基于本地时区）转换。
</td></tr><tr><td>
Reset</td><td>

*none*</td><td>

*none*</td><td>
将日期重置为当前本地日期/时间。
</td></tr><tr><td>
Set</td><td>

\<date:newdate\></td><td>

*none*</td><td>

将此 **Date** 对象的值设置为提供的日期。*newdate* 可以是：

- 另一个 **Date** 对象
- "yyyymmdd" 格式的字符串
- "yyyy-mm-dd hh:mm:ss.mmm" 格式的字符串（或其一部分）
- JScript **Date** 对象
- Unix 纪元时间值（自 1970 年 1 月 1 日以来的秒数）。
- "now" 字符串（设置为当前时间）
</td></tr><tr><td>
Sub</td><td>

\<int:value\>  
\<string:type\></td><td>

*none*</td><td>

从日期中减去指定的值。参数与 **Add** 方法的参数相同。
</td></tr><tr><td>
ToUTC</td><td>

*none*</td><td>

*object:***Date**</td><td>

返回一个新的 **Date** 对象，其日期已转换为 UTC（基于本地时区）。
</td></tr></tbody>
</table>