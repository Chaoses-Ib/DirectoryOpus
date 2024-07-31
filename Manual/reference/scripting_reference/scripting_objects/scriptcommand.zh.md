# ScriptCommand

在脚本的 **[OnInit](../scripting_events/oninit.zh.md)** 方法中，它可以调用 **[ScriptInitData](scriptinitdata.zh.md).AddCommand** 方法来 [添加命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 到 Opus 的内部命令集中。每次调用 **AddCommand** 都将返回一个 **ScriptCommand** 对象，脚本需要对其进行初始化。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
desc</td><td>

*string*</td><td>

使用此属性为命令设置描述，该描述会在用户从 [命令标签页](/Manual/customize/the_customize_dialog/commands.zh.md) 中选择命令时在 [自定义](/Manual/customize/README.zh.md) 对话框中显示。
</td></tr><tr><td>
fayt</td><td>

*object:***[ScriptFAYTCommand](scriptfaytcommand.zh.md)**</td><td>

返回一个 **[ScriptFAYTCommand](scriptfaytcommand.zh.md)** 对象，您可以使用它来初始化此命令以 [扩展即时查找字段](/Manual/scripting/example_scripts/extending_the_fayt.zh.md)。
</td></tr><tr><td>
hide</td><td>

*bool*</td><td>

设置为 **True** 可将此命令隐藏在 [命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md) 中显示的下拉命令列表中。这使您可以添加仍可在按钮和热键中使用的命令，但不会使命令列表变得混乱。
</td></tr><tr><td>
icon</td><td>

*string*</td><td>

使用此属性为该命令分配默认图标。您可以指定内部图标的名称（如果您想指定特定集合中的图标，请使用 *setname:iconname -* 仅当您将脚本与自己的图标集捆绑在 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md) 中时使用此方法）或外部图标或图像文件的路径。
</td></tr><tr><td>
label</td><td>

*string*</td><td>

使用此属性为命令设置标签。它将在 [自定义](/Manual/customize/README.zh.md) 对话框的 [命令标签页](/Manual/customize/the_customize_dialog/commands.zh.md) 中（在 *脚本命令* 类别下）显示，并且将形成如果用户将该命令拖放到工具栏中创建的按钮的默认标签。

命令的实际名称（用于调用命令）通过 **name** 属性分配。
</td></tr><tr><td>
method</td><td>

*string*</td><td>

这是当调用命令时 Opus 将在脚本中调用的方法的名称。这通常设置为 *OnXXXXX*，其中 *XXXXX* 是命令的名称，但可以使用任何方法名称。

当调用方法时，它将传递一个参数，一个 **[ScriptCommandData](scriptcommanddata.zh.md)** 对象。通常将此方法称为 **[OnScriptCommand](../scripting_events/onscriptcommand.zh.md)**。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
这是命令的名称。它决定了在按钮和热键中使用时调用命令的名称。
</td></tr><tr><td>
noprogress</td><td>

*bool*</td><td>
如果不想在选择多个文件时显示命令的进度指示器，请将其设置为 false。
</td></tr><tr><td>
template</td><td>

*string*</td><td>

这使您可以为命令指定可选的命令行模板。它是一个字符串，格式为 *ARGNAME1/MOD,ARGNAME2/MOD,ARGNAME3/MOD* 等，其中 ARGNAME 是参数的名称，而 /MOD 是一个或多个 [用于指示参数类型的修饰符](../../command_reference/argument_types.zh.md)。命令行模板可以指定任意数量的参数。

当调用您的命令并触发其 **[OnScriptCommand](../scripting_events/onscriptcommand.zh.md)** 事件时，命令行上提供的任何参数都将根据此模板进行解析，并通过 **[ScriptCommandData](scriptcommanddata.zh.md).[func](func.zh.md).args** 属性提供。
</td></tr></tbody>
</table>