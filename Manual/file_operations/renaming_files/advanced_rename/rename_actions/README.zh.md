# 重命名操作

重命名对话框的 **操作** 部分可以让你除了主要的模式化操作（由对话框的 **[模式](rename_modes/README.zh.md)** 部分控制）之外，还能启用其它重命名操作。

![](/Manual/images/media/13/rename_actions.png)

在此处启用的选项会影响你的重命名操作，无论你选择的哪种主要模式。变换会在模式化操作后应用（你可以认为重命名过程是从重命名对话框的顶部到底部执行的）。

- **大小写转换**：更改文件名的字母大小写 - 选项（内置示例）：*全部小写*, *全部大写*, *单词首字母大写*, *第一个单词首字母大写*, *小写扩展名*, *大写扩展名*。
- **宏**：命令可以添加、删除、复制和粘贴每个文件名特定位置的字符。编写宏的宏语言有点复杂，这就是为什么有一个内置的 [宏记录器](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.zh.md) 来执行困难的工作。当你记录宏时，命令会写入这个字段，并且可以保存到预设中以供重复使用。
- **从**：向现有文件添加增量数字（或用数字完全替换文件名）。有关更多详细信息，请参阅 [给文件编号](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/numbering_files.zh.md)。
- **编辑脚本**：指示是否定义了重命名脚本，并且允许你打开内置的 [重命名脚本](rename_scripts.zh.md) 编辑器，它允许你用 VBScript、JScript 等编写脚本以完全控制重命名过程。

更多信息：  
[给文件加编号](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/numbering_files.zh.md)  
[重命名宏](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.zh.md)