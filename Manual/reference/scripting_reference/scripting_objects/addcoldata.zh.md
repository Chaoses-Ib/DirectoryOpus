# AddColData

**AddColData** 对象在 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的 **OnAddColumns** 事件中被传递。脚本可以使用它通过 **AddColumn** 方法 [添加列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。

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

在 Opus 中添加一个新的信息列。返回的 **[ScriptColumn](scriptcolumn.zh.md)** 对象必须被正确初始化。脚本加载项可以添加任意数量的列，这些列将在文件列表、信息提示和 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能中可用。
</td></tr></tbody>
</table>