# 使用热键控件

[命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md)和[自定义](/Manual/customize/README.zh.md)对话框中的密钥页面都使用一个特殊的字段，即*热键控件*，以使输入热键序列变得更容易。

![](/Manual/images/media/hotkey_control_0.png)

要分配一个简单的按键，只需单击即可激活它，就像普通字符串字段一样，然后按下所需的组合键。例如，要为函数分配**Alt + D**，请单击该字段并同时按下**Alt**和**D**键。

如果使用鼠标单击下拉箭头，则会显示一个菜单，其中包含有关热键的几个命令。

![](/Manual/images/media/hotkey_control_2.png)

- **左** / **右**： 对于位于 [文件列表工具栏](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/file_display_toolbar.zh.md) 中的按钮（如上所示），**左**和**右**项目可让你分配一个仅适用于文件列表左侧或右侧的键。请参阅下面的示例，了解如何使用此功能。
- **输入** /\*\* Escape\*\* /\*\* Tab\*\*： 允许你为这些键分配一个热键。
- **原始** / **上一个**： 如果你已经更改了密钥，这两个命令可让你恢复到上一个设置以及该对话首次打开时分配的原始密钥。
- **添加替代项**： 此命令可让你为同一命令添加一个备用键序列。例如，默认的 [位置字段](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.zh.md) 可以通过按 **Alt + D** 或 **F4** 键来激活。请参阅下面的示例，了解如何使用此功能。
- **添加到序列**：此命令可让你向当前键序列添加一个其他键。你可以使用此功能创建热键，在创建热键时，必须按顺序（而不是同时）按下两个或更多个键才能激活该函数。
- **移除**： 此操作会从控件中移除（清除）热键。

在编辑热键函数（而不是工具栏按钮的热键）时，下拉菜单还可让你从*媒体键*子菜单中进行选择。

![](/Manual/images/media/hotkey_control_14.png)

这些是与键盘上的传统键不相关的特殊输入事件。例如，你可以使用此功能为键盘上的*播放*按钮或鼠标上的*后退*按钮分配一个函数。

# 使用热键控件

在上方的屏幕截图中，**Alt + D** 是当前唯一的键分配。选择**添加替代项**命令会显示一个**+**符号，表示下次按键将添加一个备用序列。

![](/Manual/images/media/hotkey_control_3.png)

然后，如果你按下另一个键，则该键将作为备用序列的开头添加。例如，如果你按下 **F4**：

![](/Manual/images/media/hotkey_control_4.png)

现在，按下 **Alt + D** 或 **F4** 即可激活此函数。你可以根据需要添加任意数量的备用键序列。当具有备用键序列的控件处于活动状态时，它将显示一个单独的下拉列表，分别列出每个备用序列。

![](/Manual/images/media/hotkey_control_6.png)

主编辑字段中显示的序列（上图中为 **F4**）是*当前序列*，并且是唯一可以编辑的序列。例如，如果你此时按下 **F3**，**F4** 将被 **F3** 替代，但 **Alt + D** 序列将不受影响。如果你想要编辑其他序列，而不是当前序列，你可以单击其 ***删除*** 链接将其删除，然后再次添加。

# 使用热键控件

根据你使用热键的频率，你可能会发现键盘上的键用完了，无法再分配给函数。多个键序列可让你创建附加热键，这些热键需要按顺序按下两个或更多个键才能激活此函数，这极大地增加了你可以定义的热键函数的数量。

向序列添加键的过程类似于添加替代项。选择**添加到序列**命令，该命令会显示一个**&**符号，表示下次按键将添加到当前序列。

![](/Manual/images/media/hotkey_control_5.png)

  
按下你想要添加到序列中的键，控件将更新以显示新分配。例如，如果你此时按下 **1**：

  
![](/Manual/images/media/hotkey_control_7.png)

为了激活此热键，你现在需要按下 **Alt + D**，然后按下 **1**。不同的热键可以使用相同的键，直至序列中的最后一个键。例如，因此，你可以创建多个热键，所有热键都以 **Alt + D** 开头，后跟不同的数字（例如，**Alt + D** 后跟 **1** 可以运行一个函数，而 **Alt + D** 后跟 **2** 可以运行另一个函数）。你可以根据需要向序列添加任意数量的键。在文件窗口中，当你按下与多键序列开头匹配的键时，Opus 会在左下角显示一个小的弹出窗口，作为你需要按下另一个键才能运行函数的可视提示。

  
![](/Manual/images/media/hotkey_control_8.png)

# 使用热键控件

[文件列表工具栏](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/file_display_toolbar.zh.md) 的处理与所有其他工具栏略有不同，因为在 [双栏模式](/Manual/basic_concepts/the_lister/dual_display/README.zh.md) 中，它有两个副本。通常，按下文件列表工具栏中按钮的热键会激活源文件列表的函数。但是，你可以分配一些热键，无论哪一项是源，都会专门在左侧（或顶部）或右侧（或底部）文件列表中激活此函数。例如，你可以通过按 **Shift + F4** 激活左侧文件列表的位置字段，通过按 **Ctrl + F4** 激活右侧文件列表的位置字段。

从你要分配的第一个键序列开始：

![](/Manual/images/media/hotkey_control_11.png)

然后从下拉菜单中选择**左**命令。这会将该键序列绑定到左侧文件列表。

![](/Manual/images/media/hotkey_control_9.png)

然后，按照上述步骤为右侧文件列表添加一个备用键序列。从下拉菜单中选择**添加替代项**命令：

![](/Manual/images/media/hotkey_control_10.png)

并按右侧文件列表的键：

![](/Manual/images/media/hotkey_control_12.png)

最后，从下拉菜单中选择**右**命令，将新序列绑定到右侧文件列表。

![](/Manual/images/media/hotkey_control_13.png)