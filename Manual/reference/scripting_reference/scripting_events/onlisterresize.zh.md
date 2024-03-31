[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)可实现**On文件窗口Resize**事件，以便在调整文件窗口窗口大小时接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
On文件窗口Resize
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[文件窗口ResizeData](../scripting_objects/listerresizedata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*none*
</td></tr><tr><td>

**说明：**</td><td>

**文件窗口ResizeData.lister**属性可识别文件窗口，而**action**属性是一个*字符串*，用于指明已执行调整操作的元素。使用**width**和**height**属性可确定新的窗口大小。
</td></tr></tbody>
</table>