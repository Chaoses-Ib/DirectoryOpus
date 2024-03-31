# Func

当脚本通过命令调用时，会将其传递给 **Func** 对象。在脚本函数（/Manual/scripting/script_functions.zh.md）中，会将其传递给 **[OnClick](../scripting_events/onclick.zh.md)** 方法作为 **[ClickData](clickdata.zh.md).func** 属性，并且在通过 **[ScriptCommandData](scriptcommanddata.zh.md).func** 属性添加内部命令脚本插件（/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md）中。**Func** 对象提供有关命令的默认源和目标的信息，以及有关如何调用的详细说明。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
args</td><td>

*object:***[Args](args.zh.md)**</td><td>

返回一个 **[Args](args.zh.md)** 对象，用于访问调用此脚本的命令行上给定的任何参数。当脚本将内部命令添加到 Opus 时，会使用此项。当添加命令时，可以提供命令行模板，并且用户在脚本命令的命令行上提供的任何参数都可通过此对象获得。

对于大多数用途，**argsmap** 属性可能是访问你的命令的参数的更简单方法。
</td></tr><tr><td>
argsmap</td><td>

*object:***[Map](map.zh.md)**</td><td>

返回一个 **[Map](map.zh.md)** 对象，用于对命令行上给出的每个参数进行关键词查找。如果参数在命令行上使用，它才会出现在 **[Map](map.zh.md)** 中，所以你可以轻松地使用 **[Map](map.zh.md).exists()** 方法来查看哪些参数可用。
</td></tr><tr><td>
command</td><td>

*object:***[Command](command.zh.md)**</td><td>

此属性返回一个预先填充的 **[Command](command.zh.md)** 对象，该对象可用于针对源和目标标签页运行命令。使用此对象相当于调用 **[DOpusFactory](dopusfactory.zh.md).Command** 并手动设置源和目标标签页。
</td></tr><tr><td>
desttab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>
此对象表示此函数的默认目标标签页。
</td></tr><tr><td>
fromdrop</td><td>

*bool*</td><td>

如果通过拖放操作调用命令，则返回 **True**。
</td></tr><tr><td>
fromkey</td><td>

*bool*</td><td>

如果通过键盘（即通过热键而不是按钮）调用命令，则返回 **True**。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，表示用户在调用命令时按下的任意限定键。

字符串可以包含以下任意或所有内容：*shift,* *ctrl*, *alt*, *lwin*, *rwin*。

如果没有按下限定键，则字符串为：*none*
</td></tr><tr><td>
sourcetab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>
此对象表示此函数的默认源标签页。
</td></tr><tr><td>
viewer</td><td>

*object:***[Viewer](viewer.zh.md)**</td><td>

如果从独立图像浏览器（/Manual/additional_functionality/viewing_images/README.zh.md）运行此按钮，则此对象表示浏览器窗口。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Dlg</td><td>

*none*</td><td>

*object:***[Dialog](dialog.zh.md)**</td><td>

创建一个新的 **[Dialog](dialog.zh.md)** 对象，可用于显示对话框和弹出菜单。对话框的 **window** 属性会自动分配给源标签页。
</td></tr></tbody>
</table>