# 高级选择

**选择文件**对话框具有两种模式：*简单*和*高级*。通过**编辑/按模式选择**命令访问它（或按<kbd>Ctrl+S</kbd>）。该对话框会记住上次使用的模式，下次使用时将以该模式打开；可以使用对话框底部的**高级**或**简单**按钮切换模式。

![](/Manual/images/media/13/select_files_-_advanced.png) 

**高级选择**对话框基于 [过滤器控件](/Manual/file_operations/filtered_operations/README.zh.md)。它允许您通过构建复杂过滤条件来选择文件和文件夹，这些过滤条件可针对很多不同属性比较文件和文件夹。上述示例显示了一个过滤条件，它将选择在过去一周内修改的所有以**.jpg**结尾的文件。

参阅 [过滤器操作](/Manual/file_operations/filtered_operations/README.zh.md) 部分，以获取有关如何使用过滤器控件的信息。

##### 选择操作

在对话框顶部，**操作**下拉列表允许您选择要执行的操作：

- **选择匹配项：**将选择与定义过滤条件匹配的所有文件和文件夹。
- **取消选择匹配项：**将取消选择与过滤器匹配的所有文件和文件夹。这允许您执行一个简单的“非”操作 - 首先，可以使用**编辑/全选**命令选择文件夹中的所有文件，然后使用此操作根据过滤条件取消选择文件。
- **隐藏匹配项：**将从显示中移除与过滤条件匹配的所有文件和文件夹

##### 隐藏不匹配项

**隐藏不匹配项**选项可与**选择**和**取消选择**操作结合使用（与**隐藏**操作一起使用没有多大意义）。如果启用此选项，将从显示中完全移除不匹配过滤条件的项。

当使用此功能从显示（隐藏）中移除项时，可以通过两种方式将其取回：

- 最简单的方法是按<kbd>F5</kbd>来刷新文件夹列表（或单击 [地址栏](/Manual/basic_concepts/the_lister/navigation/file_display_border.zh.md) 中的 ![](/Manual/images/media/13/location_toolbar_-_refresh.png) **刷新**按钮）。这将重新读取文件夹并重新显示隐藏的所有文件。
- 还可以通过运行内部命令来重新显示它们。默认菜单或工具栏上没有此命令，因此您需要为其 [创建一个按钮](/Manual/customize/creating_your_own_buttons/README.zh.md) 或将其分配给 [快捷键](/Manual/customize/the_customize_dialog/keys.zh.md)。要用于此目的的命令是`Select NOPATTERN SHOWHIDDEN`。有关命令行参数的更多信息，请参阅内部 **[Select](/Manual/reference/command_reference/internal_commands/select.zh.md)** 命令的文档。

##### 应用选择

构建过滤条件或从下拉过滤器列表中选择一个后，单击**确定**按钮以进行选择。此外，还可以单击**应用**按钮 - 它允许您应用选择而不关闭对话框。如果您的选择过滤条件未按预期执行，那么可以编辑它并再次单击**应用**。