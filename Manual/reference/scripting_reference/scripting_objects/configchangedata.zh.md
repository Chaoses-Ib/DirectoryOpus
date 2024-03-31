如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现**[OnScriptConfigChange](../scripting_events/onscriptconfigchange.zh.md)** 事件，则该方法会在用户通过配置编辑器修改脚本配置时接收一个 **ConfigChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
changed</td><td>

**[Vector](vector.zh.md)**:*string*</td><td>

返回一个 **[Vector](vector.zh.md)**，其中包含修改的配置项目名称。
</td></tr></tbody>
</table>