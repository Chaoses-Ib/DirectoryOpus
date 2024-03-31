# Split
**拆分**命令可以用来：

- 将一个文件拆分为两个或更多的较小部分
- 对拆分的文件进行 UU 编码，然后通过电子邮件/UseNet 传输

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
描述
</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

显示**[拆分文件](/Manual/additional_functionality/splitting_files.zh.md)**对话框，该对话框允许您将选中的文件拆分为可配置大小的部分。拆分的文件默认写入目标文件夹，并且其名称后会附加数字前缀以指示其顺序。

*示例：* `Split`
</td></tr><tr><td>
FROM</td><td>
/M</td><td>

*\<filename\>, ...*</td><td>

指定要拆分的文件。如果未提供此参数，则将使用当前源文件列表中选择的所有文件。如果文件名包含空格，请记住用引号引起来。这是**拆分**命令的默认参数，因此您无需指定**FROM**关键字。

*示例：* `Split "C:\Video Files\Video.avi"`
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(无值)*</td><td>

拆分的文件将写入当前源文件夹，而不是目标文件夹。

*示例：* `Split HERE`
</td></tr><tr><td>
SIZE</td><td>
/K</td><td>

*\<part size\>*</td><td>

指定拆分部分的大小。此参数允许您自动执行拆分功能。部分大小以字节、千字节（如果后跟**KB**后缀）、兆字节（如果后跟**MB**后缀）或千兆字节（如果后跟**GB**后缀）指定。

*示例：* `Split HERE SIZE 1.44MB`
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<destination\>*</td><td>

拆分的文件将写入指定的文件夹，而不是当前的目标文件列表。

*示例：* `Split SIZE 1000000 TO C:\SplitOutput`
</td></tr><tr><td>
UUENCODE</td><td>
/S</td><td>

*(无值)*</td><td>

对输出文件进行 Uuencode 编码。Uuencode 编码有时用于通过不支持 8 位数据的 Usenet 或其他通信媒体传输文件。

*示例：* `Split SIZE 1MB UUENCODE`
</td></tr></tbody>
</table>