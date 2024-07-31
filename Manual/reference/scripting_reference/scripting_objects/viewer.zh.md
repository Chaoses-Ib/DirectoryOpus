# Viewer

**Viewer** 对象代表一个独立的 [图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md)。**[Viewer](viewers.zh.md)** 对象返回一个 **Viewer** 对象集合，该对象可以通过 **[DOpus](dopus.zh.md).viewers** 属性获取。对于从查看器内部启动的函数（例如，从其工具栏启动的函数），当前 **Viewer** 对象由 **[ClickData](clickdata.zh.md).[func](func.zh.md).viewer** 属性提供。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
bottom</td><td>

*int*</td><td>
返回查看器窗口的底部坐标。
</td></tr><tr><td>
current</td><td>

*object:***[Item](item.zh.md)**</td><td>

返回一个 **[Item](item.zh.md)** 对象，表示当前显示的图像。
</td></tr><tr><td>
desktop</td><td>

*string*</td><td>
返回此查看器所在的虚拟桌面的 ID。
</td></tr><tr><td>
files</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示查看器列表中的图像。
</td></tr><tr><td>
foreground</td><td>

*bool*</td><td>

如果查看器当前是系统中的前台（活动）窗口，则返回 **True**。
</td></tr><tr><td>
imagesize</td><td>

*object:***[Rect](rect.zh.md)**</td><td>

返回一个 **[Rect](rect.zh.md)** 对象，表示当前显示的图像的大小（本机大小，忽略任何缩放）。
</td></tr><tr><td>
index</td><td>

*int*</td><td>
返回查看器文件列表中当前查看的图像的索引。
</td></tr><tr><td>
lastactive</td><td>

*bool*</td><td>

如果查看器是最新的活动查看器，则返回 **True**。
</td></tr><tr><td>
left</td><td>

*int*</td><td>
返回查看器窗口的左侧坐标。
</td></tr><tr><td>
parentlister</td><td>

*object:***[文件窗口](lister.zh.md)**</td><td>

返回一个 **[文件窗口](lister.zh.md)** 对象，表示启动查看器的文件窗口（如果有，并且它仍然存在），或者如果启用了查看器重复使用，则表示最后将文件发送到查看器的文件窗口。

在没有 **parenttab** 对象的情况下，可能存在 **parentlister** 对象。例如，如果在查看器打开后关闭了标签页，或者查看器收到来自文件夹标签页以外的某个对象的打开图像的请求，那么将不再存在 **parenttab**，但 **parentlister** 属性将保留。

此属性是创建 **Viewer** 脚本对象时的快照；它不会对脚本操作做出反应而更改。
</td></tr><tr><td>
parentlisterlinked</td><td>

*bool*</td><td>

如果查看器处于与父文件窗口 *链接的文件窗口* 模式，则返回 **True**。这意味着查看器充当一个分离的预览窗格，在文件窗口中选择每个文件时显示该文件。

此属性是创建 **Viewer** 脚本对象时的快照；它不会对脚本操作做出反应而更改。
</td></tr><tr><td>
parenttab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示启动查看器的标签页（如果有，并且它仍然存在），或者如果启用了查看器重复使用，则表示最后将文件发送到查看器的标签页。

如果需要 **[文件窗口](lister.zh.md)** 而不是标签页，则应使用 **parentlister** 属性（如上所述），因为它更加持久。此外，不要假设 **parenttab** 仍然是文件窗口中的活动标签页；如果您需要该标签页，请查询文件窗口对象。

此属性是创建 **Viewer** 脚本对象时的快照；它不会对脚本操作做出反应而更改。
</td></tr><tr><td>
right</td><td>

*int*</td><td>
返回查看器窗口的右侧坐标。
</td></tr><tr><td>
selection</td><td>

*object:***[Rect](rect.zh.md)**</td><td>

返回一个 **[Rect](rect.zh.md)** 对象，表示图像的当前选择区域（如果有）。如果没有选择，则矩形将为空。
</td></tr><tr><td>
title</td><td>

*string*</td><td>

返回或设置查看器窗口的标题栏字符串。

您可以在标题字符串中使用几个特殊的“标记”来插入各种信息：

|            |                                                                                                      |
|------------|------------------------------------------------------------------------------------------------------|
| **%P**     | 当前查看图像的完整路径                                                                           |
| **%N**     | 当前显示图像的名称                                                                               |
| **%R**     | 当前图像的驱动器根目录                                                                           |
| **%E**     | 如果图像的元数据已修改但未保存，则显示 \*                                                      |
| **%I**     | 当前图像在图像列表中的索引（编号）                                                               |
| **%O**     | 列表中图像的总数                                                                                  |
| **%W**     | 当前图像的宽度                                                                                   |
| **%H**     | 当前图像的高度                                                                                   |
| **%D**     | 当前图像的深度（每像素位数）                                                                    |
| **%M**     | 当前图像的尺寸                                                                                   |
| **%S**     | 磁盘上的文件大小                                                                                   |
| **%F**     | 文件夹名称                                                                                       |
| **%C**     | 如果当前图像已 [标记](/Manual/additional_functionality/viewing_images/image_marking.zh.md)，则为集合名称 |
| **%L**     | 分配给当前图像的任何 [标签](/Manual/file_operations/labels.zh.md)                                        |
| **%T**     | 原始标题（用于简单地在标题中添加前缀或后缀）                                                  |
| **%%%%%%** | 插入一个字面上的 % 字符                                                                         |
</td></tr><tr><td>
top</td><td>

*int*</td><td>
返回查看器窗口的顶部坐标。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddFile</td><td>

\<string:filepath\>  
\<int:index\></td><td>

*none*</td><td>

将指定文件添加到查看器的当前文件列表中。您可以传递字符串或 **[Path](path.zh.md)** 对象来指示要添加到列表中的文件。默认情况下，文件将添加到列表的末尾，除非您将基于 0 的索引指定为第二个参数。
</td></tr><tr><td>
Command</td><td>

\<string:command\> 或  
\<**[Command](command.zh.md)**:command\></td><td>

*none*</td><td>

在该查看器窗口的上下文中运行命令。您可以传递字符串或 **[Command](command.zh.md)** 对象。

如果您传递的论点是字符串，那么它只能是查看器命令论点，如 **[Show](../../command_reference/internal_commands/show.zh.md) VIEWERCMD** 命令中所述。例如，**Command("next")** 将在该查看器的上下文中运行 **Show VIEWERCMD=next** 命令。

如果您传递一个 **[Command](command.zh.md)** 对象，那么可以使用所有命令（内部或外部）。
</td></tr><tr><td>
IsOnCurrentDesktop</td><td>

*none*</td><td>

*bool*</td><td>

如果查看器位于当前虚拟桌面，则返回 **True**。
</td></tr><tr><td>
MoveToDesktop</td><td>

\<string:desktop\></td><td>

*bool*</td><td>

将查看器窗口移动到指定的虚拟桌面。如果成功，则返回 **True**。
</td></tr><tr><td>
RemoveFile</td><td>

\<int:index\> 或  
\<string:filepath\></td><td>

*none*</td><td>

从查看器的当前文件列表中删除指定文件。您可以传递要删除的文件的基于 0 的索引，或者文件路径（作为字符串或 **[Path](path.zh.md)** 对象）。
</td></tr><tr><td>
SetTaskbarGroup</td><td>

\<string:group\></td><td>

*bool*</td><td>

用于更改查看器窗口在任务栏上与其它 Opus 窗口的组合方式。指定一个组名以将窗口移动到备用组，或者省略组参数以重置回默认组。如果将一个或多个窗口移动到同一个组，它们将组合在一起，与默认组分开。

这仅在启用任务栏分组时有效。组名限制为 103 个字符，如果更长，将被截断。组名中的空格和点会自动转换为下划线。

成功时返回 true。
</td></tr></tbody>
</table>