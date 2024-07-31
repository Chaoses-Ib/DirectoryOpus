# ScriptInitData

**ScriptInitData** 对象在 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的 **[OnInit](../scripting_events/oninit.zh.md)** 事件中被传入。脚本应该初始化各种属性来识别自身，并且可以可选地使用 **AddCommand** 方法 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)，以及使用 **AddColumn** 方法 [添加自定义列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)，然后返回。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
config</td><td>

*object:***[ScriptConfig](scriptconfig.zh.md)**</td><td>

返回一个 **[ScriptConfig](scriptconfig.zh.md)** 对象，脚本可以使用它来初始化其默认配置。在此方法中添加到对象中的属性将显示在用户配置中，允许他们更改其值，从而配置脚本的行为。

如果您想保留配置项的顺序，您可以通过将新对象分配给 `config` 属性，将此对象替换为 **[OrderedMap](orderedmap.zh.md)**。
</td></tr><tr><td>
config_desc</td><td>

*object:***[Map](map.zh.md)**</td><td>

这允许您为脚本的配置选项分配描述，这些描述将在编辑器对话框中显示给用户。要做到这一点，请将此属性设置为通过 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建的 **[Map](map.zh.md)**，其中填充了名称/描述字符串对。
</td></tr><tr><td>
config_groups</td><td>

*object:***[Map](map.zh.md)**</td><td>

这允许您在编辑器对话框中显示给用户时，将脚本的配置选项组织到组中。组名是任意的 - 具有相同组名的配置选项将显示在一起。将此属性设置为通过 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建的 **[Map](map.zh.md)**，其中填充了名称/组字符串对。
</td></tr><tr><td>
copyright</td><td>

*string*</td><td>
让脚本指定一个版权信息，该信息将显示在用户配置中。
</td></tr><tr><td>
default_enable</td><td>

*bool*</td><td>

如果脚本应该默认启用，则将其设置为 **True**，如果应该默认禁用，则将其设置为 **False**。用户可以使用配置启用或禁用脚本 - 这只是控制默认状态。
</td></tr><tr><td>
desc</td><td>

*string*</td><td>
让脚本指定一个描述信息，该信息将显示在用户配置中。
</td></tr><tr><td>
early_dblclk</td><td>

*bool*</td><td>

如果您的脚本实现了 **[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件，并且（为了性能原因）您希望它只调用双击项目的路径而不是完整的 **[Item](item.zh.md)** 对象，则将其设置为 **True**。有关更多详细信息，请参见 **[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件文档。
</td></tr><tr><td>
file</td><td>

*string*</td><td>
返回此脚本的路径和文件名。
</td></tr><tr><td>
group</td><td>

*string*</td><td>
允许您为此脚本指定一个任意组。如果脚本指定了一个组，它们将在用户配置列表中的该组中显示。
</td></tr><tr><td>
log_prefix</td><td>
string</td><td>
让脚本指定一个字符串，该字符串将被附加到它执行的任何日志输出之前。如果未设置，则默认使用脚本的名称。
</td></tr><tr><td>
min_version</td><td>

*string*</td><td>

指定所需的最低 Opus 版本。如果当前版本小于指定的版本，脚本将被禁用。您可以只指定主版本（例如 *"11"*）、主版本和次版本（例如 *"11.3"*）或特定的 Beta 版本（例如 *"11.3.1"* 表示 11.3 Beta 1）。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
让脚本指定一个显示名称，该名称将在用户配置中显示。
</td></tr><tr><td>
startup</td><td>

*bool*</td><td>

**OnInit** 方法在两种不同的情况下被调用 - 一次在 Opus 启动时，以及在 Opus 已经运行时安装或编辑脚本时再次调用。如果 **OnInit** 方法是在 Opus 启动期间被调用，则此属性将返回 **True**，否则将返回 **False**。
</td></tr><tr><td>
url</td><td>

*string*</td><td>
允许您提供一个 URL，用户可以在该 URL 中找到有关您的脚本的更多信息（它将在用户配置中显示）。
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.zh.md)**</td><td>

返回一个 **[Vars](vars.zh.md)** 集合，该集合包含特定于此脚本的用户和脚本定义的变量。这些变量可以通过 **[Script](script.zh.md).vars** 属性在脚本中的其它方法中使用。
</td></tr><tr><td>
version</td><td>

*string*</td><td>
让脚本指定一个版本号字符串，该字符串将在用户配置中显示。
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

向 Opus 添加一个新的信息列。返回的 **[ScriptColumn](scriptcolumn.zh.md)** 对象必须被正确初始化。脚本加载项可以添加任意数量的列，这些列将在文件列表、信息提示和 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能中可用。

您的脚本可以实现 **[OnAddColumns](../scripting_events/onaddcolumns.zh.md)** 方法，而不是在 **OnInit** 中添加列。这更灵活，因为它允许您在添加列时访问脚本的配置，并且可以在 Opus 运行时动态添加和删除列。如果实现了 **[OnAddColumns](../scripting_events/onaddcolumns.zh.md)**，那么此方法在 **OnInit** 中不可用。
</td></tr><tr><td>
AddCommand</td><td>

*none*</td><td>

*object:***[ScriptCommand](scriptcommand.zh.md)**</td><td>

向 Opus 添加一个新的内部命令。返回的 **[ScriptCommand](scriptcommand.zh.md)** 对象必须被正确初始化。脚本加载项可以向 Opus 内部命令集中添加任意数量的内部命令。

您的脚本可以实现 **[OnAddCommands](../scripting_events/onaddcommands.zh.md)** 方法，而不是在 **OnInit** 中添加命令。这更灵活，因为它允许您在添加命令时访问脚本的配置，并且可以在 Opus 运行时动态添加和删除命令。如果实现了 **[OnAddCommands](../scripting_events/onaddcommands.zh.md)**，那么此方法在 **OnInit** 中不可用。
</td></tr></tbody>
</table>