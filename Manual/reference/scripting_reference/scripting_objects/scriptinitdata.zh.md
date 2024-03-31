**ScriptInitData** 对象传递给脚本插件中的 **[OnInit](../scripting_events/oninit.zh.md)** 事件（/Manual/scripting/script_add-ins/README.zh.md）。脚本应该初始化各种属性以标识自身，并且可以选择使用 **AddCommand** 方法 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)，并在返回之前使用 **AddColumn** 方法 [自定义列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
config</td><td>

*object:***[ScriptConfig](scriptconfig.zh.md)**</td><td>

返回 **[ScriptConfig](scriptconfig.zh.md)** 对象，该对象可用于初始化脚本的默认配置。在此方法中添加到对象的属性将以配置显示给用户，允许他们更改其值，从而配置脚本的行为。
</td></tr><tr><td>
config_desc</td><td>

*object:***[Map](map.zh.md)**</td><td>

这允许你为脚本配置选项指定描述信息，这些描述信息以编辑程序对话框中显示给用户。为此，将此属性设置为通过 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建的 **[Map](map.zh.md)**，并填充名称/描述字符串对。
</td></tr><tr><td>
config_groups</td><td>

*object:***[Map](map.zh.md)**</td><td>

这允许你将脚本配置选项组织到组中，当在编辑程序对话框中显示给用户时。组名称是任意的 - 具有相同组名称的配置选项将显示为一组。将此属性设置为通过 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建的 **[Map](map.zh.md)**，并填充名称/组字符串对。
</td></tr><tr><td>
copyright</td><td>

*string*</td><td>
允许脚本指定在配置中显示给用户的版权消息。
</td></tr><tr><td>
default_enable</td><td>

*bool*</td><td>

如果脚本应默认启用，则将其设置为 **True**；如果脚本应默认禁用，则将其设置为 **False**。用户可以使用配置启用或禁用脚本 - 这仅控制默认状态。
</td></tr><tr><td>
desc</td><td>

*string*</td><td>
允许脚本指定在配置中显示给用户的描述消息。
</td></tr><tr><td>
early_dblclk</td><td>

*bool*</td><td>

如果你希望脚本实现 **[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件，并且（出于性能原因）你只希望被调用时提供双击的项目路径，而不是完整的 **[Item](item.zh.md)** 对象，则将其设置为 **True**。有关更多详细信息，请参阅 **[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件文档。
</td></tr><tr><td>
file</td><td>

*string*</td><td>
返回此脚本的路径和文件名。
</td></tr><tr><td>
group</td><td>

*string*</td><td>
允许你为该脚本指定任意组。如果脚本指定了一个组，它们将显示在配置列表中的该组中。
</td></tr><tr><td>
log_prefix</td><td>
string</td><td>
允许脚本指定一个字符串，该字符串将作为前缀，附加到它执行的任何日志输出中。如果没有设置，则默认使用脚本名称。
</td></tr><tr><td>
min_version</td><td>

*string*</td><td>

指定需要的 Opus 最低版本。如果当前版本低于指定版本，则脚本将被禁用。你只能指定主版本（例如，*“11”*），主版本和次要版本（例如，*“11.3”*）或特定 beta 版本（例如，*“11.3.1”*，表示 11.3 Beta 1）。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
允许脚本指定在配置中显示的脚本的显示名称。
</td></tr><tr><td>
startup</td><td>

*bool*</td><td>

**OnInit** 方法在两种不同的情况下被调用 - 一次是在 Opus 启动期间，当 Opus 已在运行时再次在安装或编辑脚本时。如果在 Opus 启动期间调用 **OnInit** 方法，则此属性将返回 **True**；否则，将返回 **False**。
</td></tr><tr><td>
url</td><td>

*string*</td><td>
允许你提供一个 URL，用户可以访问该 URL 查找有关脚本的更多信息（它以配置显示给用户）。
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.zh.md)**</td><td>

返回 **[Vars](vars.zh.md)** 收集用户和脚本定义的变量，这些变量是此脚本的局部变量。这些变量可通过 **[Script](script.zh.md).vars** 属性在脚本中的其他方法中使用。
</td></tr><tr><td>
version</td><td>

*string*</td><td>
允许脚本指定在配置中显示给用户的版本号字符串。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddColumn</td><td>

*none*</td><td>

*object:***[ScriptColumn](scriptcolumn.zh.md)**</td><td>

向 Opus 添加新的信息列。返回的 **[ScriptColumn](scriptcolumn.zh.md)** 对象必须已正确初始化。脚本插件可以根据需要添加任意多的列，并且这些列将可在文件列表、信息提示和 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能中使用。

你的脚本可以在 **OnInit** 中添加列，也可以实现 **[OnAddColumns](../scripting_events/onaddcolumns.zh.md)** 方法。这么做更灵活，因为它允许你在添加列时访问脚本的配置，并且可以在 Opus 运行时动态添加和删除列。如果实现了 **[OnAddColumns](../scripting_events/onaddcolumns.zh.md)**，则此方法在 **OnInit** 中不可用。
</td></tr><tr><td>
AddCommand</td><td>

*none*</td><td>

*object:***[ScriptCommand](scriptcommand.zh.md)**</td><td>

向 Opus 添加新的内部命令。返回的 **[ScriptCommand](scriptcommand.zh.md)** 对象必须已正确初始化。脚本插件可以根据需要向 Opus 内部命令集添加任意多的内部命令。

你的脚本可以在 **OnInit** 中添加命令，也可以实现 **[OnAddCommands](../scripting_events/onaddcommands.zh.md)** 方法。这么做更灵活，因为它允许你在添加命令时访问脚本的配置，并且可以在 Opus 运行时动态添加和删除命令。如果实现了 **[OnAddCommands](../scripting_events/onaddcommands.zh.md)**，则此方法在 **OnInit** 中不可用。
</td></tr></tbody>
</table>