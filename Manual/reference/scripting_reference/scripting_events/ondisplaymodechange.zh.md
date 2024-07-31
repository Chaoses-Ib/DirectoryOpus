# OnDisplayModeChange

**OnDisplayModeChange** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在用户更改标签页的 [显示模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 时收到通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnDisplayModeChange
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[DisplayModeChangeData](../scripting_objects/displaymodechangedata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

**DisplayModeChangeData.tab** 属性标识标签页，**mode** 属性标识新的显示模式。
</td></tr></tbody>
</table>