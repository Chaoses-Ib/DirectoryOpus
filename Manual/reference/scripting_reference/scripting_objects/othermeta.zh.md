**OtherMeta** 对象是从 **[Metadata](metadata.zh.md).other** 属性中检索的。它提供了访问有关文件或文件夹的杂项信息的权限。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
autodesc</td><td>

*string*</td><td>
自动生成的描述字符串用于此项。与在文件窗口中“说明”列中显示的字符串相同。Opus 自动使用其它元数据为不同类型的文件生成说明，从而使其更合理。
</td></tr><tr><td>
dircount</td><td>

*int*</td><td>

对于已使用 **[GetSizes](../../command_reference/internal_commands/getsizes.zh.md)** 或类似方式计算了其大小的文件夹，此项提供直接位于该文件夹之下的子文件夹数。
</td></tr><tr><td>
dircounttotal</td><td>

*int*</td><td>

类似于 **dircount**，此项提供该文件夹之下的子文件总数（此项是递归计数 - 它包括子子文件夹、子子子文件夹，等等）
</td></tr><tr><td>
filecount</td><td>

*int*</td><td>

对于已使用 **[GetSizes](../../command_reference/internal_commands/getsizes.zh.md)** 或类似方式计算了其大小的文件夹，此项提供直接位于该文件夹中的文件数。
</td></tr><tr><td>
filecounttotal</td><td>

*int*</td><td>

类似于 **filecount**，此项提供某个文件夹及其所有子文件夹、子子文件夹、等等之中的文件总数
</td></tr><tr><td>
foldercontents</td><td>

*string*</td><td>

对于已使用 **[GetSizes](../../command_reference/internal_commands/getsizes.zh.md)** 或类似方式计算了其大小的文件夹，它返回一个字符串，以总结文件夹的内容。
</td></tr><tr><td>
nsdesc</td><td>

*string*</td><td>
该项的父虚拟文件系统自动生成的说明。
</td></tr><tr><td>
rating</td><td>

*int*</td><td>
返回此文件或文件夹的用户分配评级。
</td></tr><tr><td>
target</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回表示快捷方式和链接的目标路径的 **[Path](path.zh.md)** 对象。
</td></tr><tr><td>
target_type</td><td>

*string*</td><td>

返回一个 *string*，用于指示链接类型（*unknown*, *linkfile*, *dosfile*, *url*, *junction*, *softlink*）。
</td></tr><tr><td>
usercomment</td><td>
string</td><td>
返回文件或文件夹的用户分配说明。
</td></tr></tbody>
</table>