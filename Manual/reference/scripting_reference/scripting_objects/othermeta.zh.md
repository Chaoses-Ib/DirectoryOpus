# OtherMeta

**OtherMeta** 对象可以通过 **[Metadata](metadata.zh.md).other** 属性获取。它提供了关于文件或文件夹的各种信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
autodesc</td><td>

*string*</td><td>
自动生成的项目描述字符串。这与文件窗口中“描述”列显示的字符串相同。Opus 使用其它元数据以最合理的方式自动生成各种类型文件的描述。
</td></tr><tr><td>
dircount</td><td>

*int*</td><td>

对于通过 **[GetSizes](../../command_reference/internal_commands/getsizes.zh.md)** 或类似方法计算过大小的文件夹，它提供了该文件夹下直接子文件夹的数量。
</td></tr><tr><td>
dircounttotal</td><td>

*int*</td><td>

类似于 **dircount**，它提供了该文件夹下所有子文件夹（包括子子文件夹、子子子文件夹等）的总数。
</td></tr><tr><td>
filecount</td><td>

*int*</td><td>

对于通过 **[GetSizes](../../command_reference/internal_commands/getsizes.zh.md)** 或类似方法计算过大小的文件夹，它提供了该文件夹下直接文件数量。
</td></tr><tr><td>
filecounttotal</td><td>

*int*</td><td>

类似于 **filecount**，它提供了该文件夹及其所有子文件夹、子子文件夹等中的文件总数。
</td></tr><tr><td>
foldercontents</td><td>

*string*</td><td>

对于通过 **[GetSizes](../../command_reference/internal_commands/getsizes.zh.md)** 或类似方法计算过大小的文件夹，它返回一个字符串，提供该文件夹内容的摘要。
</td></tr><tr><td>
nsdesc</td><td>

*string*</td><td>
由父虚拟文件系统自动生成的项目描述。
</td></tr><tr><td>
rating</td><td>

*int*</td><td>
返回用户分配给该文件或文件夹的评分。
</td></tr><tr><td>
target</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个代表快捷方式和链接的目标路径的 **[Path](path.zh.md)** 对象。
</td></tr><tr><td>
target_type</td><td>

*string*</td><td>

返回一个表示链接类型的字符串（*unknown*、*linkfile*、*dosfile*、*url*、*junction*、*softlink*）。
</td></tr><tr><td>
usercomment</td><td>
string</td><td>
返回用户分配给文件或文件夹的描述。
</td></tr></tbody>
</table>