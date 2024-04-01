# DOpusRT 参考手册

DOpusRT 是一项独立的程序 (**dopusrt.exe**)，可为 Directory Opus 执行各种支持功能：

- 如果 [双击桌面](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_desktop.zh.md) 已启用，则它在启动时会在后台运行，以检测双击并在 Opus 未运行时启动 Opus。
- 如果 [资源管理器替换](/Manual/basic_concepts/explorer_replacement.zh.md) 模式已启用，则在打开文件夹时将其用作默认“处理程序”，并且它可以在 Opus 未运行时再次启动 Opus。
- 你可以使用它从 Opus 外部运行内部命令。
- 你可以使用它在 Opus 外部通过独立查看器显示图片。
- 你可以使用它在 Opus 外部操作 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)。
- 你可以使用它在 Opus 外部 [检索当前显示的文件夹和文件信息](/Manual/reference/dopusrt_reference/retrieving_file_and_folder_information.zh.md)。

程序 **dopusrt.exe** 位于 Opus 主程序文件夹中（通常为 *C:\Program Files\GPSoftware\Directory Opus*）。请注意，如果你要从 Opus 按钮或热键调用 DOpusRT，则不必使用完整路径 - 你可以使用 **dopusrt** 关键字作为 .exe 实际位置的快捷方式。否则，通常需要在使用时指定命令的完整路径（例如，在快捷方式或批处理文件中）。在下面的示例中，为了清楚起见，省略了完整路径。

DOpusRT 命令行由一个 *命令* 和该命令的相应 *参数* 组成。为了完整起见，所有 **dopusrt.exe** 命令在此处列出 - 但其中许多命令设计为仅供 Opus 自身使用。你最有可能感兴趣的命令是 **/cmd** 和 **/col**。

<table>
<thead><tr><th>
命令</th><th>
参数</th><th>
描述</th></tr></thead><tbody><tr><td>

**/acmd**</td><td>

*\<command and arguments\>*</td><td>

从 Opus 外部调用 Opus 命令。如果一个或多个 Opus 文件窗口已打开，则该命令将发送到当前窗口或最近的活动窗口。

//<Example://> **dopusrt.exe /acmd Go "C:\Program Files"**  
**                    -** *在最后活动窗口中导航到“C:\Program Files”（如果当前没有活动窗口，则在新窗口中导航）*
</td></tr><tr><td>

**/argsmsgbox**</td><td>

*(no arguments)*</td><td>

在消息框中显示所有剩余参数。这在希望查看 Opus 命令在调用外部命令时生成的命令行时很有用。

//<Example://> **dopusrt.exe /argsmsgbox Hello World**  
**                   ** *- 在消息框中显示“Hello World”*
</td></tr><tr><td>

**/argstoclip**</td><td>

*(no arguments)*</td><td>

将所有剩余参数放入剪贴板。与 **/argsmsgbox** 一样，这也可用于检查 Opus 将传递给外部命令的内容。

请注意，Opus 有一个内置的 **[剪贴板](command_reference/internal_commands/clipboard.zh.md)** 命令，如果你只想将文本或文件名放入剪贴板，它是一个更好的选择。

//<Example://> **dopusrt.exe /argstoclip Hello World**  
**                   ** *- 将“Hello World”放入剪贴板*
</td></tr><tr><td>

**/changelanguage**</td><td>

*\<language\>*</td><td>

更改用户界面语言。Opus 将重新启动，工具栏和菜单将被翻译（如果可能）。

//<Example://> **dopusrt.exe /changelanguage deutsch**  
**                   ** *- 将语言更改为德语*
</td></tr><tr><td>

**/cmd**</td><td>

*\<command and arguments\>*</td><td>

从 Opus 外部调用 Opus 命令。如果一个或多个 Opus 文件窗口已打开，则该命令将发送到源窗口。（将此与上述\*\* /acmd\*\* 进行比较。）

//<Example://> **dopusrt.exe /cmd Go C:\\ NEW=0,0,640,480**  
**                    -** *打开一个新的文件窗口，以指定坐标显示 C:\\*
</td></tr><tr><td>

**/col**</td><td>

*\<collection command\>*</td><td>

让你在 Opus 外部操作文件集合。有关更多信息，请参阅 [外部操作文件集合](/Manual/reference/dopusrt_reference/external_manipulation_of_file_collections.zh.md) 页面。

*<Example://> **dopusrt.exe /col create "Holiday Photos"**  
**                    ***- 创建名为“假日照片”的集合//
</td></tr><tr><td>

**/dblclk**</td><td>

*(no arguments)*</td><td>

在后台运行，以管理桌面上双击功能。

你不需要手动运行此命令 - 当启用桌面双击选项时，Opus 会自动启动它。
</td></tr><tr><td>
</td><td>

**=off**</td><td>

停用正在运行的双击管理器。如果你想暂时禁用桌面双击功能（而不是使用任务管理器终止 **dopusrt.exe** 实例），则可以使用此命令。

*<Example://> **dopusrt.exe /dblclk=off**  
**                    ***- 关闭桌面处理程序上的双击//
</td></tr><tr><td>

**/dde**</td><td>

*(no arguments)*</td><td>

运行 DDE 服务器以侦听与打开文件夹相关的 DDE 命令。

当你在一个文件夹上双击时，此命令会在资源管理器替换模式下使用。你不需要手动运行此命令。
</td></tr><tr><td>

**/delay**</td><td>

***=*\<seconds\>****</td><td>

仅在 **/dblclk** 之后有效。在设置自身之前，导致桌面双击功能等待指定秒数。这可用于解决与其它软件的冲突，如果在 Windows 启动周期结束时启动，这些冲突将破坏桌面双击。

*<Example://> **dopusrt.exe /dblclk /delay=10**  
**                    ***- 在初始化桌面双击之前等待 10 秒//  
你通常不需要自己使用此参数，但在注册表中可能会看到它。你可以在配置桌面双击时通过配置来指定延迟。
</td></tr><tr><td>

**/flushplugins**</td><td>

*(no arguments)*</td><td>

从内存中刷新查看器插件。如果 Opus 正在运行，则所有当前未使用的插件将被卸载。如果你正在开发插件并且想替换 DLL 文件而不必退出 Opus，则可以使用此功能。

*<Example://> **dopusrt.exe /flushplugins**  
**                    ***- 刷新未使用的查看器插件//
</td></tr><tr><td>

**/help**</td><td>

*\<help path\>*</td><td>

在你的网络浏览器中从本地帮助中显示指定的文档。这用于实现 **opushelp://** URL 方案，Opus 在安装时会注册该方案。
</td></tr><tr><td>

**/info**</td><td>

*\<information command\>*</td><td>

让你在 Opus 外部检索当前显示的文件夹和文件信息。有关更多信息，请参阅 [检索文件和文件夹信息](/Manual/reference/dopusrt_reference/retrieving_file_and_folder_information.zh.md) 页面。

//<Example://> **dopusrt.exe /info path_list.txt,paths**  
- *创建一个 XML 文件（path_list.txt），其中列出所有当前打开的文件窗口中当前显示的路径*
**dopusrt.exe** 参数：

| 参数 | 值 | 说明 |
|---|---|---|
| **open** | `<文件夹路径>` | 打开一个显示指定路径的新列表窗口。 |
|**示例：** | **dopusrt.exe /open "C:\Program Files"**<br>**                    ***- 打开一个显示 C:\Program Files 文件夹的列表窗口** |
|**restart** | *(无参数)* | 如果 Opus 已在运行，则重新启动它。如果 Opus 尚未运行，则启动它。 |
|**示例：** | **dopusrt.exe /restart**<br>**                    ***- 重新启动或启动 Opus** |
| | **:norun** | 如果 Opus 已在运行，则重新启动它，但如果没有运行，则不启动它。 |
|**示例：** | **dopusrt.exe /restart:norun**<br>**                    ***- 如果 Opus 已在运行，则重新启动它** |
| **runopus** | *(无参数)* | 如果 Opus 尚未运行，则启动它。在 Vista 及更高版本中，即使调用 **dopusrt.exe** 的进程具有提升权限，此操作始终将以非提升权限启动 Opus。 |
| **示例：** | **dopusrt.exe /runopus**<br>**                    ***- 如果 Opus 尚未运行，则以非提升权限运行它** |
| **runstd** | `<命令行>` | 允许你启动另一个程序。在 Vista 及更高版本中，即使调用 **dopusrt.exe** 的进程具有提升权限，此操作仍将以非提升权限运行指定命令（这实际上是此命令的唯一作用）。 |
|**示例：** | **dopusrt.exe /runstd notepad.exe**<br>**                    ***- 以非提升权限运行 notepad.exe** |
| **show** | `<文件名>` | 使用 Opus [独立查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 显示指定文件。你可以使用此参数将 Opus 查看器设为文件类型的默认系统图像查看器。 |
|**示例：** | **dopusrt.exe /show %1 **<br>**                    ***- 显示选定的图像（上下文菜单项的定义）* |
| **vcmd** | `<命令和参数>` | 在 Opus 之外调用 Opus 命令，在当前（或最近）处于活动状态的图像查看器的上下文中。如果没有打开图像查看器，则将忽略该命令。 |
| **示例：** | **dopusrt.exe /vcmd Show VIEWERCMD=selectall**<br>**                    - 选择当前处于活动状态的查看器中的图像* |
| `<文件名>` | *(无参数)* | 可以使用外部文件的文件名调用 DOpusRT 以启动各种 Opus 文件。Opus 创建的默认文件类型关联使用此行为 - 例如，在自定义模式下将工具栏按钮拖到桌面时创建的 **.dcf** 文件（Opus 命令文件）。**dopusrt.exe** 将通过将文件名传递给 **dopusrt.exe** 来启动。 |
| 可以通过这种方式调用的文件类型有 **.dcf**（命令文件）、 **.dpf**（Opus 旧版本导出的配置文件）和 **.dop**（工具栏）。 |
| **示例：** | **dopusrt.exe C:\Commands\New文件窗口.dcf**<br><br>**                    ***- 执行导出命令文件中的命令** |