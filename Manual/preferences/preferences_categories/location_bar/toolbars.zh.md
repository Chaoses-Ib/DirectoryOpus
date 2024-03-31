# 工具栏

这些选项会影响 [地址栏](/Manual/basic_concepts/the_lister/navigation/file_display_border.zh.md) - 在文件窗口中文件列表上方显示的工具栏或标题栏。

此页面上的主要选择是，将地址栏显示为工具栏，还是显示为静态标题（模拟 Opus 11 之前的版本）。

##### 显示为工具栏

此选项默认打开，可以在每个文件列表的顶部使用一个或多个工具栏。为此使用的默认工具栏是 [文件列表](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/file_display_toolbar.zh.md)，但您可以通过列表选择您自己的工具栏。

左侧的列表显示您的可用工具栏，右侧的列表显示已选择用于地址栏的工具栏。

##### 显示为静态标题

此选项会禁用文件列表工具栏，而是显示一个静态标题，该标题显示当前文件夹路径和几个小的导航和控制按钮。虽然显示的路径具有一些功能（例如，您可以单击各个片段，类似于 [面包屑位置字段](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.zh.md)），但它远不如工具栏灵活。

- **允许停靠文件窗口**：它允许您将一个单一显示的文件窗口拖到另一个的标题栏上方，并将它们停靠在一起（您拖动的文件窗口将关闭，您将其停靠的文件窗口将更改为双栏模式，并且它显示的文件夹标签页将在新显示中打开）。您还可以通过从 [地址栏](/Manual/basic_concepts/the_lister/navigation/file_display_border.zh.md) 中拖动将双栏文件窗口分成两个单显示。
- **标题边框中的可点击路径组件**：您可以单击边框中的各个路径段，浏览到当前文件夹的父位置。
- **标题栏中的“向上”按钮执行“向上 + 返回”**：当打开时，单击 **向上** 按钮的行为就像已使用 `Go UP BACK` 命令一样（例如，如果父文件夹在路径历史记录中，Opus 将“返回”到它，保留文件选择和计算的文件夹大小）。
- **即使在单一显示模式下也显示标题**：必须以双模式显示地址栏（以指示 [哪边是源，哪边是目标](/Manual/basic_concepts/source_and_destination.zh.md)），但您可以在单一显示模式下将其关闭，以节省空间。