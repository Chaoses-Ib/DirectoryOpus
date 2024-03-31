**OnInit** 事件对于每个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 仅调用一次，以对其进行初始化。在程序启动时，以及当 Opus 已在运行时添加或编辑脚本时，将调用此事件。实施 **OnInit** 事件是可选的，但强烈建议这样做，因为它使您可以提供要在配置中向用户显示的名称、描述和其他信息。它还为脚本提供了一种 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 和 [列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md) 的方法（尽管 **[OnAddCommands](onaddcommands.zh.md)** 和 **[OnAddColumns](onaddcolumns.zh.md)** 方法提供了更好的执行此操作的方法）。

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

在 Opus 启动时，或者在添加或编辑脚本加载项时，将调用其 **OnInit** 方法。通过设置 **ScriptInitData** 对象的各种属性，这给了脚本一个机会来告诉 Opus 它自身的信息。还可以通过此事件来使用 **AddCommand** 方法向 Opus 命令集 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)，可以使用 AddColumn 方法 [添加列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。<br><br>如果您从此方法返回 **True**，那么脚本将被禁用，直到下次调用 **OnInit** 为止（正常情况下，这将是下次运行 Opus 时）。例如，如果您脚本的 Windows 版本不适用，您可能希望执行此操作。
</td></tr></tbody>
</table>