# 嵌入重命名脚本

[重命名脚本](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.zh.md) 可以直接嵌入到按钮或热键中，这使你无需先显示 **[高级重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)** 对话框即可使用脚本重命名文件。

![](/Manual/images/media/rename_embed.png)

此图片描绘了嵌入重命名脚本的一个示例。此类按钮的第一行必须调用 **[重命名](/Manual/reference/command_reference/internal_commands/rename.zh.md)** 命令。此命令实际上会调用重命名功能 - 在调用脚本之前，你可以使用 **重命名** 命令的任何参数对文件重命名执行“预处理”。例如，在调用脚本之前，你可以使用命令 **Rename CASE=allwords** 首先对文件名中的单词大写。在上面的屏幕截图中，**重命名** 命令实际上不会修改文件名本身 - 它会按照原样传递给脚本。

在 **重命名** 命令下方，**@script** [命令修饰符](/Manual/reference/command_reference/command_modifier_reference.zh.md) 用于引入脚本。这会告诉 Opus 该脚本的编写语言，如上所示的屏幕截图中显示的是 **vbscript**，但你可以指定 **jscript** 以使用 JavaScript，并且在你安装了其它语言的情况下，这些语言也会受到支持。

**@script** 行下方的函数定义中的任何文本都会定义脚本本身。有关编写重命名脚本的更多信息，请参阅 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md) 页面。