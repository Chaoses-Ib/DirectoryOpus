# 样式

此页面可用于创建和编辑 [文件窗口样式](/Manual/basic_concepts/the_lister/styles.zh.md)。样式是一种可以应用到现有文件窗口的预定义配置。例如，您可以定义一种样式，在单个操作中打开查看器窗格和元数据窗格并关闭文件夹树。您可以使用默认工具栏上的 *文件窗口* 下拉菜单在不同样式之间切换。

使用列表上方的工具栏按钮来创建和管理样式。双击现有样式，或选择该样式并单击 **编辑** 按钮进行编辑。

### 编辑文件窗口样式

创建或编辑样式时，将弹出一个 **编辑文件窗口样式** 对话框。

- **名称**：编辑样式的名称。
- **描述**：可用于向样式分配描述。如果您不分配描述，Opus 将基于该样式中的设置显示默认描述。

这些字段下方有若干复选框和下拉列表，可用于定义样式确切影响哪些文件窗口元素。如果某个项目的复选框处于关闭状态，则样式不会对文件窗口中的该元素产生任何影响。如果复选框处于开启状态，则应用该样式时将使用该元素的设置。样式可以影响的元素如下：

- **文件列表**：此样式可以将文件窗口强制设置为 [单显示或双栏](/Manual/basic_concepts/source_and_destination.zh.md) 模式。此下拉列表允许您在水平或垂直布局中选择单显示或双栏。您还可以选择在导航锁定自动激活的情况下将文件窗口设置为双栏（此下拉列表中的 ![](/Manual/images/media/style_navlock.png) 图标表示该设置）。
- **文件夹树**：您可以让样式关闭或打开 [文件夹树](/Manual/basic_concepts/the_lister/navigation/folder_tree.zh.md)。如果文件窗口处于双栏模式，还可以设置样式以在该模式下打开双文件夹树。
- **查看器窗格**：此样式可以在水平或垂直方向上关闭或打开 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md)。
- **元数据窗格**：您可以按照水平或垂直方向关闭或打开 [元数据窗格](/Manual/basic_concepts/the_lister/metadata_pane.zh.md)。
- **工具栏**：可通过开启此选项更改样式显示哪些工具栏，并选择单个工具栏或 **[工具栏组](../toolbars/toolbar_sets.zh.md)**。
- **实用程序面板**：此样式可以关闭或打开 [实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)。如果开启实用程序面板，您可以选择打开其哪种模式 - [查找](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md)、[同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md) 或 [重复项](/Manual/additional_functionality/duplicate_file_finder.zh.md)。
- **状态栏**：此样式可以关闭或打开文件窗口的 [状态栏](/Manual/basic_concepts/the_lister/status_bar.zh.md)。
- **格式锁定**：此样式可以关闭或打开 [格式锁定](/Manual/basic_concepts/folder_options/locking_the_format.zh.md)。
- **胶卷**：此选项会将文件窗口设置为一种特殊模式：在该模式下，查看器窗格处于开启状态，且单文件列表中显示一行可滚动的缩略图。

### 文件列表配置

在文件窗口元素选项下方是其它一些选项，这些选项允许您配置该样式显示的文件夹、文件夹格式和标签页。如果这些选项处于关闭状态，则该样式将仅重新配置文件窗口，而不会更改文件窗口当前显示的文件夹；但是您也可以定义一个样式来读取新文件夹、打开一组标签页等。

单独为 **左文件列表** 和 **右文件列表** 配置这些选项。如果文件窗口不处于双栏模式，则只使用 **左文件列表标签页** 上的选项。

- **标签页组**：使样式打开文件夹标签页组。此下拉列表显示在 **[文件夹标签页/标签页组](../folder_tabs/groups.zh.md)** 配置页面上配置的所有标签页组的列表。选择一个标签页组会覆盖所有后续选项。
- **关闭现有文件夹标签页**：此选项使样式关闭所有现有标签页，然后再打开样式定义的新标签页。如果关闭此选项，此处定义的任何标签页将被添加到文件列表中的现有标签页。
- **视图模式**：此样式可以更改文件列表中的 [视图模式](/Manual/basic_concepts/the_lister/view_modes.zh.md)。您可以从下拉列表中选择任何标准视图模式（详细资料、列表等）以及自动。自动是一种特殊模式，表示“将视图模式重置为通常针对显示文件夹的默认模式”。系统将查阅 [文件夹格式](/Manual/basic_concepts/folder_options/folder_formats.zh.md) 以确定显示文件夹的适当视图模式。
- **格式**：此样式可以定义应用于当前文件夹的文件夹格式，或者如果激活 **文件夹**（如下），则在读取新文件夹后应用于该文件夹。
- **平面视图**：此样式可以关闭 [平面视图](/Manual/basic_concepts/flat_view.zh.md)，或在平面视图的各种模式中任意一种模式下开启它。
- **文件夹**：此样式可以定义一个新文件夹，在样式激活时读取该文件夹至文件列表中。