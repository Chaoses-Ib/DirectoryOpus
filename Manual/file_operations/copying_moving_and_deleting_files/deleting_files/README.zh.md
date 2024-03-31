# 删除文件

要删除文件或文件夹，您可以：

- 选择文件并按下键盘上的 <kbd>Del</kbd> 键
- 右键单击文件，然后从上下文菜单中选择 **Delete** 命令
- 选择文件，然后单击工具栏上的 **Delete** 按钮。

默认情况下，Opus 会将 Opus 删除的文件存放到回收站（如果可能）。存放到回收站中的文件可以正常恢复（通过 [撤销](../tracking_and_undoing_file_operations.zh.md) 命令），直到清空回收站。回收站不支持网络驱动器或可移动媒体，而且从压缩包内部或 FTP 站点中删除的文件也无法恢复。

如果您在按下 <kbd>Del</kbd> 或单击工具栏按钮时按住 <kbd>Shift</kbd> 键，则您可以绕过回收站并永久删除文件。

附加到默认工具栏上 **Delete** 按钮的下降菜单包含多个与删除文件相关的命令和选项：

##### Delete 菜单

![](/Manual/images/media/13/delete_dropdown.png)

- **Delete**：删除所选文件或文件夹，默认情况下存放到回收站
- **Secure Wipe**：[安全删除](/Manual/file_operations/copying_moving_and_deleting_files/deleting_files/secure_delete.zh.md) 选定的文件或文件夹，以使它们无法恢复
- **Remove From Collection**：在查看 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 的内容时，此功能使您能够从集合中移除某个项目，而无需实际删除它。如果您在文件集合中使用常规 Delete 命令，则会删除真实文件。
- **Go to Recycle Bin**：带您到回收站（废纸篓）文件夹。
- **Empty Recycle Bin**：清空回收站。
- **Secure Empty Recycle Bin**：安全清空回收站（在清空回收站之前先覆盖其中的文件）。
- **Enable Recycle Bin**：启用和禁用回收站的默认使用。
- **Enable Recycle Confirmation**：启用或禁用将文件删除到回收站时显示的确认信息。
- **Enable Delete Filter**：激活 Delete 功能的 [递归过滤器](../filtered_operations/README.zh.md)，该过滤器让您可以选择性地删除选定子文件夹的内容。
- **Delete Settings**：打开 [Deleting Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md) 配置页面。

##### Delete 选项

**[文件操作 / 删除文件](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md)** 配置页面包含多个选项，这些选项允许您在 Opus 中配置 Delete 功能。您可以选择是否让 Opus 在删除之前询问您确认（如果您愿意，它甚至可以在每个文件之前询问您），并且可以配置回收站的使用。您还可以选择是否可以在没有特殊确认提示的情况下删除标记为只读的文件。

更多信息：[安全删除](/Manual/file_operations/copying_moving_and_deleting_files/deleting_files/secure_delete.zh.md)