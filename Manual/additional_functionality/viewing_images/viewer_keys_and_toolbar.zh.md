# 查看器鼠标、键和工具栏

默认情况下，独立查看器的主要鼠标和键盘控件如下：

- **滚动图像：**用**左鼠标按钮**在图像周围拖动，或使用**光标键**。使用鼠标拖动时，按住**Ctrl**在 1:1 滚动和加速滚动之间切换。  
  \* **将图像拖动到其他应用程序：**使用**左鼠标按钮**，单击并拖动窗口图标（标题栏左上角），然后将其放在接受图像拖放的其他程序上（例如大多数图像编辑器）。  
  \* **选择图像的一部分：**使用**左鼠标按钮**，按住**Shift**键，然后单击并拖动图像来创建选取矩形。拖动以调整选取大小时，您可以按住**空格**键移动整个矩形并调整其起始点。通过定义选取后，您可以使用**Ctrl+C**将图像的那部分复制到剪贴板，或使用**Ctrl+R**裁剪查看器显示的内容。（注意：如果您不进行选取而使用**Ctrl+C**，则会将整个图像复制到剪贴板，因此您无需先选择全部。）  
  \* **切换有关图像的其他信息：**按下**F10**，图像信息将出现在右下角。再次按下同一键将其隐藏。  
  \* **切换幻灯片模式：**按下**S**键。当前图像列表将按计时器循环播放。  
  \* **切换全屏模式：**单击**中鼠标按钮**或按下**Alt+Enter**。  
  \* **下一张或上一张图像：**转动**鼠标滚轮**或按下**空格**和**退格**键。  
  \* **删除当前文件：**按下**Delete**键。  
  \* **放大和缩小：**在主键盘上按下**=**和**-**，或在数字键盘上按下**+**和**-**。您还可以按下**Ctrl**并转动**鼠标滚轮**。  
  \* **重置为原始大小（100% 缩放）：**在主键盘上按下**O**（字母 O）或在数字键盘上按下\*。  
  \* **设置为特定大小（25% 至 800% 缩放）：**在主键盘上按下**Ctrl+1**到**Ctrl+8**可获得各种缩放预设。  
  \* **适合窗口：**按下**F**。如果图像太大，无法容纳窗口，则会缩小大图像，但绝不会放大图像。（图片的纵横比始终保持不变。）  
  \* **扩展到窗口：**按下**G**。大型图像会缩小到适合窗口；小图像会放大以填满整个窗口。（图片的纵横比始终保持不变。）  
  \* **将图像向左旋转：**按下**L**。  
  \* **将图像向右旋转：**按下**R**。  
  \* **旋转到特定位置：**按下**1**（90 度），**2**（180 度）或**3**（270 度）。在主键盘或数字键盘上按下**0**（零）以重置图像旋转。  
  \* **水平翻转图像：**按下**H**。  
  \* **垂直翻转图像：**按下**V**。  
  \* **切换白色背景：**按下**Shift+W**。  
  \* **切换黑色背景：**按下**Shift+B**。  
（默认背景色可在配置中更改，但在查看使用透明度的图像时，动态更改背景色可能很有用。并非所有插件都支持以这种方式更改背景色。）

还有其他一些动作和热键，您可以在查看器的顶部菜单中找到：

- **文件：**“文件”菜单包含用于打开新图像、保存当前图像（当您裁剪图像或想要将其转换为不同格式时很有用）的命令。您可以打印当前图像，并启动 [图像转换](../image_conversion/README.zh.md) 功能以转换、调整大小或旋转图像。  
  \* **编辑：**包含一些简单的文件操作命令（*复制*、*移动*、*剪切*、*删除*）。您还可以将图像（或图像的选定部分）复制到剪贴板以粘贴到其他应用程序中。还可以根据当前选取裁剪图像。  
  \* **视图：**包含用于修改查看器窗口外观的命令。您还可以对图像进行旋转、放大和缩小，应用伽马校正，覆盖正常的背景色并选择性地禁用 Alpha 通道（如果有）。还有一个全屏命令可将图像显示为全屏模式，“*显示信息*”命令会在覆盖的工具提示中显示有关图像文件的信息。

**Ctrl+Tab**可用于在元数据编辑器中的字段和主查看器之间移动输入焦点。

##### 编辑查看器工具栏和键

独立图像查看器中的工具栏和上下文菜单是完全可配置的，[与列表中的所有工具栏和菜单一样](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/README.zh.md)。此外，您可以创建仅在查看器中激活的热键。

![](/Manual/images/media/image014_001.png)

要编辑查看器中的工具栏，只需像在列表中一样从“编辑”菜单中选择**自定义工具栏**命令。查看器上下文菜单可以从**[自定义](/Manual/customize/README.zh.md)**对话框中的*[上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md)*标签页进行编辑，您还可以在*键*标签页上创建特定于查看器的热键。

默认查看器工具栏称为*图像查看器*，但您可以从配置中的*查看器/外观*页面中选择另一个工具栏。例如，如果您想创建自己的工具栏，但保留默认工具栏不变，则可能需要这样做。

独立查看器的所有内部功能都可以通过**Show VIEWERCMD**命令访问。这些命令仅适用于查看器工具栏、菜单或热键 –如果您尝试在列表中运行它们，它们将不起作用。您可以从上面的屏幕截图中看到与*放大*功能相对应的命令是**Show VIEWERCMD=zoom,+**。**VIEWERCMD**命令的完整列表显示在 [显示命令](/Manual/reference/command_reference/internal_commands/show.zh.md) 引用部分。

尽管**Show VIEWERCMD**命令仅在查看器内有效，但这并不意味着它是唯一有效的命令 – 所有其他 Opus 命令和外部功能也在查看器内有效。当然，某些命令（例如**选择**）不适用于查看器，但当然可以使用**复制**或**重命名**之类的命令，或具有按钮在（例如）Photoshop 中打开当前图片。

如果在查看器中使用，**@if**指令可以测试各种**Show VIEWERCMD**选项的状态。例如，以下函数将在 100% 缩放和扩展到窗口模式之间切换：`@if:Show VIEWERCMD=zoom,reset
Show VIEWERCMD=zoom,grow
@if:else
Show VIEWERCMD=zoom,reset `

有关**@if**命令测试的更多信息，请参阅 [命令修饰符参考](/Manual/reference/command_reference/command_modifier_reference.zh.md) 部分。

鼠标滚轮和鼠标按钮的行为可以通过配置进行更改。例如，您可以让左鼠标按钮前进到下一张图像，或者关闭查看器（如果您愿意）。

##### 底部控制栏

查看器底部的可选控制栏与 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md)中的控制栏相同 - 它包含用于常用功能的按钮。您可以使用**查看/控制栏**命令启用或禁用它。与查看器顶部的主要工具栏不同，该工具栏无法编辑。
![](/Manual/images/media/viewer_pane_-_control_bar.png)

从左到右，按钮为**前一个文件**(![](/Manual/images/media/viewer_control_-_prev.png))，**下一个文件**(![](/Manual/images/media/viewer_control_-_next.png))，**向左旋转**(![](/Manual/images/media/viewer_control_-_rotate_left.png))，**向右旋转**(![](/Manual/images/media/viewer_control_-_rotate_right.png))，**放大**(![](/Manual/images/media/viewer_control_-_zoom_in.png))，**缩小**(![](/Manual/images/media/viewer_control_-_zoom_out.png))，**原始大小**(![](/Manual/images/media/viewer_control_-_original_size.png))，**适合窗口**(![](/Manual/images/media/viewer_control_-_fit_to_page.png))，**扩大到窗口**(![](/Manual/images/media/viewer_control_-_grow_to_page.png))，**十六进制视图**(![](/Manual/images/media/viewer_control_-_hex_view.png))，**幻灯片放映**(![](/Manual/images/media/viewer_control_-_slideshow.png))，**全屏**(![](/Manual/images/media/viewer_control_-_fullscreen.png))，**打印**(![](/Manual/images/media/viewer_control_-_printer.png)) 和**设置**(![](/Manual/images/media/viewer_control_-_settings.png))。