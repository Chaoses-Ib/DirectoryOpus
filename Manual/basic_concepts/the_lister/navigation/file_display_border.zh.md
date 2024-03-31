# 地址栏

地址栏是显示在文件窗口中文件列表区域顶部的标题栏。默认情况下，地址栏包含一个工具栏，[文件列表](../toolbars/the_default_toolbars/file_display_toolbar.zh.md) 工具栏：

![](/Manual/images/media/13/file_display_toolbar.png)

##### 默认地址栏工具栏

默认工具栏的主要组件是 [面包屑地址栏](breadcrumbs_location_field.zh.md)，它向您显示当前文件夹并允许您在当前层次结构内导航。

地址栏左侧的按钮是：

- ![](/Manual/images/media/13/location_toolbar_-_back.png) **后退：**返回 [后退](up_forwards_back.zh.md) 到上一文件夹。右键单击以显示先前文件夹的下拉列表。
- ![](/Manual/images/media/13/location_toolbar_-_forward.png) **前进：**[前进](up_forwards_back.zh.md) 到下一个文件夹（如果您之前已返回）。右键单击以显示后续文件夹的下拉列表。
- ![](/Manual/images/media/13/location_toolbar_-_up.png) **向上：**[向上](up_forwards_back.zh.md) 至文件夹层次结构中。右键单击以显示带有几个不同选项的下拉菜单。
- ![](/Manual/images/media/13/location_toolbar_-_refresh.png) **刷新：**刷新当前文件夹（默认情况下，文件列表和树被刷新）。
- ![](/Manual/images/media/13/location_toolbar_-_home.png) **主页：**转到您的 [主页文件夹](home_folder.zh.md)。右键单击以显示下拉菜单。

地址栏右侧的按钮是：

- **重复：**在另一个文件列表中重复此文件夹显示。如果不是已经处于该状态，文件窗口将切换到双栏模式。
- **交换：**用另一个文件列表替换此文件夹。在单显示模式下，此按钮不可见。
- **关闭：**关闭当前标签页。如果在双栏文件窗口中这是唯一标签页，它将关闭第二个文件列表。在仅打开一个标签页的单显示文件窗口中，此按钮不可见。

这是一个完全 [可配置的工具栏](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/README.zh.md)，因此您可以添加您自己的按钮并修改或移除默认按钮。请参阅 [文件列表工具栏](../toolbars/the_default_toolbars/file_display_toolbar.zh.md) 页面以了解有关这些按钮的更多信息。

##### 源/目标状态

复制文件等某些操作本质上需要涉及两个文件夹 - 源文件夹和目标文件夹。

在双栏文件窗口中，一个显示一直被指定为源，另一个显示一直被指定为目标。地址栏更改颜色以显示此情况。

默认情况下，单显示文件窗口没有任何源/目标状态，虽然如果您希望通过这种方式进行操作，则可以在配置中启用此功能。

有关源/目标概念的更多信息，请参阅 **[源和目标](../../source_and_destination.zh.md)** 主题。

##### 静态标题模式

在 **[地址栏/工具栏](/Manual/preferences/preferences_categories/location_bar/toolbars.zh.md)** 中，您可以选择关闭文件列表工具栏，在这种情况下，地址栏将恢复为一个更简单的静态标题：

![](/Manual/images/media/13/fdb1.png)

在单文件列表文件窗口的静态标题模式中，地址栏是可选的 - 您可以选择使用 **在单显示模式中显示标题** 选项来显示或不显示它。在双栏文件窗口中，始终显示地址栏。

从左到右的静态标题元素依次是：

- **位置：**显示当前位置。位置的各个部分是可单击的链接。
- **后退：**返回 [后退](up_forwards_back.zh.md) 到上一文件夹。
- **前进：**[前进](up_forwards_back.zh.md) 到下一个文件夹（如果您之前已返回）。
- **向上：**[向上](up_forwards_back.zh.md) 至文件夹层次结构中。
- **重复：**在另一个文件列表中重复此文件夹显示。
- **交换：**用另一个文件列表替换此文件夹。
- **关闭：**关闭当前标签页。