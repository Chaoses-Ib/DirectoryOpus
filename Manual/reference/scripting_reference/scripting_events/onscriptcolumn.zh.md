# OnScriptColumn

**OnScriptColumn** 事件是 [自定义列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md) 的入口点，该自定义列由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 添加。该事件的实际名称由脚本本身在使用 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).AddColumn** 方法添加命令时定义 - **OnScriptColumn** 只是一个占位符名称。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnScriptColumn
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ScriptColumnData](../scripting_objects/scriptcolumndata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

当脚本加载项使用 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).AddCommand** 添加新列时，它会使用 **ScriptColumn.method** 属性指定其入口点的名称。当 Opus 需要检索特定文件或文件夹的列值时，Opus 将在你的脚本中调用该方法。
**[ScriptColumnData](../scripting_objects/scriptcolumndata.zh.md).item** 属性提供了有关所述文件或文件夹的信息，而 **col** 属性标识你应该返回数据的列（如果你使用一个方法来处理多个列）。

该事件的返回值将被忽略 - 相反，你应该通过设置 **[ScriptColumnData](../scripting_objects/scriptcolumndata.zh.md)** 对象中的相应值来返回列数据（以及可选的排序和分组信息）。
</td></tr></tbody>
</table>