\<evalcmd\> 年龄 && 整数 && 当前日期与提供日期之间的差额。 && 日期 && 日期 && 有问题的日期。 && \[单位\] && 字符串 && 要返回的值单位类型（默认值为“d”，表示天数）。有效值类型如下：

|      |                                    |
|------|------------------------------------|
| yyyy | 年份                              |
| q    | 季度                              |
| m    | 月份                             |
| y    | 天                               |
| d    | 天                               |
| w    | 整周                            |
| ww   | 日历周（星期日数量）             |
| h    | 小时                              |
| n    | 分钟                            |
| s    | 秒                            |

\</evalcmd\>

（Opus 13.3.4 及更高版本）

返回当前日期与提供日期之间的差额，表示为 *单位*（默认为天）。

//<示例://>

    输出(年龄("2021-01-01"))
    --> 1158