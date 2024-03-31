**OnViewerEvent** 事件可以通过[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)来实现，用于在 [独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中发生特定事件时收到通知。一种可能的用途是脚本，该脚本在独立查看器处于活动状态时自动显示浮动工具栏，并在窗口处于非活动状态或关闭时再次将其隐藏。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnViewerEvent
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ViewerEventData](../scripting_objects/viewereventdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

**查看器事件数据对象**属性标识事件发生在哪种**[查看器](../scripting_objects/viewer.zh.md)**中。**事件**属性返回一个字符串，标识发生的事件，如果适用，**项目**属性则标识所涉及的**项目**。
</td></tr></tbody>
</table>