**OnTabClick** 事件可由 [脚本当加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现以接收在按住定性符的情况下单击标签页时的通知。您可以使用它来覆盖默认行为（例如，通过按住 Ctrl 键单击标签页通常会将它们链接起来）。

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

**说明：**</td><td>

**TabClickData.tab** 属性识别已单击的标签页。您可以从该事件返回 **True** 来阻止默认操作，或返回 **False**（这是默认设置）来允许该操作继续进行。
</td></tr></tbody>
</table>