# OnAddColumns

**OnAddColumns** 事件允许您的 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) [添加列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。 为您希望添加的每一列调用 **[AddColData](../scripting_objects/addcoldata.zh.md).AddColumn** 方法一次。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnAddColumns
</th></tr></thead><tbody><tr><td>

**参数类型：**</th><td>

**[AddColData](../scripting_objects/addcoldata.zh.md)**
</td></tr><tr><td>

**返回类型：**</th><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

当 Opus 启动时，或者当一个脚本加载项被添加、编辑或启用时，它的 **OnAddColumns** 方法就会被调用。 这允许脚本向 Opus [添加列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md) :scripting:example_scripts:adding_a_new_internal_command。 脚本可以通过调用 **[Script](../scripting_objects/script.zh.md).InitColumns** 方法随时重新初始化其列列表。
</td></tr></tbody>
</table>