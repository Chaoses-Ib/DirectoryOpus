# 高级重命名

高级重命名对话框允许您执行复杂的批量重命名操作。您可以使用通配符或正则表达式、查找和替换、创建宏、修改大小写、对文件进行编号或重新编号、使用文件元数据重命名，甚至使用该对话框编写复杂的重命名脚本。

要访问高级重命名功能，请选中您想要重命名的文件，然后单击工具栏上的 **重命名** 按钮。

![](/Manual/images/media/13/advanced_rename.png) 

高级重命名对话框有五个不同的部分：

- 左面板是 **[预设列表](/Manual/file_operations/renaming_files/advanced_rename/rename_presets.zh.md)**，您可以在其中加载和管理您的重命名预设。
- 顶部部分控制 **[重命名模式](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/README.zh.md)**（如下所述），并允许您编辑 **旧名称** 和 **新名称** 字符串。除了其他内容之外，它们用于提供通配符模式或查找和替换字符串。
- **[操作](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/README.zh.md)** 部分控制将应用于每个文件名的转换。脚本 **编辑** 按钮用于展开对话框以显示重命名脚本编辑器。
- **[选项](/Manual/file_operations/renaming_files/advanced_rename/rename_options.zh.md)** 部分包含几个控制重命名操作的复选框。
- 最后，**预览** 部分显示已转换文件名的预览。预览列表中列出的每个文件（子文件夹中的文件除外）都有一个复选框，您可以使用该复选框从重命名操作中删除该文件。

### 宏构建器

当 **使用预览列表构建宏** 选项已打开时，预览列表还可用作 [宏构建器](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.zh.md)，这是一个强大的批量编辑功能，可同时对每个文件名进行相同的更改。当该选项关闭时，您可以单独编辑新文件名。编辑单个名称非常适合对宏（或其他批处理操作）可能无法完全正确捕获的进行小更改。一旦文件的名称被直接编辑，它将以红色显示，并且名称将被锁定，直到执行重命名操作（或直到您清除自定义名称）。

宏构建器不能与剪贴板 **粘贴**、**前缀** 和 **追加** 命令（如下所述）同时使用；如果您使用它们，它将被关闭。如果您需要将宏应用于剪贴板中的名称，请粘贴新名称，然后单击应用，然后使用宏构建器。（请注意，宏构建器还可以使用剪贴板、以它自己的方式复制和粘贴。有关详细信息，请参阅 [宏构建器](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.zh.md) 页面。）

### 剪贴板按钮

对话框底部的 **剪贴板** 菜单包含一些命令，允许您将原始文件名的完整列表复制到剪贴板，以便您可以将它们粘贴到另一组文件上，或在外部文本编辑器或电子表格中编辑它们。剪贴板中有文件名时（每行一个），使用 **从剪贴板粘贴新名称** 命令将其粘贴到 *重命名* 对话框中。

该菜单还包含 **前缀**、**追加** 和 **重置** 命令。**前缀** 和 **追加** 允许您将剪贴板内容添加到现有名称的开头或结尾，而不是替换名称。如果剪贴板中有一行，它将被添加到每个名称。如果剪贴板中有多行，则每行将被添加到每个名称，空白行可用于跳过名称。（如果文件数量大于行数，剪贴板内容将循环显示。）最后，**重置** 选项清除通过相同菜单或通过手动键入单个名称设置的任何新名称。

### 应用重命名

配置好重命名参数后，您可以单击 **确定** 来关闭对话框并执行重命名。或者，**应用** 按钮允许将更改应用于选定的文件，同时保持重命名对话框打开。一旦您使用 **应用** 按钮，旁边的 **撤消** 按钮将变为可用，允许您撤消刚刚应用的重命名操作。

更多：

[重命名预设](/Manual/file_operations/renaming_files/advanced_rename/rename_presets.zh.md)  
[重命名模式](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/README.zh.md)  
[重命名操作](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/README.zh.md)  
[重命名选项](/Manual/file_operations/renaming_files/advanced_rename/rename_options.zh.md)  
[使用元数据重命名](/Manual/file_operations/renaming_files/advanced_rename/renaming_with_metadata.zh.md)  
[重命名脚本](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.zh.md)