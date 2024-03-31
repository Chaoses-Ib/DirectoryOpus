**OnAddColumns** 事件可用于允许你的 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) [添加列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。针对你想要添加的每一列调用 **[AddColData](../scripting_objects/addcoldata.zh.md).AddColumn** 方法一次。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnAddColumns
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[AddColData](../scripting_objects/addcoldata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*无*
</td></tr><tr><td>

**说明：**</td><td>

在 Opus 启动或脚本加载项添加、编辑或启用后，将调用其 **OnAddColumns** 方法。这允许脚本向 Opus [添加列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md) :scripting:example_scripts:adding_a_new_internal_command。脚本可以通过调用 **[Script](../scripting_objects/script.zh.md).InitColumns** 方法随时重新初始化其列列表。
</td></tr></tbody>
</table>