# 文件窗口

Opus 中的主文件管理器窗口称为“文件窗口”浏览器。

![](/Manual/images/media/13/lister_simple.png)

上面的屏幕截图展示了一个带有默认 Opus 配置的基本文件窗口。它的特点是具有三个顶部工具栏，左边是一个文件夹树，右边是文件列表（上方还有另一个工具栏）。文件夹树突出显示了 C: 驱动器，其内容显示在它的右边。文件列表下方是文件夹标签页栏——当前只有一个标签页处于打开状态（显示 C: 的那个标签页），但你可以随意打开所需数量的文件夹，每个文件夹都在它们自己的标签页中，并且可以快速地在它们之间切换。

在标签页栏下方是状态栏，它对文件夹内容提供可配置的摘要。

虽然文件窗口看起来与 Windows 文件资源管理器类似，但 Opus 故意模仿了它的设计，以方便用户初期熟悉。在其界面之下，Opus 提供了用户可以逐步探索的高级功能。

![](/Manual/images/media/13/lister_complex.png)

此屏幕截图展示了一个复杂得多的文件窗口，你一眼就能看出它与资源管理器的相似之处仅仅是表面的。此屏幕截图中可见的重要用户界面元素有：

- **文件列表：**文件窗口的核心元素，文件列表使你可以查看当前文件夹的内容。你可以选择文件的排列方式（[排序和分组](sorting_and_grouping/README.zh.md)均可配置），并且可以使用 [过滤器](searching_and_filtering/README.zh.md) 隐藏或显示某些文件或文件类型。大多数操作（例如复制/删除文件、创建文件夹、添加到压缩包文件等）都在文件列表中进行。文件窗口最多可以同时显示一个或两个文件列表，并且每个文件列表可以有一个或多个 [标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md)，每个标签页都可以显示不同文件夹的内容。每个文件列表在上方都有一个可配置工具栏，该工具栏显示当前位置并提供基本导航按钮。配置中包含许多影响文件列表的外观和行为的选项（例如，你可以显示网格线，启用整行选择模式等）。有关更多信息，请参阅配置中的 **[文件列表](/Manual/preferences/preferences_categories/file_displays/README.zh.md)** 和 **[文件列表模式](/Manual/preferences/preferences_categories/file_display_modes/README.zh.md)** 类别。
- **默认工具栏：**菜单、操作和收藏工具栏是 Opus 中内置的 [默认工具栏](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/README.zh.md) 集。这些工具栏可以开启或关闭，并且可以编辑，但无法删除或重命名，并且你可以随时轻松地将它们重置为其默认值。上面还显示了默认的图像工具栏，它会在文件列表设置为缩略图模式时显示。当然，你可以使用任意喜欢的按钮组合 [创建自己的工具栏](/Manual/customize/the_customize_dialog/toolbars.zh.md)——许多人在安装 Opus 后立即关闭默认工具栏，并且不再去看它们！
- **搜索字段：**[搜索字段](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md) 使你可以快速使用 Windows 搜索、Opus 内部 [查找工具](searching_and_filtering/find_files/README.zh.md) 或 [Everything](/Manual/additional_functionality/everything_integration.zh.md）（如果你已将其安装）运行搜索。
- **地址栏：**[地址栏](/Manual/basic_concepts/the_lister/navigation/file_display_border.zh.md) 是一个工具栏，它出现在文件列表的顶部。虽然它像其他工具栏一样完全可配置，但它的主要目的是导航。
- **文件夹树：**[文件夹树](/Manual/basic_concepts/the_lister/navigation/folder_tree.zh.md) 显示通往当前所选文件夹的文件夹层级。你可以开启或关闭文件夹树，并且在双栏屏文件窗口中，你可以选择为每个文件列表提供一个独立的文件夹树，或一个它们共用的文件夹树。文件夹树既可以是一种导航工具（单击树中的新文件夹将在文件列表中显示它的内容），又可以作为文件操作的目标（例如，你可以将文件从文件列表中拖动并将其放到树中的另一个文件夹上，以复制或移动它）。
- **查看器窗格：**[查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md) 显示所选文件的内容。Opus 本机支持数十种不同的图像和电影文件格式，并且还具有一个查看器插件系统，使第三方开发者可以编写不支持的文件类型的查看器。此外，Opus 与一个查看器插件一起发行，该插件利用 ActiveX 技术显示 Office 和 PDF 文档等文件。
- **实用工具面板：**这是一个多方面的面板，它提供对几个 [实用工具功能](/Manual/basic_concepts/the_lister/utility_panel.zh.md) 的访问，包括 **[查找](searching_and_filtering/find_files/README.zh.md)**（根据可定义条件查找文件和文件夹）、**[同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md)**（将一个驱动器或文件夹（包括远程 FTP 站点）的内容与另一个驱动器或文件夹的内容同步）和 **[重复的文件](/Manual/additional_functionality/duplicate_file_finder.zh.md)**（搜索任何重复的文件，或搜索特定文件重复项）。此外，实用工具面板用于显示多个日志，包括文件操作日志、FTP 活动日志和脚本输出。
- **元数据窗格：**此窗格使你可以查看和编辑所选文件或文件的 [元数据](/Manual/basic_concepts/the_lister/metadata_pane.zh.md)。它支持许多不同的图像、音乐和文档文件类型。
- **状态栏：**显示当前文件夹的统计信息，包括文件总数、被过滤器隐藏的文件、驱动器上的可用空间等。你可以通过配置 [配置](/Manual/basic_concepts/the_lister/status_bar.zh.md) 显示的信息。
- **过滤栏：**提供对文件名过滤器的快速访问，使你可以 [控制在文件夹中显示或隐藏哪些文件](searching_and_filtering/filter_bar.zh.md)。
- **文件夹标签页：**使用 [文件夹标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md)，你可以同时打开多个文件夹，并且可以轻松地在它们之间切换。