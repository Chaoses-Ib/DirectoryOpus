# 列上下文菜单

与任何其它 [工具栏或菜单](functions/README.zh.md) 一样，列标题上下文菜单中的函数可以使用运算符，但在此求值上下文中，有以下特定于列标题的变量可用：

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
frozenfields</td><td>

*int*</td><td>
冻结列的数量。
</td></tr><tr><td>
group</td><td>

*int*</td><td>

文件列表进行分组的列的 ID，如果没有则为 `-1`。您可以将此 ID 传递给命令，例如 `Set GROUPBY=x,toggle`
</td></tr><tr><td>
groupkey</td><td>

*str*</td><td>
文件列表进行分组的列的关键字。
</td></tr><tr><td>
groupname</td><td>

*str*</td><td>
文件列表进行分组的列的名称。
</td></tr><tr><td>
groupscheme</td><td>

*str*</td><td>
当前分组方案的名称（如果有）。
</td></tr><tr><td>
header</td><td>

*int*</td><td>

右键单击的列的 ID，如果没有则为 `-1`。您可以将此 ID 传递给命令，例如 `Set COLUMNSTOGGLE=x`。
</td></tr><tr><td>
headerindex</td><td>

*int*</td><td>
右键单击的标题项的位置。
</td></tr><tr><td>
headerinsert</td><td>

*int*</td><td>

插入点。与 *headerindex* 类似，但如果单击位于项的右侧区域，则为 +1。
</td></tr><tr><td>
headeritem</td><td>

*int*</td><td>

已弃用。与 *headerinsert* 相同。
</td></tr><tr><td>
headerkey</td><td>

*str*</td><td>
右键单击的列的关键字。
</td></tr><tr><td>
headername</td><td>

*str*</td><td>
右键单击的列的名称。
</td></tr><tr><td>
path</td><td>

*path*</td><td>
返回文件列表中显示的路径。
</td></tr></tbody>
</table>