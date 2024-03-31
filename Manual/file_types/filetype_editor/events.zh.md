# 事件

“**事件**”标签页允许你配置由各种鼠标事件引发的文件类型功能——双击和拖放事件。例如，你可以将 Opus 配置为在按住“**Shift**”键双击文件或使用鼠标中键双击文件（如果你有的话）时为其运行不同的程序。还可以使用此系统设置不同的双击行为来区别于资源管理器——以便在 Opus 中双击某个文件与在资源管理器中双击该文件触发不同的行为。

![](/Manual/images/media/filetypes_-_events.png) 

上方的屏幕截图显示了为“**图片**”[文件类型组](../file_type_groups.zh.md)配置的若干事件示例。你可以配置的事件包括：

- **拖放**：将文件拖放到其他文件夹时发生的事件。
- **左键双击**：使用鼠标左键双击文件后发生的事件。
- **中键双击**：使用鼠标中键双击文件后发生的事件。

这三个事件还可以根据是否按住“**Alt**”、“**Ctrl**”或“**Shift**”键进行单独配置。没有右键双击事件，因为右键用于[上下文菜单](context_menu.zh.md)。你还可以将项目添加至拖放上下文菜单（使用鼠标右键拖动文件时显示的菜单），方法是在[拖放菜单](drop_menu.zh.md)标签页中执行此操作。

每当发生上述事件之一时，Opus 都会搜索已配置的文件类型以查找已配置的操作。文件类型的搜索顺序如下：

1.  该文件的特定文件类型（例如，对于“**.jpg**”文件，这可能是“**JPEG 图像**”文件类型）
2.  包含该文件扩展名的文件类型组（例如“**图片**”）
3.  如果文件是已识别的图像文件，则为“**已识别的图像**”文件类型
4.  “**所有文件**”文件类型（或对于文件夹，为“**所有文件夹**”）
5.  “**所有文件和文件夹**”文件类型。

使用具有针对该事件定义的功能的最先找到的、最具体的文件类型。

要编辑文件类型的事件，请从列表中选择该事件，然后单击页面底部的“**编辑**”按钮（或双击列表中的事件）。事件编辑器是标准命令编辑器的一种变体，因此请参阅[命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md)页面，了解如何定义命令的说明。

你还可以右键单击事件列表中的项目以显示该事件的上下文菜单。此上下文菜单允许你使用“**复制**”和“**粘贴**”将定义从一个事件复制到另一个事件。

事件系统非常有用；经过周密的思考和配置，有可能真正简化你的工作流程。以上述屏幕截图为例，已为“**图片**”组配置了四个事件（意味着它们将对添加到该组的任何文件类型起作用）。

1.  ![](/anchor/convertpng/)已配置“**拖放 + Ctrl**”事件，以便当你按住“**Ctrl**”键并将图像释放到文件夹中时，可以将图像转换为 PNG 格式。

![](/Manual/images/media/event_-_dropctrl.png)

用于此操作的功能是 **Image CONVERT=png**。这会调用[图像转换](/Manual/additional_functionality/image_conversion/README.zh.md)功能并指定输出格式为 PNG。由于已在命令行中指定了输出格式，因此不会显示图像转换对话框——取而代之的是，释放的文件会立即以 PNG 格式保存到目标文件夹中。

1.  已配置“**左键双击**”事件，以便当双击文件时，使用 Opus 内部查看器打开该文件。

![](/Manual/images/media/event_-_dblclk.png)

此事件调用内部的**[显示](/Manual/reference/command_reference/internal_commands/show.zh.md)**命令，以使用[独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md)查看图像。这使你可以在 Opus 中双击图像以在其自己的查看器中快速预览它们，但不会对在 Opus 之外双击图像文件时发生的操作产生任何影响。

1.  已配置“**左键双击 + Ctrl**”事件，以便当你按住“**Ctrl**”键双击文件时，在 Photoshop 中打开该文件。

![](/Manual/images/media/event_-_dblclkctrl.png)

此事件运行外部功能 **"C:\Program Files\Adobe\Adobe Photoshop CS5 (64 Bit)\Photoshop.exe" %1**，以便在 Photoshop 中打开文件。**%1** [控制代码](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md)用于将文件名传递给 **Photoshop.exe**。

1.  最后，已配置“**中键双击**”事件，以便当你使用鼠标中键双击文件时，在标准 Windows 图像查看器中打开该文件。

![](/Manual/images/media/event_-_middleclk.png)

此事件运行外部功能 **C:\Windows\System32\rundll32.exe "C:\Program Files\Windows Photo Viewer\PhotoViewer.dll", ImageView_Fullscreen %1**，此功能会调用 Windows 照片查看器。文件名使用**%1** [控制代码](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md)传递给该应用程序。