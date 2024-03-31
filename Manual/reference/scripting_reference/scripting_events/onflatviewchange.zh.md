[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 可以实现 **OnFlatViewChange** 事件接收用户无论何时在标签页中更改 [显示模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 的通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnFlatViewChange
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[FlatViewChangeData](../scripting_objects/flatviewchangedata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*无*
</td></tr><tr><td>

**说明：**</td><td>

**FlatViewChangeData.tab** 属性可标识标签页，而 **mode** 属性可标识新的“平面视图”模式（“off”、“grouped”、“mixed”、“mixednofolders”）。
</td></tr></tbody>
</table>