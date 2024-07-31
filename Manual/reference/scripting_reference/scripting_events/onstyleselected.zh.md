# OnStyleSelected

**OnStyleSelected** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在用户选择新的 [文件窗口风格](/Manual/basic_concepts/the_lister/styles.zh.md) 时收到通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnStyleSelected
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[StyleSelectedData](../scripting_objects/styleselecteddata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

**StyleSelectedData.lister** 属性标识文件窗口，而 **style** 属性返回新选择的风格的名称。
</td></tr></tbody>
</table>