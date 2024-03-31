# 替换菜单

**“替换菜单”** 标签页允许您将命令添加到在您右键单击 **[确认文件替换](/Manual/file_operations/copying_moving_and_deleting_files/the_confirm_file_replace_dialog.zh.md)** 对话框中的文件图标时显示的上下文菜单（当您复制一个已有文件的文件时显示）。使用此功能，您可以定义命令，例如，让您使用外部比较工具比较旧文件和新文件。

[Image of the Replace Menu tab in the Folder Options dialog box with the Replace Menu item selected]

例如，一个使用 Beyond Compare 比较两个文件的命令可能看起来像这样：

“C:\Program Files (x86)\Beyond Compare 4\BCompare.exe” {filepath\$} {filepathdest\$}

然后，在替换对话框中，单击任一文件缩略图都会在此上下文菜单的顶部显示此命令。

[Image of the Replace dialog box showing the context menu with the Beyond Compare command at the top]