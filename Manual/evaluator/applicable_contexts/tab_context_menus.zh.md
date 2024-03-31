# 标签上下文菜单

[文件夹标签上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md) 中的函数可以使用求值器，就像在任何其他 [工具栏或菜单](functions/README.zh.md) 中一样，但是在此求值上下文中，可以使用以下特定于文件夹标签的变量：

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>
返回标签的数目。
</td></tr><tr><td>
countdual</td><td>

*int*</td><td>
在双栏文件窗口中，返回另一个文件列表中的标签数目。
</td></tr><tr><td>
dual</td><td>

*bool*</td><td>

如果这是双栏文件窗口，返回 **true**，否则对单显示返回 **false**。
</td></tr><tr><td>
path</td><td>

*path*</td><td>
返回在右键单击的标签中显示的路径。
</td></tr><tr><td>
right</td><td>

*bool*</td><td>

如果这是右/下文件列表，返回 **true**，如果它是上/左文件列表，返回 **false**。
</td></tr><tr><td>
sel</td><td>

*int*</td><td>

返回右键单击的标签的索引，如果未在标签上单击，则返回 `-1`。
</td></tr></tbody>
</table>