# OnSourceDestChange

**OnSourceDestChange** 事件可以通过一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以在标签页的源/目标状态发生变化时收到通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnSourceDestChange
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[SourceDestData](../scripting_objects/sourcedestdata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

**SourceDestData.tab** 属性标识标签页，而 **source** 和 **dest** 属性标识新的状态（如果两者都是 **False**，则表示标签页处于 "关闭" 状态 - 这只可能发生在单个文件列表的文件窗口中）。
</td></tr></tbody>
</table>