# 过滤操作

通常，当命令对某个文件夹进行更改时，该文件夹的全部内容也会进行处理。例如，如果你选择一个文件夹并单击 **复制文件** 按钮，则该文件夹（包括全部内容）将被复制。

文件过滤器使你可以控制文件夹内的哪些项目被处理。你可能只想复制子文件夹中的图像文件；或你想删除所有 **.tmp** 文件，但让所有其它文件保持不变。你可以使用文件过滤器来实现此目的。

### 支持递归过滤器的功能

有一些功能支持使用文件过滤器：

- **复制文件：**复制或移动文件时，可以通过选择 **复制文件** 按钮上的下拉菜单中的 **复制过滤器** 选项启用过滤。此复制过滤器是文件窗口本地的，它在该文件窗口中保持启用，直至关闭或该文件窗口被关闭。
- **删除：**删除文件时，可以通过选择 **删除** 按钮上的下拉菜单中的 **删除过滤器** 选项启用过滤。此删除过滤器是文件窗口本地的，它在该文件窗口中保持启用，直至关闭或该文件窗口被关闭。
- **查找文件：** **[查找文件](/manual/basic_concepts/searching_and_filtering/find_files/README.zh.md)** 工具的 [高级模式](/manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md) 使用过滤器来定义搜索参数。
- **文件选择：** **[高级选择](/manual/basic_concepts/selecting_files/advanced_selection.zh.md)** 对话框允许你使用过滤器在当前文件列表中选择、取消选择和隐藏文件。
- **同步：** **[同步](copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md)** 工具中的 **过滤器** 选项允许你使用过滤器来控制同步如何处理子文件夹。
- **重复文件查找：** **过滤器** 选项允许你在 [搜索重复文件](/manual/additional_functionality/duplicate_file_finder.zh.md) 时控制比较哪些文件。
- **属性：** **属性** 按钮的下拉菜单中的 **[属性](changing_attributes.zh.md)** 命令允许你在将属性应用于子文件夹内容时使用过滤器。
- **打印文件夹：** **工具** 菜单中的 **[打印/导出文件夹列表](/manual/additional_functionality/print_folder.zh.md)** 命令允许你使用过滤器来控制哪些文件打印到列表中。
- **标记：** 你可以使用 **[标记](labels.zh.md)** 系统来自动为与复杂过滤器匹配的文件和文件夹着色或高亮显示。

### 定义过滤器

在函数中使用过滤器时，有两种方法可以定义它：

- 你可以在实际使用它时定义过滤器。允许你通过用户界面指定过滤器的函数还可以让你编辑它。你可以从预先保存的一个开始，或从头开始构建一个。
- 你可以从下拉列表中选择预先配置的过滤器。可以使用 [过滤器](/manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md) 选项页面对过滤器进行预先配置并存储起来。这使你可以建立一个有用的过滤器存储库，以便在整个程序中轻松访问。

一些 [内部命令](/manual/reference/command_reference/internal_commands/README.zh.md) 允许你在命令行上指定过滤器：

- 过滤器名称，例如：`复制过滤器 <filtername>`。在这种情况下，必须预先配置并存储过滤器。
- 使用过滤器定义本身以 [文本格式](/manual/file_operations/filtered_operations/textual_filters.zh.md)；例如：`复制过滤器定义名称匹配 *.jpg`。

### 过滤器控制

![](/Manual/images/media/13/file_filter.png) 

这是一个使用过滤器控件的对话框示例。当你运行 **复制文件** 函数并且 **复制过滤器** 选项已打开时，会显示此特定对话框。Opus 在复制过程开始时显示过滤器对话框，你可以在其中定义新的过滤器，或从 **过滤器** 下拉列表中选择预先配置的过滤器。

此过滤器控件顶部工具栏中的 **清除** 按钮允许你快速清除现有的过滤器。如果你在单击它时按住 <kbd>Shift</kbd> 键，则将过滤器重置为简单的模板过滤器，并添加一些常见条件。

在上方的屏幕截图中，在工具栏下方的区域是定义过滤器本身的区域，在过滤器控件下方是特定于 **复制** 或 **删除** 过滤器的控件：

- **此函数后禁用过滤器：** 这允许你自动在当前函数完成时禁用过滤器（复制或删除）（否则，该过滤器将一直有效，直至你手动关闭它）。
- **选择：** 此按钮采用当前过滤器定义，并使用它选择当前文件列表中所有匹配的文件和文件夹。这允许你在运行命令之前查看过滤器在当前文件夹上的结果。
- **跳过过滤器：** 跳过对当前操作使用过滤器，但过滤器仍保持启用状态（除非你也启用了 **此函数后禁用过滤器** 选项）。

同样，这些选项仅适用于复制和删除过滤器。在你其它函数中使用过滤器时（例如， **[查找](/manual/basic_concepts/searching_and_filtering/find_files/README.zh.md)** 或 **[同步](copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md)** 工具），这些选项将不会显示。

*过滤器：* 标签右侧的下拉菜单允许你访问功能，以便加载、保存和管理预先配置的过滤器。你还可以通过选项中的 [过滤器](/manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md) 页面执行此操作。

![](/Manual/images/media/13/filter_drop-down.png)

更多：

[定义过滤器](/manual/file_operations/filtered_operations/defining_a_filter.zh.md)  
[添加、删除和编辑子句](/manual/file_operations/filtered_operations/adding_removing_and_editing_clauses.zh.md)  
[过滤器子句类型](/manual/file_operations/filtered_operations/filter_clause_types.zh.md)