**OnScriptColumn** 事件是 [自定义列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md) 的入口点,该列由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 添加。事件的实际名称由脚本本身定义,当通过 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).AddColumn** 方法添加命令时 - **OnScriptColumn** 仅仅是占位符名称。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnScriptColumn
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[ScriptColumnData](../scripting_objects/scriptcolumndata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*none*
</td></tr><tr><td>

**描述:**</td><td>

当脚本加载项使用 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).AddCommand** 添加新列时,它将使用 **ScriptColumn.method** 属性指定其入口点的名称。当 Opus 想为特定文件或文件夹检索该列的值时,Opus 将在你的脚本中调用此方法。  
**[ScriptColumnData](../scripting_objects/scriptcolumndata.zh.md).item** 属性提供关于有问题的文件或文件夹的信息,**col** 属性标识你应该为其返回数据的列(如果你为多个列使用同一个方法)。

此事件的返回值将被忽略 - 相反,你应通过在 **[ScriptColumnData](../scripting_objects/scriptcolumndata.zh.md)** 对象中设置适当的值来返回列数据(以及可选的分组和排序信息)。
</td></tr></tbody>
</table>