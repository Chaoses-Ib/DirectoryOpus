**AddColData** 对象传递给 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 中的 **OnAddColumns** 事件。脚本可以使用此对象通过 **AddColumn** 方法来 [添加列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddColumn</td><td>

*无*</td><td>

*对象:***[ScriptColumn](scriptcolumn.zh.md)**</td><td>

向 Opus 中添加一个新的信息列。返回的 **[ScriptColumn](scriptcolumn.zh.md)** 对象必须正确初始化。脚本加载项可以根据需要添加多列，这些列可以在文件列表、提示信息以及 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能中使用。
</td></tr></tbody>
</table>