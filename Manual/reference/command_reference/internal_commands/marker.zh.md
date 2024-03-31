# Marker

**Marker** 内部命令用于显示由第三方命名空间扩展动态添加的工具栏按钮和菜单项（它充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。例如，FTP 命名空间扩展可能向工具栏中添加按钮，以在 ASCII 和二进制传输模式之间切换。

资源管理器允许第三方命名空间扩展完全替换工具栏和菜单内容。然而，Directory Opus 使得用户能够完全控制工具栏的状态，因此需要 **Marker** 命令来标记这些命令出现的位置。

在 Windows 的后续版本中，Microsoft 已弃用允许命名空间扩展添加工具栏按钮的系统，因此如今经常不需要此命令，但出于向后兼容性考虑，它仍然存在。

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
描述
</th></tr></thead><tbody><tr><td>
HEADING</td><td>
/O</td><td>

*（无值）*</td><td>

当与生成项目列表的命令一起使用时（请参阅 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数在列表的开头添加一个小标题。在列表为空时将隐藏该标题。标题仅发生在有可能在按钮本身的相同级别生成多个项目的命令上。

当 **HEADING** 本身使用时，不指定文本值，主按钮的标签文本用于标题。

*示例:* `Marker TOOLBAR`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题\>*</td><td>

如果您希望标题文本不同于按钮的标签，则可以指定该文本。

*示例:* `Marker TOOLBAR HEADING="Extra Toolbar Commands"`
</td></tr><tr><td>
ID</td><td>
/K/N</td><td>

*\<id\>*</td><td>

将命名空间特定命令直接发送到当前在活动文件窗口中显示的命名空间文件夹。您需要知道命名空间使用的确切命令 ID，这可能很难确定。通常您永远不会直接使用此选项 - 当生成 **Marker** 命令添加的动态按钮时，Opus 会使用它。

*示例:* `Marker ID 1002`
</td></tr><tr><td>
MENU</td><td>
/K</td><td>

*\<名称\>*</td><td>

标记将显示命名空间特定菜单项的位置。*名称* 参数是与一个标准资源管理器菜单（**文件**、**编辑**、**查看**、**工具**、**帮助**）、**其他**（不适合这些菜单的命令）和 **全部**（所有命名空间特定菜单项）对应的关键字。

*示例:* `Marker MENU=file`
</td></tr><tr><td>
TOOLBAR</td><td>
/S</td><td>

*（无值）*</td><td>

标记显示命名空间特定工具栏按钮的位置。

*示例:* `Marker TOOLBAR`
</td></tr></tbody>
</table>