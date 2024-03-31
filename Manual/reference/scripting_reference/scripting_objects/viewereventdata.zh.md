# ViewerEventData

如果脚本实施了 **[OnViewerEvent](../scripting_events/onviewerevent.zh.md)** 事件，当独立 [图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中发生特定事件时，它会接收一个 **ViewerEventData** 对象。

  

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
事件</td><td>

*字符串*</td><td>

返回指示已发生事件的字符串。当前定义的事件为：

- **create**：已创建新的查看器。
- **destroy**：已销毁查看器窗口。
- **load**：已在查看器中加载新图像。**item** 属性可用于查找已加载哪个文件。
- **setfocus**：查看器窗口已收到焦点（已激活）。
- **killfocus**：查看器窗口已失去焦点（已停用）。
- **click**：在图像上单击左键（要求将鼠标按钮设置为在 **配置 / 查看器 / 鼠标按钮** 中触发 *脚本事件*）。
- **dblclk**：在图像上双击左键。
- **mclick**：在图像上单击中键。
</td></tr><tr><td>
项目</td><td>

*对象:***[Item](item.zh.md)**</td><td>

对于 **load** 事件，返回表示新加载的图像的 **[Item](item.zh.md)** 对象。
</td></tr><tr><td>
查看器</td><td>

*对象:***[Viewer](viewer.zh.md)**</td><td>

返回表示事件发生所在的查看器的 **[Viewer](viewer.zh.md)** 对象。
</td></tr><tr><td>
x</td><td>

*int*</td><td>
对于单击事件，返回在查看器窗口中单击发生的 x 坐标。
</td></tr><tr><td>
y</td><td>

*int*</td><td>
对于单击事件，返回在查看器窗口中单击发生的 y 坐标。
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