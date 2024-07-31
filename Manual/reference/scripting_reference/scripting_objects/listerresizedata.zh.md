# ListerResizeData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnListerResize](../scripting_events/onlisterresize.zh.md)** 事件，当文件窗口窗口大小发生变化时，该方法会接收一个 **ListerResizeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
action</td><td>

*string*</td><td>

返回一个 *string* 表示发生的调整大小操作。这将是以下字符串之一：*resize*、*minimize*、*maximize*、*restore*。
</td></tr><tr><td>
width</td><td>
int</td><td>
返回文件窗口新的宽度（以像素为单位）。
</td></tr><tr><td>
height</td><td>
int</td><td>
返回文件窗口新的高度（以像素为单位）。
</td></tr><tr><td>
lister</td><td>

*object:***[文件窗口](lister.zh.md)**</td><td>

返回一个 **[文件窗口](lister.zh.md)** 对象，表示被调整大小的文件窗口。
</td></tr></tbody>
</table>