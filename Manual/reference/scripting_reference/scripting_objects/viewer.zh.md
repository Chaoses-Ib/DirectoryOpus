# Viewer

**Viewer** 对象表示一个独立的 [图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md)。**Viewer** 对象集合由 **[Viewers](viewers.zh.md)** 对象返回，而该对象可以通过 **[DOpus](dopus.zh.md).viewers** 属性获得。对于从查看器内启动的函数（例如，从其工具栏启动），当前 **Viewer** 对象由 **[ClickData](clickdata.zh.md).[func](func.zh.md).viewer** 属性提供。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
bottom</td><td>

*int*</td><td>
返回查看器窗口的底部坐标。
</td></tr><tr><td>
current</td><td>

*object:***[Item](item.zh.md)**</td><td>

返回一个 **[Item](item.zh.md)** 对象，该对象表示当前显示的图像。
</td></tr><tr><td>
desktop</td><td>

*string*</td><td>
返回该查看器所在的虚拟桌面的 ID。
</td></tr><tr><td>
files</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，该对象表示查看器列表中的图像。
</td></tr><tr><td>
foreground</td><td>

*bool*</td><td>

如果查看器当前是系统中的前台（活动）窗口，则返回 **True**。
</td></tr><tr><td>
imagesize</td><td>

*object:***[Rect](rect.zh.md)**</td><td>

返回一个 **[Rect](rect.zh.md)** 对象，该对象表示当前显示的图像的大小（本机大小，忽略任何缩放）。
</td></tr><tr><td>
index</td><td>

*int*</td><td>
返回当前查看的图像在查看器文件列表中的索引。
</td></tr><tr><td>
lastactive</td><td>

*bool*</td><td>

如果查看器是最近激活的查看器，则返回 **True**。
</td></tr><tr><td>
left</td><td>

*int*</td><td>
返回查看器窗口的左坐标。
</td></tr><tr><td>
parentlister</td><td>

*object:***[文件窗口](lister.zh.md)**</td><td>

返回一个 **[文件窗口](lister.zh.md)** 对象，该对象表示启动查看器的文件窗口（如果存在并且仍在运行）或者，如果启用了查看器重用，则最后将文件发送到查看器。

在不再有 **parenttab** 对象的情况下，可能存在一个 **parentlister** 对象。例如，如果在查看器打开后关闭了标签，或者如果查看器收到了从文件夹标签以外的某些内容打开图像的请求，那么将不再有 **parenttab**，但 **parentlister** 属性将持续存在。

此属性是创建 **Viewer** 脚本对象时的快照；它不会对脚本操作做出反应而更改。
</td></tr><tr><td>
parentlisterlinked</td><td>

*bool*</td><td>

如果查看器与父文件窗口处于 *文件窗口链接* 模式，则返回 **True**。这意味着查看器就像一个分离的预览窗格，在文件窗口中选择每个文件时都会显示该文件。

此属性是创建 **Viewer** 脚本对象时的快照；它不会对脚本操作做出反应而更改。
</td></tr><tr><td>
parenttab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，该对象表示启动查看器的标签（如果存在并且仍在运行）或者，如果启用了查看器重用，则最后将文件发送到查看器。

如果你想要 **[文件窗口](lister.zh.md)** 而不是标签，应该使用上述 **parentlister** 属性，因为它更持久。此外，不要假定 **parenttab** 仍然是文件窗口中的活动标签；如果你需要它，请查询文件窗口对象。

此属性是创建 **Viewer** 脚本对象时的快照；它不会对脚本操作做出反应而更改。
</td></tr><tr><td>
right</td><td>

*int*</td><td>
返回查看器窗口的右坐标。
</td></tr><tr><td>
selection</td><td>

*object:***[Rect](rect.zh.md)**</td><td>

返回一个 **[Rect](rect.zh.md)** 对象，该对象表示图像的当前选择区域（如果存在）。如果没有选择，矩形将为空。
</td></tr><tr><td>
title</td><td>

*string*</td><td>

返回或设置查看器窗口的标题栏字符串。

你可以在标题字符串中使用多个特殊“标记”来插入各种信息：

|            |                                                                                                      |
|------------|------------------------------------------------------------------------------------------------------|
| **%P**     | 当前查看图像的完整路径                                                              |
| **%N**     | 当前显示图像的名称                                                                  |
| **%R**     | 当前图像的驱动器根目录                                                                      |
| **%E**     | 如果图像的元数据已修改但未保存，则显示 \*                                                  |
| **%I**     | 图像列表中当前图像的索引（数字）                                                 |
| **%O**     | 列表中的图像总数                                                                   |
| **%W**     | 当前图像的宽度                                                                           |
| **%H**     | 当前图像的高度                                                                          |
| **%D**     | 当前图像的深度（每像素位数）                                                          |
| **%M**     | 当前图像的尺寸                                                                           |
| **%S**     | 磁盘上的文件大小                                                                                    |
| **%F**     | 文件夹名称                                                                                          |
| **%C**     | 如果当前图像已[标记](/Manual/additional_functionality/viewing_images/image_marking.zh.md)，则为集合名称 |
| **%L**     | 分配给当前图像的任何 [标签](/Manual/file_operations/labels.zh.md)                                  |
| **%T**     | 原始标题（适用于在标题前或标题后添加前缀或后缀）                            |
| **%%%%%%** | 插入文字 %                                                                         |
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
说明
</th></tr></thead><tbody><tr><td>
AddFile</td><td>

\<string:filepath\>  
\<int:index\></td><td>

*none*</td><td>

将指定的文件添加到查看器的当前文件列表中。你可以传递一个字符串或一个 **[Path](path.zh.md)** 对象来表示要添加到列表中的文件。默认情况下，文件将被添加到列表末尾，除非你指定一个从 0 开始的索引作为第二个参数。
</td></tr><tr><td>
Command</td><td>

\<string:command\> 或  
\<**[Command](command.zh.md)**:command\></td><td>

*none*</td><td>

在此查看器窗口的上下文中运行命令。你可以传递字符串或 **[Command](command.zh.md)** 对象。
如果您传递的参数是一个字符串，则它只能是 **[Show](../../command_reference/internal_commands/show.zh.md) VIEWERCMD** 命令记录的查看器命令参数。例如，** 命令("next")** 将在这个查看器的上下文中运行 **Show VIEWERCMD=next ** 命令。

如果您传递一个 **[Command](command.zh.md)** 对象，则可以使用所有命令（内部或外部）
</td></tr><tr><td>
IsOnCurrentDesktop</td><td>

*无*</td><td>

*bool*</td><td>

如果查看器在当前虚拟桌面上，则返回 **True**。
</td></tr><tr><td>
MoveToDesktop</td><td>

<string:desktop></td><td>

*bool*</td><td>

将查看器窗口移动到指定的虚拟桌面。如果成功，则返回 **True**。
</td></tr><tr><td>
RemoveFile</td><td>

<int:index> 或  
<string:filepath></td><td>

*无*</td><td>

从查看器当前的文件列表中，移除指定的文件。您可以传递要移除的文件的从 0 开始的索引，或传递文件路径（作为字符串或 **[Path](path.zh.md)** 对象）。
</td></tr><tr><td>
SetTaskbarGroup</td><td>

<string:group></td><td>

*bool*</td><td>

用于更改查看器窗口在任务栏上与其他 Opus 窗口分组的方式。指定一个组名称，以将窗口移动到一个备用组中，或省略组参数以重置回默认组。如果已将一个或多个窗口移动到同一组中，则它们将被分组在一起，独立于其他默认组。

此操作仅在启用任务栏分组时才起效。组名称被限制为 103 个字符，如果超过此限制，将被截断。组名称中的空格和句点将自动转换为下划线。

成功时，返回 true。
</td></tr></tbody>
</table>