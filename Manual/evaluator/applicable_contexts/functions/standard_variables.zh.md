求值员在此上下文中可使用许多变量。请注意，有些只适用于 [独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中的工具栏，有些只适用于文件窗口工具栏。

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
dest</td><td>

*路径*</td><td>
当前目标路径。
</td></tr><tr><td>
dest_shell</td><td>

*bool*</td><td>

**True**，如果目标是资源管理器承载的 Shell（虚拟）文件夹，否则为 **false**。
</td></tr><tr><td>
expanded</td><td>

*uint*</td><td>
返回已展开的目录数。
</td></tr><tr><td>
fullscreen</td><td>

*bool*</td><td>

*仅查看器*。**True**，如果查看器为全屏，否则为 **false**。
</td></tr><tr><td>
key_repeat</td><td>

*bool*</td><td>

**True**，如果函数是由重复按键（即按住按键）启动的。
</td></tr><tr><td>
seldirs</td><td>

*uint*</td><td>
返回所选目录的数量。
</td></tr><tr><td>
selfiles</td><td>

*uint*</td><td>
返回所选文件数量。
</td></tr><tr><td>
selimage</td><td>

*bool*</td><td>

*仅查看器*。**True**，如果已选择图像区域，否则为 **false**。
</td></tr><tr><td>
selitems</td><td>

*uint*</td><td>
返回所选项目的总数。
</td></tr><tr><td>
source</td><td>

*路径*</td><td>
当前源路径。
</td></tr><tr><td>
source_shell</td><td>

*bool*</td><td>

**True**，如果源是资源管理器承载的 Shell（虚拟）文件夹，否则为 **false**。
</td></tr><tr><td>
totaldirs</td><td>

*uint*</td><td>
返回目录总数。
</td></tr><tr><td>
totalfiles</td><td>

*uint*</td><td>
返回文件总数。
</td></tr><tr><td>
totalitems</td><td>

*uint*</td><td>
返回项总数。
</td></tr><tr><td>
viewmode</td><td>

*str*</td><td>

返回文件列表中的当前视图模式。值包括 **largeicons**、**smallicons**、**list**、**details**、**power**、**thumbnails** 和 **tiles**。
</td></tr></tbody>
</table>

除了上述变量，还可以使用 [求值函数](/Manual/reference/evaluator/README.zh.md)，如 [ischecked](/Manual/reference/evaluator/ischecked.zh.md) 和 [isenabled](/Manual/reference/evaluator/isenabled.zh.md) 来查询有关文件窗口状态的其它信息。