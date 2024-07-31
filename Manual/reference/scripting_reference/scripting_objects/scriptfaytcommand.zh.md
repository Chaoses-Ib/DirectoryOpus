# ScriptFAYTCommand

当脚本调用 **[ScriptInitData](scriptinitdata.zh.md).AddCommand** 方法向 Opus 内部命令集 [添加命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 时，它检索到的 **[scriptcommand](scriptcommand.zh.md)** 对象在其 **fayt** 属性中提供了一个 **ScriptFAYTCommand** 对象。您可以初始化此对象以创建一个 [扩展即时查找字段](/Manual/scripting/example_scripts/extending_the_fayt.zh.md) 的命令。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
backcolor</td><td>

*string*</td><td>

指定即时查找扩展的默认背景颜色。它应采用 **\#RRGGBB**（十六进制）或 **RRR,GGG,BBB**（十进制）的形式。您应该使用此属性和 **textcolor** 属性来指定相同的深色和浅色，否则使用 **dark** 和 **light** 属性。
</td></tr><tr><td>
dark</td><td>

*object:***[ScriptColorPair](scriptcolorpair.zh.md)**</td><td>

使用返回的 **[ScriptColorPair](scriptcolorpair.zh.md)** 对象指定即时查找扩展的默认暗模式文本和背景颜色（并使用 **light** 属性指定亮模式颜色）。如果您希望默认暗模式和亮模式颜色相同，则可以使用 **textcolor** 和 **backcolor** 属性。
</td></tr><tr><td>
enable</td><td>

*bool*</td><td>

将此属性设置为 **True** 以启用即时查找扩展。
</td></tr><tr><td>
flags</td><td>

*object:***[Map](map.zh.md)**</td><td>

允许您指定一组用户可以通过用户界面打开或关闭的标志。要使用此功能，您需要将该属性分配给由 **[dopus](dopus.zh.md).[Create](dopusfactory.zh.md).Map** 方法创建的 **[map](map.zh.md)** 对象。

每个标志都应该使用其数值（二的幂；例如 1、2、4、8、...）作为键，并使用其标签作为值添加到映射中。当调用您的即时查找扩展时，Opus 会将用户选择的标志的值加在一起，并将其传递给您的命令。

您可以添加的最大标志数量为 16。
</td></tr><tr><td>
key</td><td>

*string*</td><td>
允许您指定即时查找扩展的默认键。从文件列表或即时查找字段中按下此键将调用脚本。
</td></tr><tr><td>
label</td><td>

*string*</td><td>
这允许您为即时查找扩展指定一个标签，该标签将在用户界面中显示。如果未提供，则使用命令的名称。
</td></tr><tr><td>
light</td><td>

*object:***[ScriptColorPair](scriptcolorpair.zh.md)**</td><td>

使用返回的 **[ScriptColorPair](scriptcolorpair.zh.md)** 对象指定即时查找扩展的默认亮模式文本和背景颜色（并使用 **dark** 属性指定暗模式颜色）。如果您希望默认暗模式和亮模式颜色相同，则可以使用 **textcolor** 和 **backcolor** 属性。
</td></tr><tr><td>
realtime</td><td>

*bool*  
或 *int*</td><td>

设置为 **True** 使您的扩展在用户键入时实时调用。如果设置为 **False**，您的扩展只会在用户按下 <kbd>Enter</kbd> 时被调用。如果设置为整数值，则它指定用户键入到调用脚本之间的时间（以毫秒为单位）（即延迟通知）。
</td></tr><tr><td>
textcolor</td><td>

*string*</td><td>

指定即时查找扩展的默认文本颜色。它应采用 **\#RRGGBB**（十六进制）或 **RRR,GGG,BBB**（十进制）的形式。您应该使用此属性和 **backcolor** 属性来指定相同的深色和浅色，否则使用 **dark** 和 **light** 属性。
</td></tr><tr><td>
wantempty</td><td>

*bool*</td><td>
如果不想为空字符串调用建议列表（即用户必须键入某些内容才能调用您的扩展），则将其设置为 false。
</td></tr></tbody>
</table>