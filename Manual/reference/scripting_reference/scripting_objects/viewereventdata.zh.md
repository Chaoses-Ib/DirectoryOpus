# ViewerEventData

如果脚本实现 **[OnViewerEvent](../scripting_events/onviewerevent.zh.md)** 事件，则每当独立 [图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中发生某些事件时，它都会收到一个 **ViewerEventData** 对象。

  

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
event</td><td>

*string*</td><td>

返回一个字符串，指示发生的事件。目前定义的事件有：

- **create**: 创建了一个新的查看器。
- **destroy**: 查看器窗口已销毁。
- **load**: 在查看器中加载了新图像。**item** 属性可用于找出加载了哪个文件。
- **setfocus**: 查看器窗口已获得焦点（变为活动状态）。
- **killfocus**: 查看器窗口已失去焦点（变为非活动状态）。
- **click**: 在图像上单击了左键（需要将鼠标按钮设置为在 **配置 / 查看器 / 鼠标按钮** 中触发 *脚本事件*）。
- **dblclk**: 在图像上双击了左键。
- **mclick**: 在图像上单击了中间键。
</td></tr><tr><td>
item</td><td>

*object:***[Item](item.zh.md)**</td><td>

对于 **load** 事件，返回一个 **[Item](item.zh.md)** 对象，表示新加载的图像。
</td></tr><tr><td>
viewer</td><td>

*object:***[Viewer](viewer.zh.md)**</td><td>

返回一个 **[Viewer](viewer.zh.md)** 对象，表示发生事件的查看器。
</td></tr><tr><td>
x</td><td>

*int*</td><td>
对于单击事件，返回单击事件发生时查看器窗口内的 x 坐标。
</td></tr><tr><td>
y</td><td>

*int*</td><td>
对于单击事件，返回单击事件发生时查看器窗口内的 y 坐标。
</td></tr><tr><td>
w</td><td>

*int*</td><td>
对于单击事件，返回查看器窗口的宽度。
</td></tr><tr><td>
h</td><td>

*int*</td><td>
对于单击事件，返回查看器窗口的高度。
</td></tr></tbody>
</table>