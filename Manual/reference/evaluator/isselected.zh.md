\<evalcmd\> IsSelected 和布尔值或整数 && 已选项目的测试结果。 && pattern && 字符串 && 带有前缀 **dirs: 的文件名通配符模式** 只匹配目录，或者 **files:只匹配文件。&& \[pattern...\] && 字符串 &&其它文件名模式... \</evalcmd\>

只指定了一个 *pattern*，如果匹配该模式的项目已选，则返回 **True**，否则返回 **False**。

指定了多个 pattern，如果选定项目不匹配任何 pattern，则返回 **0**，否则返回第一个匹配项的索引。

//<范例://>

    如果 (IsSelected("*.jpg")) { ... } // 选择一个或多个 jpg

*另请参见：* [filecount](filecount.zh.md)