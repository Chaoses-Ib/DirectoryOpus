# 驱动按钮和下拉菜单

Directory Opus 所提供的 **驱动器** 工具栏显示了你的磁盘驱动器列表。这提供了一种极其简单的方式，可以从一个驱动器的根目录导航到下一个驱动器。

![](/Manual/images/media/13/drive_buttons.png) 

该工具栏实际上并不是 [默认工具栏](../toolbars/the_default_toolbars/README.zh.md) 之一（内建在程序中），而是由程序安装程序安装在你的 Opus 工具栏文件夹中。要启用，请从 ***设置 / 工具栏*** 菜单中选择 **驱动器**。

此工具栏为每个安装的磁盘驱动器显示一个按钮。工具栏上的按钮实际上被分组，以首先显示所有“固定驱动器”（主要是内部硬盘驱动器），然后是所有其它驱动器。要读取你的一个磁盘驱动器的根文件夹，只需单击该按钮。你也可以右键单击按钮，以显示驱动器的系统上下文菜单。

### 配置驱动器工具栏

驱动器工具栏是基于内部 `Go DRIVEBUTTONS` 命令构建的，你可以编辑用于生成驱动器按钮的命令，以配置它们的外观和行为。

参阅 [编辑工具栏](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/README.zh.md) 页面，了解有关编辑工具栏的信息，以及 [驱动器按钮配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/drive_buttons_configuration.zh.md) 页面，了解有关你可以对驱动器按钮进行的更改的具体信息。

### 驱动器下拉菜单

除了显示驱动器按钮外，Opus 还允许你将 **驱动器下拉菜单** 添加到工具栏中。这类似于驱动器按钮，因为它显示了你的磁盘驱动器列表，并允许你通过从下拉列表中选择驱动器来进行导航。

![](/Manual/images/media/13/drive_list.png)

### 添加驱动器列表下拉菜单

**驱动器下拉菜单** 可作为一个预定义的命令，从中添加 **[命令](/Manual/customize/the_customize_dialog/commands.zh.md)** 标签页的 **[自定义](/Manual/customize/README.zh.md)** 对话框。

1.  从 **设置** 菜单中选择 **自定义** 命令
2.  单击 **命令** 标签
3.  使用 *自定义* 对话框底部的搜索字段输入字符串 `drive`
4.  从结果列表中选择 **驱动器下拉菜单** 并将其拖动到其中一个工具栏
5.  单击 **确定** 以关闭 *自定义* 对话框

### 使用驱动器下拉菜单进行导航

默认情况下，通过 **驱动器下拉菜单** 进行导航的行为与通过 **驱动器按钮** 进行导航的行为略有不同。

下拉菜单记住你当前（或最近使用）的每个驱动器文件夹。当你从下拉列表中选择，比如说，***C*** 时，Opus 会把你带到 C: 上你上次使用的文件夹，而不是驱动器的根目录。

如果你愿意，可以更改此行为并使下拉菜单始终读取根文件夹。你还可以配置在列表中显示的驱动器，并控制哪个文件列表将列表应用于- 有关详细信息，请参阅 [驱动器下拉菜单配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/drive_list_configuration.zh.md) 页面。