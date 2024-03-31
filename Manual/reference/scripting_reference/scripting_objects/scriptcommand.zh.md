在脚本的 **[OnInit](../scripting_events/oninit.zh.md)** 方法中，可以调用 **[ScriptInitData](scriptinitdata.zh.md).AddCommand** 方法向 Opus 内部命令集[添加命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)。每次调用 **AddCommand** 都会返回一个 **ScriptCommand** 对象，脚本需要对其进行初始化。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
desc</td><td>

*字符串*</td><td>

使用此设置命令的描述，当用户从 [Commands 标签页](/Manual/customize/the_customize_dialog/commands.zh.md) 中选择该命令时，会在 [自定义](/Manual/customize/README.zh.md) 对话框中显示该描述。
</td></tr><tr><td>
fayt</td><td>

*对象:***[scriptfaytcommand](scriptfaytcommand.zh.md)**</td><td>

返回一个 **[scriptfaytcommand](scriptfaytcommand.zh.md)** 对象，可用于初始化此命令以 [扩展即时查找字段](/Manual/scripting/example_scripts/extending_the_fayt.zh.md)。
</td></tr><tr><td>
hide</td><td>

*布尔值*</td><td>

勾选 **True**，以在 [命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md) 中显示的下拉命令列表中隐藏此命令。这样，你可以添加仍可在按钮和热键中使用的命令，但不会杂乱命令列表。
</td></tr><tr><td>
icon</td><td>

*字符串*</td><td>

使用此属性为此命令分配一个默认图标。你可以指定一个内部图标的名称（如果你想指定来自特定集合的图标，请使用 *setname:iconname -* 使用此方法，如果你将你的脚本打包在带自己图标集的 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md) 中）或外部图标或图像文件的路径。
</td></tr><tr><td>
label</td><td>

*字符串*</td><td>

使用此设置命令的标签。这会显示在 [自定义](/Manual/customize/README.zh.md) 对话框的 [命令标签页](/Manual/customize/the_customize_dialog/commands.zh.md)（在 *脚本命令* 类别下），如果用户将该命令拖到工具栏上，它将形成创建的按钮的默认标签。

命令的实际名称（用于调用命令）通过 **name** 属性进行分配。
</td></tr><tr><td>
method</td><td>

*字符串*</td><td>

这是 Opus 在调用命令时将在脚本中调用的方法的名称。这通常被设置为 *OnXXXXX*，其中 *XXXXX* 是命令的名称，但是可以使用任何方法名称。

当调用该方法时，它会传递一个参数，即 **[ScriptCommandData](scriptcommanddata.zh.md)** 对象。一般而言，此方法称为 **[OnScriptCommand](../scripting_events/onscriptcommand.zh.md)**。
</td></tr><tr><td>
name</td><td>

*字符串*</td><td>

这是命令的名称。这将确定在按钮和热键中使用命令时调用的名称。
</td></tr><tr><td>
noprogress</td><td>

*布尔值*</td><td>

如果你不希望你的命令在选择了多个文件时显示进度指示器，请将此设置为 false。
</td></tr><tr><td>
template</td><td>

*字符串*</td><td>

这允许你指定命令的可选命令行模板。这是一个格式为 *ARGNAME1/MOD,ARGNAME2/MOD,ARGNAME3/MOD* 等的字符串，其中 ARGNAME 是参数的名称，而 /MOD 是用于指示参数类型的 [一个或多个修饰符](../../command_reference/argument_types.zh.md)。命令行模板可以指定任意需要的参数。

当调用你的命令并且触发其 **[OnScriptCommand](../scripting_events/onscriptcommand.zh.md)** 事件时，根据此模板解析命令行上提供的任何参数，并通过 **[ScriptCommandData](scriptcommanddata.zh.md).[func](func.zh.md).args** 属性提供。
</td></tr></tbody>
</table>