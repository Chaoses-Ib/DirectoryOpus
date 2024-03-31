[script 加载项](/Manual/scripting/script_add-ins/README.zh.md) 可以实现 **OnStyleSelected** 事件以接收用户选择新的 [文件窗口样式](/Manual/basic_concepts/the_lister/styles.zh.md) 的通知。

<table>
<thead><tr><th>

**方法名：**</th><th>
OnStyleSelected
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[StyleSelectedData](../scripting_objects/styleselecteddata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

**StyleSelectedData.lister** 属性会识别文件窗口，而 **style** 属性会返回新选择的样式的名称。
</td></tr></tbody>
</table>