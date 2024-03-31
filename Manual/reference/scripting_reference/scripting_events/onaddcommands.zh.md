**OnAddCommands** 事件被调用以允许你的 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)。对于你想要添加的每个命令，调用一次 **[AddCmdData](../scripting_objects/addcmddata.zh.md).AddCommand** 方法。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnAddCommands
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[AddCmdData](../scripting_objects/addcmddata.zh.md)**
</td></tr><tr><td>

**返回类型:**</td><td>

*none*
</td></tr><tr><td>

**描述:**</td><td>

当 Opus 启动时，或当脚本加载项添加、编辑或启用时，其 **OnAddCommands** 方法被调用。这允许脚本将 [内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 添加到 Opus 命令集中。脚本可以通过调用 **[Script](../scripting_objects/script.zh.md).InitCommands** 方法随时重新初始化其命令列表。
</td></tr></tbody>
</table>