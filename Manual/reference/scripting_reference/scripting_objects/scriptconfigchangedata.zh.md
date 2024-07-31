# ScriptConfigChangeData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnScriptConfigChange](../scripting_events/onscriptconfigchange.zh.md)** 事件，则该方法会在用户通过配置编辑器修改脚本配置时收到一个 **ScriptConfigChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
changed</td><td>

**[Vector](vector.zh.md)**:*string*</td><td>

返回一个包含已修改配置项名称的 **[Vector](vector.zh.md)**。
</td></tr></tbody>
</table>