# 状态栏

每个文件列表底部的状态栏主要用于显示当前文件夹的基本统计信息。与 Opus 中的大多数内容一样，它完全可配置。

### 默认状态栏

![](/Manual/images/media/13/status_bar_1.png) 

这是默认状态栏的示例。显示的信息（从左至右）是：

- 已选总数/文件夹总数
- 已选总数/文件总数
- 不同的所选文件扩展名（以及每个扩展名的数量）
- 隐藏项数量（如果有任何项当前 [被过滤器隐藏](../searching_and_filtering/README.zh.md)）
- 所有所选项的总大小/所有项的总大小（这仅包括所有所选文件夹的大小，前提是已 [计算其大小](/Manual/basic_concepts/folder_sizes.zh.md)）
- [当前格式](../folder_options/identifying_the_current_format.zh.md) 指示器和菜单 (![](/Manual/images/media/13/info.png))
- 当前驱动器上的可用空间
- 当前驱动器上已用空间的百分比（作为条形图）

### 配置状态栏

您可以在配置中的 **[文件列表/状态栏](/Manual/preferences/preferences_categories/file_displays/status_bar.zh.md)** 页面中，配置状态栏中显示的信息。使用各种可用的状态栏代码，可以配置一些相当复杂的状态栏显示，包括所选文件的详细信息、各种条形图等等。

该配置页面上的选项还允许您将状态栏更改为出现在文件窗口的底部，而不是文件列表的底部（因此，例如，您可以在窗口底部放置一个单一的文件列表，该显示仅适用于活动文件列表，而不是每个显示都有自己的显示）。

### 状态栏工具提示

当您将鼠标悬停在一些状态栏元素上时，它们会向您显示带有更多信息的工具提示：

- 隐藏项指示器显示前几个隐藏文件和文件夹的名称，以便您可以快速查看是否有任何感兴趣的内容被隐藏。单击它们以切换 [显示所有](../searching_and_filtering/show_everything.zh.md) 模式的开和关。
- ![](/Manual/images/media/13/info.png) 格式指示器向您显示当前文件夹格式的来源，以帮助您确定如何影响该格式的更改。它还有右键单击上下文菜单，可让您快速更改当前 [文件夹格式](../folder_options/README.zh.md)。