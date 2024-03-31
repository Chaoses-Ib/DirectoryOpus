编辑工具栏

编辑工具栏并创建按钮（或修改现有按钮）的第一步是进入 [Customize](/Manual/customize/README.zh.md) 模式。执行此操作的最简单方法是从 **Settings** 菜单中选择 **Customize Toolbars** 命令。

![](/Manual/images/media/customize_toolbar_item.png) 

*一个有用的提示是：*如果您发现无法进入 **Customize Toolbars** 命令（因为您已将其从菜单中删除或关闭该工具栏），那么您始终可以通过文件窗口的窗口菜单进入（单击左上角的图标）。

![](/Manual/images/media/customise_window_menu.png)

进入 Customize 模式的另一种方法（尤其是您想要编辑特定按钮时），打开 Preferences 中 **[Toolbars / Options](/Manual/preferences/preferences_categories/toolbars/toolbar_options.zh.md)** 页上的 **按 <kbd>Alt</kbd> 点击以编辑工具栏按钮** 选项。在此选项打开的状态下，按住 <kbd>Alt</kbd> 键并用鼠标左键单击工具栏按钮，将使 Opus 进入 Customize 模式并显示您单击的按钮的命令编辑器。

无论您如何进入 Customize 模式，一旦您进入该模式，所有工具栏都将变为可编辑状态。*另一个有用的提示是：*您仍可以通过按 <kbd>Shift</kbd> 键并单击来从 Customize 模式运行工具栏按钮。

![](/Manual/images/media/toolbars_in_customize.png) 

上图显示了 Customize 模式下的默认工具栏。当您进入 Customize 模式时，您会注意到的唯一可见更改是，各种字段已被占位符代替。在上面的示例中，**Search** 字段是可调整大小的（通过其右边缘上的抓柄符号指示）- 您可以通过拖动右边缘来调整其大小。**Location** 和 **Spacer** 字段没有调整大小的抓柄，这表明它们已设置为 *full width* 模式。请参阅 [Field Buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/README.zh.md) 页面，以了解更多有关字段按钮的信息。

您还会注意到，在 Customize 模式下，底部工具栏上的按钮不完全适合可用空间。这是因为以前隐藏的按钮 - 这种情况下的 **Toolbar Marker** 按钮 - 在 Customize 模式下变为可见。请参阅 [Dynamic Buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md) 页面，以了解更多有关此类按钮的信息。

当按钮不适合 Customize 模式下的可用空间时，工具栏的右侧会出现两个小箭头。 您可以使用这些箭头滚动工具栏并访问不可见的项目。

工具栏编辑主要基于鼠标。所有按钮（和工具栏本身）都具有 [上下文菜单](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/toolbar_context_menus.zh.md)，您可以在 Customize 模式下通过右键单击来访问该菜单。

##### 编辑现有按钮

要编辑现有按钮，请双击它。或者，右键单击该按钮并从上下文菜单中选择 **Edit**。在这两种情况下，[Command Editor](command_editor/README.zh.md) 对话框都将打开，让您可以更改按钮的外观和功能。

要编辑下拉菜单中的函数，请左键单击菜单以将其打开，然后正常编辑其中的按钮。在 Customize 模式下，下拉菜单将保持打开状态，直到您再次单击它以将其关闭（或直到打开同一工具栏上的另一个下拉菜单）。

##### 添加新的预定义按钮

要添加预定义按钮（已为其分配命令的按钮），请在 Customize 对话框的 **Commands** 标签页上找到所需的命令，然后将其拖放到工具栏。按钮将被添加到您将其放置的位置。您还可以通过将按钮拖到菜单上来将按钮添加到下拉菜单中 - 短暂延迟后，菜单将弹出，然后您可以将按钮拖动到其中。

##### 添加新的空按钮

要将全新的按钮（没有定义功能的按钮）添加到工具栏，请执行以下任一操作：

- 从 Customize 对话框的 **Commands** 标签页中，展开 **New** 类别，然后将 **New Button** 从列表中拖出并将其放置在工具栏上。这将在您将其放置的位置添加按钮。
- 右键单击工具栏末尾的空白处，然后从上下文菜单中选择 **New \> New Button**。这将在工具栏的末尾添加按钮。
- 右键单击现有按钮并选择 **Insert New \> New Button** 以在您单击的按钮后立即插入新按钮。

添加新按钮后，您可以通过双击或右键单击来编辑它（如上所述）。

##### 添加运行外部程序的按钮

要添加启动外部程序的按钮，您可以简单地拖动该程序的图标（或指向该程序的快捷方式）并将其放置在工具栏上。例如，您可以在 Windows“开始”菜单中拖动快捷方式，或从 C:\Program Files 目录中拖动程序图标。

当您将程序放置在工具栏上时，会弹出 **[启动选项](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/launch_options.zh.md)** 对话框，允许您选择运行程序的方式。例如，您可能希望独立运行程序，或向其传递所选文件。如果 **启动选项** 对话框已配置为在不重新出现的情况下始终使用特定设置，您可以通过按住 <kbd>Ctrl</kbd> 键并同时将程序放置在工具栏上 迫使其出现。

##### 添加将您带到文件夹的按钮

拖动文件夹（或指向文件夹的快捷方式），并将其放置在工具栏上，以创建一个将导航到该文件夹的按钮。

##### 复制现有按钮

要复制现有工具栏按钮，您可以：

- 拖动按钮，并且在按住 <kbd>Ctrl</kbd> 键的同时，将其放置在新位置处。
- 右键单击按钮并从上下文菜单中选择 **Copy**，然后右键单击工具栏上的空白处或现有按钮，并从上下文菜单中选择 **Paste**。如果您右键单击现有按钮，则复制会立即插入在其后。如果您右键单击工具栏的空白处，则复制会添加到工具栏的末尾。

您可以将现有按钮复制到同一工具栏或另一个工具栏。您可以通过将按钮拖动到菜单上并在那里停留一小段时间来将按钮复制到下拉菜单 - 菜单会弹出，允许您将按钮拖动到其中。确保按住 <kbd>Ctrl</kbd> 键，直到释放鼠标按钮。

##### 移动现有按钮

要将工具栏按钮从一个位置移动到另一个位置（在同一工具栏或其他工具栏上），您可以：

- 拖动按钮并将其放置在新位置处。
- 右键单击按钮并从上下文菜单中选择 **Cut**，然后右键单击工具栏上的空白处或现有按钮，并从上下文菜单中选择 **Paste**。如果您右键单击现有按钮，则剪切的按钮将移动到紧随其后的位置。如果您右键单击工具栏的空白处，则剪切的按钮将移动到工具栏的末尾。
你可以将工具栏按钮移动到下拉菜单中，方法是将按钮拖到菜单上并在那里停留一小段时间 - 菜单将自动弹出，让你将按钮拖进去。你还可以使用复制和粘贴操作进入或退出下拉菜单 - 只要点击菜单打开它，然后像往常一样右键单击其中的按钮。

##### 删除按钮

若要删除工具栏按钮，你可以：

- 将按钮从工具栏中拖出，然后将其拖放到“自定义”对话框。
- 右键单击该按钮，然后从上下文菜单中选择 **删除**。

##### 添加一个新的空子菜单（或菜单按钮）

若要向工具栏添加一个全新的子菜单（然后可以在其中添加更多项），请执行以下任一操作：

- 从“自定义”对话框的 **命令** 标签页中，展开 **新建** 类别，然后将 **新菜单**（或 **新菜单按钮**）从列表中拖出并将其拖放到工具栏上。这将在你将其拖放的位置添加该菜单。
- 右键单击工具栏末尾的空白处，然后从上下文菜单中选择 **新建 > 新菜单**（或 **新菜单按钮**）。这将在工具栏末尾添加按钮。
- 右键单击现有按钮或菜单，然后选择 **插入新建 > 新按钮**（或 **新菜单按钮**）以在你单击的按钮后面立即插入新菜单。

添加新菜单后，你可以对其进行编辑（通过双击或右键单击，如上面所述），如果你用左键单击打开它，则可以像对顶级工具栏一样在其中添加项。

请参阅 [下拉按钮和菜单](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/drop-down_buttons_and_menus.zh.md) 以了解不同子菜单类型的信息。

##### 插入分隔符

若要在两个按钮之间插入分隔符，你可以：

- 将按钮向右拖动一段小距离（几个像素）。如果你将按钮拖动得太远，你将移动它 - 你只需将其拖动一小段距离即可插入分隔符。
- 右键单击该按钮，然后在上下文菜单中启用 **开始一个组** 选项。

在任何一种情况下，分隔符都将被添加到你拖动或右键单击的按钮和其之前的按钮（左侧）之间。

##### 删除分隔符

若要从两个按钮之间删除分隔符，你可以：

- 将按钮（分隔符右侧的按钮）向左拖动几个像素。
- 右键单击该按钮，然后在上下文菜单中取消启用 **开始一个组** 选项。

##### 在按钮之间留出间隙

你可以使用 **间隔符** 字段在按钮之间留出间隙（或右对齐一个或多个按钮）。

- 在“自定义”对话框的 [[..:the_customize_dialog:commands|命令]] 标签页上，找到 **新建** 类别下的 **间隔符**，然后将其拖动到工具栏。或者，右键单击现有按钮并选择 **插入新建 > 间隔符**，或右键单击工具栏的空白处并选择 **新建 > 间隔符**。
- 你可以手动调整间隔符的大小，也可以右键单击它并启用“全宽”选项，以使其自动右对齐后续的任何工具栏按钮。有关更多信息，请参阅 [[~field_buttons|字段按钮]] 部分。

更多内容：

[启动选项](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/launch_options.zh.md)  
[工具栏上下文菜单](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/toolbar_context_menus.zh.md)  
[多功能按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/multiple_function_buttons.zh.md)  
[下拉按钮和菜单](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/drop-down_buttons_and_menus.zh.md)  
[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)  
[字段按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/README.zh.md)  
[与他人共享函数](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/sharing_functions_with_others.zh.md)