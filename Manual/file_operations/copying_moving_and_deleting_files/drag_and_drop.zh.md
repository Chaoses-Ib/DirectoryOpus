# 拖放

拖放是 Windows 中移动文件的一种常见方式。在 Opus 中，拖放由 **[文件类型](/Manual/file_types/README.zh.md)** 系统控制。

##### 默认拖放行为

默认行为与在资源管理器中相同：

- 将文件拖放到同一驱动器上的另一个文件夹将会移动该文件
- 将文件拖放到其他驱动器上的文件夹将会复制该文件
- 在放置时按住 <kbd>Shift</kbd> 键会强制移动文件
- 在放置时按住 <kbd>Ctrl</kbd> 键会强制复制文件
- 在放置时按住 <kbd>Alt</kbd> 键会创建文件的快捷方式
- 通过右键拖放会显示一个菜单，让你可以选择 *复制*、*移动* 或 *创建快捷方式* 作为操作。

在内部，这些操作是由 **所有文件和文件夹** 文件类型的 **事件** 标签页上的项定义的。尽管在资源管理器中这些操作是固定的，但在 Opus 中它们是可配置的。

##### 配置拖放操作

![](/Manual/images/media/13/default_draganddrop.png)

此屏幕截图显示了 **所有文件和文件夹** 文件类型的 [文件类型编辑器](/Manual/file_types/filetype_editor/README.zh.md)。所有事件都定义为内部 **[复制](/Manual/reference/command_reference/internal_commands/copy.zh.md)** 命令的某些变体。

- 拖放：`Copy MOVEWHENSAME` 在同一驱动器上移动文件，否则则复制文件。
- 拖放+<kbd>Alt</kbd>：`Copy MAKESHORTCUT` 创建到文件的快捷方式。
- 拖放+<kbd>Ctrl</kbd>：`Copy RENAMEWHENSAME` 如果名称与现有名称冲突，将自动重命名复制的文件。
- 拖放+<kbd>Shift</kbd>：`Copy MOVE` 始终移动文件。

此处未显示，**放置菜单** 标签页还定义了用鼠标右键拖动时显示的菜单的内容。这也可配置。

编辑这些函数会修改 Opus 中的拖放行为。例如，如果你希望拖放始终复制（而不是在同一驱动器上移动），则可以将命令定义编辑为 `Copy RENAMEWHENSAME`（与 *拖放+*<kbd>Ctrl</kbd> 事件相同）。

##### 针对特定文件类型覆盖行为

**所有文件和文件夹** 文件类型是一种特殊文件类型，根据定义匹配所有内容——包括文件和文件夹。你可以使用文件类型系统来定义特定文件类型的覆盖事件。例如，你可以将 ZIP 文件的拖放配置为在按住 <kbd>Shift</kbd> 键放置时解压缩压缩包的内容。

有关更多信息，请参阅 **[文件类型](/Manual/file_types/README.zh.md)** 系统文档。