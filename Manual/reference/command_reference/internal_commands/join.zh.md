# Join

**合并**内部命令可以将多个文件合并成一个单独的大文件。如果文件被分成了多个部分，通常用于通过电子邮件传输。

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
描述
</th></tr></thead><tbody><tr><td>

\<nobr\>*(无参数)*\</nobr\></td><td>
-</td><td>
-</td><td>

显示**[合并文件](/Manual/additional_functionality/joining_files.zh.md)** 对话框。所有当前选中的文件都将添加到列表中；你可以在对话框中重新整理此列表、从列表中删除项目，并添加其他项目。

*示例：* `Join`
</td></tr><tr><td>
CONVERT</td><td>
/K</td><td>
uudecode</td><td>

指定已合并的文件应为 uudecode。

*示例：* `Join /temp/part1.uuenc.txt /temp/part2.uuenc.txt CONVERT=uudecode TO /temp/original.bin`
</td></tr><tr><td>
</td><td>
</td><td>
base64</td><td>
已合并的文件将使用 base64 编码进行解码。
</td></tr><tr><td>
</td><td>
</td><td>
text</td><td>
文件将合并为文本。不同的编码格式将规范化成 UTF-8。
</td></tr><tr><td>
FROM</td><td>
/M</td><td>

*\<filename\> ...*</td><td>

指定要合并的文件。如果每个文件中包含空格，请务必用引号将每个文件括起来。

*示例：* `Join /temp/part1.bin /temp/part2.bin`
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(无值)*</td><td>

将合并的文件写入源文件夹，而不是目标文件夹。

*示例：* `Join HERE`
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<输出文件\>*</td><td>

指定合并的文件名。

*示例：* `Join part1.bin part2.bin part3.bin TO original.jpg HERE`
</td></tr></tbody>
</table>