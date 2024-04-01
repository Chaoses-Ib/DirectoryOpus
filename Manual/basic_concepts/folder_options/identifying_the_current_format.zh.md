# 确定当前格式

如你所了解的，文件夹格式系统相当复杂——我们发现这是新 Opus 用户经常感到最困惑的问题之一。显示格式可以自动改变，有时看似随机，而且很有可能不知道为什么使用特定格式。

Opus 提供了一个功能来帮助解决这个问题。如果你将鼠标悬停在状态栏中的 ![](/Manual/images/media/13/info.png) 图标上，则将显示的工具提示将描述如何以及为什么使用当前显示格式。

![](/Manual/images/media/13/format_explain.png)

在上面的示例中，我们可以看到这个文件列表中的当前格式开始于 [自动记忆的格式](auto_folder_formats.zh.md)，但后来被打开了一个列的命令修改了（在本例中，用户右键单击列头并添加了 *创建时间* 列）。

### 更多信息

信息工具提示还显示文件窗口的来源（在本例中是一个名为 **上次关闭的文件窗口** 的系统布局——即上次关闭 Opus 时它处于打开状态）。如果适用，它还可以显示背景图片的来源（如果 [文件夹图片](/Manual/preferences/preferences_categories/folders/folder_images.zh.md) 系统正在使用中）。

### 通过信息图标的右键单击菜单执行格式命令

![](/Manual/images/media/13/status_info_menu.png)

右键单击状态栏信息图标以显示其上下文菜单。这会让你可以访问各种与文件夹格式有关的命令。

前三个命令是：

- **锁定格式**：[锁定](locking_the_format.zh.md) 格式，以防止自动更改。
- **文件夹格式**：显示 [文件夹格式对话框](folder_options_dialog/README.zh.md)。
- **管理文件夹格式**：转至配置中的 [文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md) 页面。

下一组命令列出不同的 [内容类型格式](content_types.zh.md)。选择其中一个命令以立即切换到该格式。

下一组命令允许你通过多种方式重置格式：

- **重置为文件夹格式**：如果你将文件夹加载到一个新标签中，它将具有的格式。
- **重置为文件夹类型格式**：这种类型的文件夹（而不是此特定文件夹）的默认格式。
- **重置为“用户默认”格式**：可编辑的“用户默认”格式。
- **重置为出厂默认格式**：不可编辑的出厂默认格式。

在底部，**编辑状态栏** 命令会转到你 [文件列表/状态栏](/Manual/preferences/preferences_categories/file_displays/status_bar.zh.md)配置页面，可以在其中配置状态栏定义。

### 能够移除状态栏图标

![](/Manual/images/media/13/info.png) 图标是在状态栏中使用 `{fl}` 代码生成的。由于状态栏可通过配置配置，因此可能可以移除此代码——如果是这样，图标将不可见。在这种情况下，你可以从 [文件列表/状态栏](/Manual/preferences/preferences_categories/file_displays/status_bar.zh.md)配置页面中添加它。