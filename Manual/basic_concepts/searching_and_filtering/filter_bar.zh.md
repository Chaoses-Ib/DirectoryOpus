# 过滤栏

过滤栏是文件列表底部弹出一个的小文本框，方便快速过滤当前文件列表。默认情况下，按 `*` 键显示过滤栏，但是可以通过 [文件列表/快速键](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.zh.md) 配置页面修改此键。

![](/Manual/images/media/13/filter_bar.png)

按激活键后立即出现过滤栏，您可以继续立即键入以开始过滤列表。

##### 过滤文件列表

在上述屏幕截图中，我们已经过滤 `C:\Windows\System32` 目录以显示所有以 `.msc` 结尾的文件。您可以从状态栏中看到，这导致 4,671 项从显示中隐藏，只留下 21 个 .msc 文件可见。

过滤栏也会显示这些统计数据，稍加详细说明（将隐藏的项目计数分为隐藏文件和隐藏文件夹）。

过滤栏会影响所谓的“快速过滤”。此过滤器应用于通过 [文件夹格式](../folder_options/README.zh.md) 系统设置的过滤器之上，以及 **[全局过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/global_filters.zh.md)** 配置页面上的全局过滤选项之上。它不会覆盖这些过滤器 - 因此，通过这些其他方法隐藏的任何文件都会保持隐藏状态，无论快速过滤器设置为如何。

##### 清除过滤器

要清除过滤器，请按 <kbd>Esc</kbd> 或单击过滤栏上的 X 按钮。

默认情况下，清除过滤器后过滤栏会自动消失，但在 [过滤栏](/Manual/preferences/preferences_categories/filtering_and_sorting/filter_bar.zh.md) 配置页面上有一个选项，可以根据您的选择始终保持打开状态。

##### 指示何时激活快速过滤器

您可以配置文件列表，以便在激活快速过滤器时显示不同的背景颜色，方法是使用配置中 **[Directory Opus Colors](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.zh.md)** 页面的文件列表背景设置。

##### 快速隐藏或显示文件和文件夹

过滤栏上显示文件和文件夹总数的“文件”和“文件夹”图标是可点击的：

- 单击第一个文件/文件夹图标以暂时 **隐藏** 所有文件/文件夹。
- 单击第二个文件/文件夹图标以暂时 **显示** 所有文件/文件夹。

##### 过滤器选项

![](/Manual/images/media/13/filter_bar_menu.png)

选项按钮显示一个菜单，您可以用它来控制过滤器的应用方式：

- **忽略变音符号**: 过滤时忽略重音字符。
- **匹配任意单词**: 激活“任意单词”模式，其工作方式类似于搜索引擎。如果文件包含您输入的任何单词，则该文件将匹配。您可以在单词前加上 `+`，表示它 **必须** 存在，加上 `-` 表示它 **不能** 存在。
- **部分匹配**: 如果启用此选项，您输入的单词只需匹配部分单词即可视为匹配。例如，搜索“quint”将匹配“quintuplet”。
- **使用正则表达式**: 允许您使用 [正则表达式](/Manual/reference/wildcard_reference/regular_expression_syntax.zh.md) 指定搜索模式。如果关闭，该模式将使用 [标准模式匹配语法](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md) 代替。

使用 **保存为默认值** 命令将当前设置保存为默认值。

##### 文件类型过滤

![](/Manual/images/media/13/filter_bar_filetypes.png)

文件类型按钮显示一个菜单，可以根据文件夹的实际内容快速按文件扩展名或文件类型组进行过滤。

菜单的顶部部分指的是文件类型组 - 在此示例中，有一个来自文档组的文件，五个来自图像组，依此类推。

菜单的底部部分列出当前文件夹中出现的扩展名。

从菜单中选择一个组或扩展名以快速按该类型进行过滤（您还可以一次选择多个）。

##### 显示所有

**显示所有** 选项提供了对 *[显示所有](show_everything.zh.md)* 模式的快速切换 - 一种暂时禁用过滤器并显示当前文件夹中所有文件和文件夹的方法。

##### 在平面视图中过滤

当您正在过滤的文件列表处于 [平面视图模式](../flat_view.zh.md) 中时，会出现 **在平面视图中过滤文件夹** 选项。

这允许您控制过滤器是应用于文件夹还是只应用于文件。当在平面视图模式下从显示中过滤出文件夹后，该文件夹中的所有文件（及其子文件夹）也会被过滤掉。这种行为可能或可能不是理想的，而且突然消失大量文件可能会让人困惑，这就是提供此选项（并且默认情况下已关闭）的原因。

可以通过修改配置中 **[杂项/高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面上的 **flatview_folder_filters** 选项来更改此选项的默认状态。

##### 使用即时查找快速过滤

您还可以使用 [即时查找](../the_lister/find-as-you-type_field.zh.md) 字段进行快速过滤（尽管它不具有过滤栏的附加功能）。

为此，您需要在 **[快速键](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.zh.md)** 配置页面上为 **过滤器** 模式分配激活键。有关此内容的更多信息，请参阅即时查找字段的文档。