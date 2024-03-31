# 复制和粘贴

复制粘贴（或剪切粘贴）可能是移动文件的最简单方法。

1. 选择要复制或移动的文件，从**编辑**菜单中选择*复制* (<kbd>Ctrl+C</kbd>) 或*剪切* (<kbd>Ctrl+X</kbd>) 命令
2. 导航至目标文件夹，然后选择*粘贴* (<kbd>Ctrl+V</kbd>)。

使用剪贴板移动文件几乎在所有文件管理器中都是以相同的方式实现的，尽管 Opus 在某些方面扩展了此功能，因此值得了解它。

##### 复制队列

虽然这些功能使用内部**[剪贴板](/Manual/reference/command_reference/internal_commands/clipboard.zh.md)**命令来启动，但是当您将文件粘贴到文件窗口时，实际的文件复制或移动将使用内部**[复制](/Manual/reference/command_reference/internal_commands/copy.zh.md)**命令“以幕后方式”执行。

这意味着诸如[复制队列](copy_queues/README.zh.md)之类功能可用于剪贴板操作，就像在[通过工具栏按钮复制](copying_using_the_toolbar_buttons/README.zh.md)时的操作一样。

您可以使用**[剪贴板](/Manual/reference/command_reference/internal_commands/clipboard.zh.md)**命令的各种参数来控制排队。

##### 粘贴文本和图形数据

如果剪贴板包含文本或图形数据，则可以将其粘贴到文件窗口中，就像它是一个真实的文件一样。Opus 将创建一个新文件并自动将剪贴板数据写入其中。

- 文本数据将被写入名为 *剪贴板文本.txt* 的文件
- 图形数据将被写入名为 *剪贴板图像.jpg* 的文件

您可以在配置中的**[杂项/高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)**页面中使用 **clipboard_image_paste** 选项修改保存图形数据的格式（位图、GIF、PNG 或 JPG）。您还可以使用 **clipboard_image_paste_dpi** 选项使粘贴的图像自动缩放以补偿系统 DPI。

可以使用 **[剪贴板](/Manual/reference/command_reference/internal_commands/clipboard.zh.md)** 命令的各种参数来控制新文件的名称。

##### 增量剪贴板

内部**[剪贴板](/Manual/reference/command_reference/internal_commands/clipboard.zh.md)**命令的 **ADD** 参数允许您将选定的文件添加到已在剪贴板上的任何文件中。例如，您可以从一个文件夹复制一些文件、从另一个文件夹复制一些文件、从第三个文件夹复制一些文件，然后一次性将它们全部粘贴到目标位置。

要使用此功能，您需要创建一个新的工具栏按钮或运行 `Clipboard COPY ADD` 命令的热键（或将其分配给热键 - 例如，<kbd>Ctrl+C</kbd> 默认运行 `Clipboard COPY`，因此您可以将其分配给 <kbd>Ctrl+Shift+C</kbd>）。

请参阅有关 [自定义](/Manual/customize/README.zh.md) 部分，以获取有关创建您自己的按钮和热键的信息。