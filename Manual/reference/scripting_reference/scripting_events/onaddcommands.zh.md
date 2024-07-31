# OnAddCommands

当需要你的 [脚本加载项](/Manual/scripting/script_add_ins/README.zh.md) 去 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 时，会调用 **OnAddCommands** 事件。 为每个你希望添加的命令调用 **[AddCmdData](../scripting_objects/addcmddata.zh.md).AddCommand** 方法一次。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnAddCommands
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[AddCmdData](../scripting_objects/addcmddata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*none*
</td></tr><tr><td>

**描述：**</td><td>

当 Opus 启动时，或者当一个脚本插件被添加、编辑或启用时，会调用它的 **OnAddCommands** 方法。 这允许脚本向 Opus 命令集中 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)。 脚本可以通过调用 **[Script](../scripting_objects/script.zh.md).InitCommands** 方法随时重新初始化其命令列表。
</td></tr></tbody>
</table>