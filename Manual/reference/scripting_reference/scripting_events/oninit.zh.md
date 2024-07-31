# OnInit

**OnInit** 事件在每个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 初始化时被调用一次。该事件会在程序启动时被调用，如果在 Opus 运行时添加或编辑脚本，也会被调用。实现 **OnInit** 事件是可选的，但强烈推荐，因为它允许您提供一个名称、描述和其它信息，以便在配置中向用户显示。它还为脚本提供了一种方式来 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 和 [列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)（尽管 **[OnAddCommands](onaddcommands.zh.md)** 和 **[OnAddColumns](onaddcolumns.zh.md)** 方法提供了更好的方法来执行此操作）。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnInit
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ScriptInitData](../scripting_objects/scriptinitdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool*
</td></tr><tr><td>

**描述：**</td><td>

当 Opus 启动，或当脚本加载项被添加或编辑时，它的 **OnInit** 方法会被调用。这为脚本提供了一个机会，通过设置 **ScriptInitData** 对象的各种属性来告诉 Opus 有关自身的信息。**AddCommand** 方法也可以从该事件中使用来 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 到 Opus 命令集中，AddColumn 方法可以用来添加 [列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。
如果您从该方法返回 **True**，则脚本将被禁用，直到下次调用 **OnInit**（通常是在下次运行 Opus 时）。例如，如果 Windows 的版本不适合您的脚本，您可能需要这样做。
</td></tr></tbody>
</table>