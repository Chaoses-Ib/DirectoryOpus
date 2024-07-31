# OnViewerEvent

**OnViewerEvent** 事件可以由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在 [独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中发生某些事件时收到通知。一种可能的用途是脚本，它在独立查看器处于活动状态时自动显示浮动工具栏，并在窗口变为非活动状态或关闭时再次隐藏它。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnViewerEvent
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ViewerEventData](../scripting_objects/viewereventdata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

**ViewerEventData.viewer** 属性标识发生事件的 **[查看器](../scripting_objects/viewer.zh.md)**。**event** 属性返回一个字符串，标识发生的事件，如果适用，**item** 属性标识涉及的 **项目**。
</td></tr></tbody>
</table>