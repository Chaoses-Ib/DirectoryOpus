# Func

**Func** 对象在脚本通过命令调用时被传递给脚本。在 [脚本函数](/Manual/scripting/script_functions.zh.md) 中，它被传递给 **[OnClick](../scripting_events/onclick.zh.md)** 方法作为 **[ClickData](clickdata.zh.md).func** 属性，在 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 的脚本加载项中，通过 **[ScriptCommandData](scriptcommanddata.zh.md).func** 属性传递。**Func** 对象提供有关命令的默认源和目标的信息，以及有关它如何被调用的详细信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
args</td><td>

*object:***[Args](args.zh.md)**</td><td>

返回一个 **[Args](args.zh.md)** 对象，该对象提供对调用此脚本的命令行上给定的任何参数的访问权限。当脚本为 Opus 添加了 [内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 时，使用此方法。添加命令时可以提供命令行模板，用户在命令行上为脚本命令提供的任何参数都将通过此对象提供。
对于大多数情况，**argsmap** 属性可能是访问命令参数的更简单方法。
</td></tr><tr><td>
argsmap</td><td>

*object:***[Map](map.zh.md)**</td><td>

返回一个 **[Map](map.zh.md)** 对象，该对象提供命令行上给定的每个参数的关键字查找。只有在命令行上使用了某个参数时，它才会出现在 **[Map](map.zh.md)** 中，因此您可以使用 **[Map](map.zh.md).exists()** 方法轻松检查哪些参数存在。
</td></tr><tr><td>
command</td><td>

*object:***[Command](command.zh.md)**</td><td>

此属性返回一个预先填充的 **[Command](command.zh.md)** 对象，该对象可用于对源和目标标签页运行命令。使用此对象等效于调用 **[DOpusFactory](dopusfactory.zh.md).Command** 并手动设置源和目标标签页。
</td></tr><tr><td>
desttab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>
此对象表示函数的默认目标标签页。
</td></tr><tr><td>
fromdrop</td><td>

*bool*</td><td>

如果命令是通过拖放操作调用的，则返回 **True**。
</td></tr><tr><td>
fromkey</td><td>

*bool*</td><td>

如果命令是通过键盘调用的（即通过热键而不是按钮），则返回 **True**。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，表示用户在调用命令时按下的任何限定符键。

该字符串可以包含以下任何或所有内容：*shift*, *ctrl*, *alt*, *lwin*, *rwin*。

如果没有按下限定符，该字符串将为：*none*
</td></tr><tr><td>
sourcetab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>
此对象表示函数的默认源标签页。
</td></tr><tr><td>
viewer</td><td>

*object:***[Viewer](viewer.zh.md)**</td><td>

如果此按钮是从 [独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中运行的，则此对象表示查看器窗口。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Dlg</td><td>

*无*</td><td>

*object:***[Dialog](dialog.zh.md)**</td><td>

创建一个新的 **[Dialog](dialog.zh.md)** 对象，允许您显示对话框和弹出菜单。对话框的 **window** 属性将自动分配给源标签页。
</td></tr></tbody>
</table>