# OnTabClick

**OnTabClick** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在使用限定键点击标签页时接收通知。您可以使用此事件来覆盖默认行为（例如，通常情况下，使用 Control 键点击标签页会链接它们）。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnTabClick
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[TabClickData](../scripting_objects/tabclickdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool*
</td></tr><tr><td>

**描述：**</td><td>

**TabClickData.tab** 属性标识被点击的标签页。您可以从该事件返回 **True** 来阻止默认操作，或者返回 **False**（默认值）来允许操作继续。
</td></tr></tbody>
</table>