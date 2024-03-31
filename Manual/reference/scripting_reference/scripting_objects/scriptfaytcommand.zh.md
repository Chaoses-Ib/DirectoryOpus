当脚本调用 **[ScriptInitData](scriptinitdata.zh.md).AddCommand** 方法以将命令 [添加到](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) Opus 内部命令集，它检索的 **[scriptcommand](scriptcommand.zh.md)** 对象会在 **fayt** 属性中提供一个 **Script即时查找Command** 对象。您可以初始化此对象以创建 [扩展即时查找字段](/Manual/scripting/example_scripts/extending_the_fayt.zh.md) 的命令。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
backcolor</td><td>

*string*</td><td>

为您的即时查找扩展指定默认背景色。这应该是 **\#RRGGBB**（十六进制）或 **RRR,GGG,BBB**（十进制）形式。您应该将它与 **textcolor** 属性一起使用，以将深色和浅色都指定为相同，否则使用 **dark** 和 **light** 属性。
</td></tr><tr><td>
dark</td><td>

*object:***[ScriptColorPair](scriptcolorpair.zh.md)**</td><td>

使用此返回的 **[ScriptColorPair](scriptcolorpair.zh.md)** 对象来为您的即时查找扩展指定默认深色模式文本和背景颜色（并使用 **light** 属性来指定浅色模式颜色）。如果您希望默认深色和浅色相同，可以使用 **textcolor** 和 **backcolor** 属性。
</td></tr><tr><td>
enable</td><td>

*bool*</td><td>

将此属性设置为 **True** 以启用即时查找扩展。
</td></tr><tr><td>
flags</td><td>

*object:***[Map](map.zh.md)**</td><td>

允许您指定一组标志，用户可以通过用户界面打开或关闭这些标志。要使用此功能，您需要将属性分配给由 **[dopus](dopus.zh.md).[Create](dopusfactory.zh.md).Map** 方法创建的 **[map](map.zh.md)** 对象。

每个标志都应该用其数值（2 的幂；例如 1、2、4、8、...）作为键，并将其标签作为值添加到映射中。当调用您的即时查找扩展时，Opus 将用户已选择的标志值相加并传递给您的命令。

您可以添加的最大标志数量为 16。
</td></tr><tr><td>
key</td><td>

*string*</td><td>
允许您为您的即时查找扩展指定默认键。从文件列表或即时查找字段按下此键将调用脚本。
</td></tr><tr><td>
label</td><td>

*string*</td><td>
这允许您为您的即时查找扩展指定一个标签，该标签显示在用户界面中。如果没有提供，则使用命令的名称。
</td></tr><tr><td>
light</td><td>

*object:***[ScriptColorPair](scriptcolorpair.zh.md)**</td><td>

使用此返回的 **[ScriptColorPair](scriptcolorpair.zh.md)** 对象来为您的即时查找扩展指定默认浅色模式文本和背景颜色（并使用 **dark** 属性来指定深色模式颜色）。如果您希望默认深色和浅色相同，可以使用 **textcolor** 和 **backcolor** 属性。
</td></tr><tr><td>
realtime</td><td>

*bool*  
或 *int*</td><td>

设置为 **True** 以在用户输入时实时调用您的扩展。如果设置为 **False**，则只有当用户按下 <kbd>Enter</kbd> 时才调用您的扩展。如果设置为整数，则指定用户键入与调用脚本之间的时间（即延迟通知）。
</td></tr><tr><td>
textcolor</td><td>

*string*</td><td>

为您的即时查找扩展指定默认文本颜色。这应该是 **\#RRGGBB**（十六进制）或 **RRR,GGG,BBB**（十进制）形式。您应该将它与 **backcolor** 属性一起使用，以将深色和浅色都指定为相同，否则使用 **dark** 和 **light** 属性。
</td></tr><tr><td>
wantempty</td><td>

*bool*</td><td>
如果您不想因空字符串的建议列表而被调用，请将其设置为 false（即用户必须在调用您的扩展之前键入一些内容）。
</td></tr></tbody>
</table>