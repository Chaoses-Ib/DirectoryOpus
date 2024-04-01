# 高级选项

此页面包含被视为“高级”选项的列表。这些通常是晦涩的设置，大多数用户不需要了解，更不用说更改它们了。

每个选项都有一个名称和一个值。该值可以是布尔值（true/false）、数值、字符串或从下拉列表中选择。要编辑选项的值，请双击现有值或选择该选项并按 <kbd>F2</kbd>。当选项未设置为其默认值时，它将以粗体显示。

当您选择一个选项时，它的描述将显示在页面底部。用星号标记的项目是全局设置 - 它们影响计算机的所有用户。您可以通过选择它并单击底部的 **复位** 按钮来将其选项重置为其默认值。

如果您正在寻找一个特定的选项，则可以使用顶部的搜索字段按名称或描述进行搜索。如果您希望仅查看您已从默认值修改的设置，可以使用搜索字段右侧的 **隐藏未更改设置** 复选框。

<table>
<thead><tr><th>

**类别：行为**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**clipboard_datestamps**</td><td>
</td><td>
粘贴图像或文本数据从剪贴板到新文件时，使用诸如“Clipboard Image.bmp”和“Clipboard Text.txt”等名称，并根据需要添加数字后缀以使其唯一。打开此选项将在这些文件名开头添加YYYY-MM-DD HH-MM-SS日期时间戳。在粘贴和转换多个数据片段以及在标准的文件打开对话框中选择它们时，这有助于按顺序保存这些数据片段，否则这些对话框无法正确对名称进行排序。
</td></tr><tr><td>

**clipboard_text_encoding**</td><td>
</td><td>
指定粘贴文本从剪贴板到文件时要使用的默认文本编码。
</td></tr><tr><td>

**compress_collections**</td><td>
</td><td>

压缩[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)以节省磁盘空间。如果关闭，文件集合将被保存为未压缩的XML文件 - 如果一个集合中有很多文件，这会导致文件占用大量空间。
</td></tr><tr><td>

**config_backup_name**</td><td>
</td><td>

用于生成配置备份默认名称的模板。在执行备份时，您仍然可以手动编辑名称，但这会更改其初始名称。

模板支持`D#`、`T#`和`A#`前缀，用于日期和时间（如[此处](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.zh.md)所述）和环境变量。请注意，要使用日期和时间代码，您必须将它们括在`{}`中，例如`{D#yyyy-MM-dd}`。

（Opus 13.3.4及更高版本：）默认使用本地时间，但是如果您希望使用UTC，可以添加`UTC#`前缀（例如`{UTC#T#HH-mm}`）。
</td></tr><tr><td>

**dblclk_distance**</td><td>
</td><td>
鼠标光标移动以进行双击注册的最大距离（以像素为单位）。
</td></tr><tr><td>

**display_release_history**</td><td>
</td><td>
当打开此选项时，在安装新版本后首次使用Directory Opus时，帮助文件中的发布历史记录页面将自动打开。它帮助您了解新版本中的新功能、修复和其它更改。关闭该选项以防止发布历史页面自动出现。
</td></tr><tr><td>

**drag_distance**</td><td>
</td><td>
鼠标光标需要移动的像素距离才能启动拖放。如果您想完全禁用拖放，请将此设置设为0。
</td></tr><tr><td>

**find_extension_func**</td><td>
</td><td>

在Windows XP上，Opus注册了一个[搜索处理程序](http://msdn.microsoft.com/en-us/library/bb776834(v=vs.85).aspx) ，它允许您从开始菜单访问Opus查找功能。您可以使用此选项配置Opus响应搜索处理程序时运行的命令。如果未指定，则使用默认的[查找](/Manual/reference/command_reference/internal_commands/find.zh.md)命令。
</td></tr><tr><td>

**find_unique_collections**</td><td>
</td><td>

不要让同时执行的[查找](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md)操作对结果使用同一个集合。查找功能默认为将结果显示在*查找结果* [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)中。如果您并行运行两个或更多个查找操作，此选项会修改第二个及后续任务输出文件集合的名称以使其唯一，以便结果不会混在一起。
</td></tr><tr><td>

**flatview_folder_filters**</td><td>
</td><td>

启用在[平面视图](/Manual/basic_concepts/flat_view.zh.md)中过滤子文件夹。默认情况下，当文件列表在平面视图中时，快速过滤器（即由[过滤栏](/Manual/basic_concepts/searching_and_filtering/filter_bar.zh.md)设置的过滤器）不会应用于文件夹。原因是当一个文件夹从列表中过滤出来时，其所有内容也会自动被过滤出来，这可能会导致不想要的结果。当文件列表在平面视图模式时，过滤栏会显示一个复选框选项，让您打开或关闭文件夹过滤，您可以使用此选项控制该复选框的默认状态（也就是说，如果您通常希望快速视图过滤器也应用于平面视图中的文件夹和文件，请打开此选项。）
</td></tr><tr><td>

**go_up_always_back**</td><td>
</td><td>

`上移`命令通常重新读取父文件夹，即使您之前访问过它并且它位于历史记录列表中，您也可以添加 **返回** 参数（即**上移 返回**）以使Opus在可能的情况下使用历史记录（保留文件选择）访问父文件夹。如果打开此选项，则**上移**总是表现得好像指定了**返回**参数一样。
</td></tr><tr><td>

**image_locate_services**</td><td>
</td><td>

允许您配置`Image LOCATE`命令使用的图像定位服务。每一行都包含用于引用服务的关键字、等号和将在默认网络浏览器中打开的URL。插入代码`%lat%`和`%lon%`用于传递图像的纬度和经度。
</td></tr><tr><td>

**layout_string**</td><td>
</td><td>

此选项允许您定义从[布局](../layouts_and_styles/layouts.zh.md)页中放到桌面的[文件窗口布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md)的名称。您必须指定包含代码`%1`的字符串 - 此代码将被生成快捷方式中的布局名称替换。如果未为该选项指定任何内容，默认值为`布局 '%1'`。
</td></tr><tr><td>

**manual_sort_names**</td><td>
</td><td>

允许您定义附加的[手动排序](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.zh.md)顺序。Opus可以记住多个手动排序顺序，您可以轻松地在命名的顺序之间切换。例如，您可能有一个在工作中使用的手动排序顺序，另一个在家中使用。您必须在单独的行上输入每个名称。如果您没有指定任何名称，则将只会有一个未命名的手动排序顺序可用。


</td></tr><tr><td>

**navlock_warn_verbose**</td><td>
</td><td>

当导航锁打开时，在一边输入相对路径而另一边无法镜像会导致出现一个警告覆盖在文件列表中。默认情况下，当**navlock_warn_verbose**设置为**True**时，此警告很长，并解释您可以返回到之前的文件夹以使两边重新同步，还可以提供手动重新同步当前文件夹对或完全关闭导航锁的选项。如果您将**navlock_warn_verbose**设置为**False**，则会显示一条较短、较不醒目的消息。如果您已经了解导航锁的工作原理并已经多次阅读较长的消息，请切换到较短的消息。
</td></tr><tr><td>

**pinyin_support**</td><td>
</td><td>
Opus有一些拼音支持（一种使用西方键盘输入中文的方法）。默认情况下，如果Opus以中文运行，即时查找和过滤栏都支持拼音用于搜索/过滤。此选项允许您覆盖自动设置并明确启用或禁用拼音支持。
</td></tr><tr><td>

**powermode_singledrag**</td><td>
</td><td>

[增强模式](/Manual/basic_concepts/the_lister/view_modes.zh.md)文件列表默认具有持久选择 - 当您单击未选择的项目时，它会将其选中，但不会自动取消选择任何其它已选项目。通常，当您单击项目并将其拖出时，所有其它选定的文件也会一起拖动。当此选项打开时，如果您单击单个文件并将其向左或向右拖动，只有该文件将成为拖动的一部分 - 任何其它选定的文件都不会。
</td></tr><tr><td>

**powershell_exe**</td><td>
</td><td>
允许您指定要使用的默认PowerShell可执行文件。例如，您可能希望默认的PowerShell菜单项打开PowerShell 7而不是Windows PowerShell。
</td></tr><tr><td>

**rename_default_focus**</td><td>
</td><td>

选择[重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)对话框中默认获取输入焦点的字段 - *旧名称*或*新名称*字段。重命名脚本可以覆盖此设置。
</td></tr><tr><td>

**save_button_editor_pos**</td><td>
</td><td>

保存[命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md)对话框的默认位置。如果您打开此选项，Opus将在关闭时记住命令编辑器的放置，并在下次打开一个命令编辑器时使用该已保存位置。如果关闭，命令编辑器将居中显示在其父窗口上。
</td></tr><tr><td>

**searchfield_autostart**</td><td>
</td><td>
允许您控制停止从文件窗口搜索字段键入搜索后多久自动开始。如果设置为0，则使用[边输入文件边查找](/Manual/preferences/preferences_categories/filtering_and_sorting/find_as_you_type/README.zh.md)页面上为即时查找配置的值。
</td></tr><tr><td>

**scroll_lock**</td><td>
</td><td>

如果**滚动锁定**键打开，光标键将在不更改焦点项的情况下滚动文件列表。
</td></tr><tr><td>

**search_warn_nonindexed**</td><td>
</td><td>
当值为true时，如果您对未编制索引的文件夹使用Windows搜索，并且搜索花费了几秒钟，Opus将显示一个横幅警告，通知您搜索可能会很慢，因为该文件夹未编制索引。如果关闭，将不会显示警告。（这不会对Opus内置的查找文件功能产生任何影响。查找文件功能独立于Windows搜索索引，并且不会显示类似横幅。）
</td></tr><tr><td>

**setwallpaper_file**</td><td>
</td><td>

`属性 SETWALLPAPER`命令可用于将所选图像文件设置为桌面壁纸。默认情况下，选定的文件被复制到您的文档文件夹，但是您可以通过为此选项指定完整的路径和文件名来覆盖位置。指定的文件名必须以**.bmp**或（在Vista和更高版本中）**.jpg**结尾。
</td></tr><tr><td>

**single_click_rename**</td><td>
</td><td>

如果您启用了[单击模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/single-click_mode.zh.md)，并且文件列表在[详细信息模式](/Manual/basic_concepts/the_lister/view_modes.zh.md)中，并在[配置](../file_display_modes/details_mode.zh.md)中启用了整行选择，则通常无法使用鼠标启动[内联重命名](/Manual/file_operations/renaming_files/inline_rename.zh.md)，因为单击该行中的任何位置都会打开该项目。启用此选项后，您可以使用鼠标启动内联重命名 - 一旦通过悬停选择条目，您可以在该行上的任何位置（而不是文件名）单击以开始重命名。
</td></tr><tr><td>

**slow_dblclk_rename**</td><td>
</td><td>
将其设置为**False**以禁用标准功能，该功能使您可以通过“慢双击”（在双击时间之外单击已选中的文件或文件夹）进入内联重命名模式。如果禁用了慢双击重命名，您仍然可以使用**F2**键进入内联重命名模式。
</td></tr><tr><td>

**status_metadata_trigger**</td><td>
</td><td>

控制状态栏（如果显示所选或总媒体持续时间（时间长度））可能触发该数据的计算时间，如果文件列表中还没有其它内容触发它。

计算媒体持续时间包括单独打开和解析每个文件中的数据，这可能需要一些时间并占用磁盘或网络，特别是当有很多文件时。

如果已为文件列表中的一列（例如**持续时间**列）计算了持续时间，则该设置是可变的，因为状态栏将重新使用这些计算。该设置仅更改状态栏本身是否可以触发计算。

如果状态栏定义不包括任何[媒体持续时间代码](/Manual/reference/status_bar_codes/codes_for_music_and_video_duration.zh.md) -- 即 **{smp3}**或**{tmp3}** -- 那么该设置也是可变的，因为状态栏不会触发对其不感兴趣的数据的计算。

默认设置是**永不**，这意味着状态栏永远不会自行触发计算，并且仅在其它内容计算时显示持续时间信息。

选择**始终**设置意味着状态栏将在所有情况下触发持续时间计算。

选择**始终，平面视图和集合除外**设置意味着状态栏可以触发持续时间计算，但当[平面视图](/Manual/basic_concepts/flat_view.zh.md)启用时或处于[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)中时除外。平面视图和集合通常涉及大量文件，这使得它们成为最坏的情况。
</td></tr><tr><td>

**styles_update_previous**</td><td>
</td><td>

如果您对文件窗口的外观进行了更改（通过手动打开或关闭用户界面元素，或通过[文件窗口样式](/Manual/basic_concepts/the_lister/styles.zh.md)），则`配置样式`命令允许您将文件窗口恢复到其初始外观。如果您打开此选项，那么只要选择了新的文件窗口样式，就会更新“上一个”样式（因此从那时起，`配置样式=^prev`会将文件窗口重置为该样式，而不是其初始布局）。

</td></tr><tr><td>

**tab_click_nofocus**</td><td>
</td><td>

单击[文件夹标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md)使其出现在最前面通常会激活该文件列表并使其成为源。如果此选项打开，那么单击目标文件列表中的标签页将使源/目标状态保持不变。
</td></tr><tr><td>

**utility_panel_autoshrink**</td><td>
</td><td>

此设置可用于在执行查找、重复文件或同步操作后自动将实用程序面板缩小为仅显示其标题。单击设置以打开一个菜单，您可以在其中为每个操作打开或关闭自动缩小。
</td></tr><tr><td>

**wheel_acceleration**</td><td>
</td><td>

Opus通常在使用鼠标滚轮在文件列表中滚动时应用少量的加速，但是如果需要，您可以使用此选项禁用它。
</td></tr><tr><td>

**wordbreak_char_names**</td><td>
</td><td>

当编辑文件名（例如内联重命名）时，这允许您指定一个或多个将用作编辑字段中“单词断开”字符的字符。单词断开字符会影响在按**Ctrl+左**或**Ctrl+右**键时光标停止的位置。空格始终被视为单词断开。
</td></tr><tr><td>

**wordbreak_char_paths**</td><td>
</td><td>

当编辑路径（例如在[面包屑路径字段](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.zh.md)中）时，这允许您在编辑字段中配置其它单词断开字符。标准路径分隔符（**:/\\**)总被视为单词断开。
</td></tr><tr><td>

**wsl_distribution**</td><td>
</td><td>
如果您安装了多个WSL发行版，此选项允许您控制Opus使用哪个发行版来启动WSL命令。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：兼容性**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**convert_descriptions**</td><td>
</td><td>

将旧描述文件转换为*descript.ion*格式。除非您正在从Directory Opus的极旧版本迁移，否则您永远不需要设置此项。
</td></tr><tr><td>

**def_func_cd_sourcedir**</td><td>
</td><td>
从不指定当前目录的按钮启动程序时，使用当前源目录作为默认当前目录。出于安全原因，此类功能的默认设置是将当前目录设置为*C:\Windows\System32*目录。
</td></tr><tr><td>

**direct2d**</td><td>
</td><td>

控制Direct2D如何用于渲染UI的某些部分。Direct2D在某些地方被用来提供更好的性能或更好的质量渲染。

**正常**是默认选项，启用Direct2D并允许操作系统决定使用硬件（GPU）渲染还是软件（CPU）渲染。

如果认为GPU硬件或驱动程序有问题，并且想强制Direct2D在CPU上渲染所有内容，则可以选择**强制CPU渲染**。

可以选择**禁用**以防止使用Direct2D。

在撰写本文时，该选项影响进度对话框的速度图。
</td></tr><tr><td>

**dlldir_security**</td><td>
</td><td>

此选项在默认情况下启用，可防止Opus从当前工作目录加载DLL。这降低了“二进制植入”攻击的风险，当您在有人隐藏了恶意DLL的文件夹中打开照片或音乐等文件时，它可以诱使您的计算机运行不受信任的软件。

关闭此选项会降低您的安全性，但如果它导致问题，可能是由编写得很差的壳扩展或安装在您计算机上的其它第三方软件引起的，则可能需要关闭它。（此类软件通常只针对Windows资源管理器进行测试，后者传统上不使用Opus默认使用的更安全的模式。）

此选项仅影响Opus以及您从Opus启动的软件。它不是一个系统范围的设置（尽管如果您想更加安全，也可以进行一项设置；在网络上搜索CWDIllegalInDllSearch以了解更多信息）。

从可移植USB安装程序运行时无法修改此选项。
</td></tr><tr><td>

**dragdrop_async**</td><td>
</td><td>

当文件从另一个程序拖放到Opus时，Opus通常会在后台处理它们，以便其窗口保持响应。如果您从中拖动的程序支持Windows 用于异步拖放的API，那么这永远不是问题；但是，大量的程序不支持该API。

当**dragdrop_async**开启时，Opus将尝试在后台处理*所有*拖放，如果必须的话，它会打破规则，除非它检测到来自已知有此类问题的程序的拖放。如果关闭此选项，Opus将更加严格，并且仅为明确支持它的程序在后台处理拖放。

如果您在从某些程序将文件拖到Opus时遇到问题，请尝试关闭此选项，看看它是否可以提高兼容性。缺点是您有时可能不得不等到拖放完成之后才能继续使用您拖放到的窗口。
</td></tr><tr><td>

**flush_com_libraries**</td><td>
</td><td>

默认情况下，Opus在不再需要COM库时会主动要求COM库（通常是壳扩展DLL）卸载它们。这可能会导致组件在其仍在进程中运行代码时错误地表示可以卸载而导致崩溃。将此设置切换为**False**可以减少那些故障组件的问题。
</td></tr><tr><td>

**function_default_async**</td><td>
</td><td>

默认情况下，只包含一个命令的函数将[异步](/Manual/customize/creating_your_own_buttons/synchronous_and_asynchronous_functions.zh.md)运行，而包含两个或更多个命令的函数将[同步](/Manual/customize/creating_your_own_buttons/synchronous_and_asynchronous_functions.zh.md)运行。此选项允许您覆盖此行为，并默认使所有函数（单个或多个命令）异步运行。
</td></tr><tr><td>

**global_explorer_replacement**</td><td>
全局</td><td>

[资源管理器替代](/Manual/basic_concepts/explorer_replacement.zh.md)模式通常是每个用户的设置，但是如果您打开此选项，则资源管理器替代模式设置将对机器的所有用户都是全局的。这可能会提高Opus拦截某些对资源管理器调用的能力，但通常情况下您会将其关闭。
</td></tr><tr><td>

**mp3_custom_comments**</td><td>
</td><td>

MP3 ID3v2标签用于注释没有严格的定义，而不同的第三方工具通常使用自己的此标签的格式。当使用[元数据面板](/Manual/basic_concepts/the_lister/metadata_pane.zh.md)时，您可以使用此选项使Opus使用指定的描述来撰写COMM标签，以便与这些工具兼容。例如，MediaMonkey将COMM标签标记为**Songs-DB_Custom1**，因此您将这个字符串放入**mp3_custom_comments**值中，以使Opus MP3注释与MediaMonkey兼容。如果您使用多个工具，可以添加多个注释描述，每行一个，并且Opus将为每个描述撰写一个单独的COMM标签。


</td></tr><tr><td>

**no_async_icons**</td><td>
</td><td>

不应该异步检索图标的文件类型。通常，Opus在后台线程上检索文件图标以获得更好的性能，但我们偶尔发现某些文件类型的图标无法在后台成功生成。多个文件扩展名应该用分号分隔。请注意，以下扩展名会自动阻止在后台提取图标： **.msg;.oft;.xnk**
</td></tr><tr><td>

**patch_edit_control_dpi**</td><td>
</td><td>
允许您禁用修复高DPI下垂直对齐的Edit控件补丁。如果补丁程序导致未来版本的Windows出现问题，则使用此项。
</td></tr><tr><td>

**patch_text_apis**</td><td>
</td><td>

将其设置为*True*（默认值），Opus将使用一些Windows文本渲染和测量API进行修补，旨在使其使用一致的字体字距。这应该使字符间距看起来更好和更一致。它还应该防止拉丁字符的字符串在从末尾添加或删除非拉丁字符时以不同的方式间距，这可能导致文本溢出其边界。但是，由于此设置修改了操作系统API（仅在dopus.exe中），它可能会导致在Opus中运行的第三方代码出现兼容性问题。如果您在Opus中看到文本渲染或布局问题，请查看关闭此项是否有帮助，并请通过Directory Opus技术支持论坛报告您的发现。
</td></tr><tr><td>

**regex_style**</td><td>
</td><td>

设置Opus使用的[正则表达式](/Manual/reference/wildcard_reference/regular_expression_syntax.zh.md)的样式。默认值为*TR1 ECMAScript*，但您可以更改此值以恢复旧版Opus支持的原始正则表达式样式。如果您有大量已保存的[重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)预设由于某种原因不适用于新版本的正则表达式，您可能只想这样做。
</td></tr><tr><td>

**zip_large_file_support**</td><td>
</td><td>

启用对大型Zip文件提供支持。大型Zip文件支持单个项目和大于4 GB的档案，以及档案中超过65536个单独的项目。大型Zip支持在默认情况下启用，但如果您需要保持与旧版档案的兼容性，则可以关闭此选项。即使此选项关闭，Opus也会始终读取大型Zip文件 - 它仅仅控制Opus创建的档案类型。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：外观**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**collection_icon_default**</td><td>
</td><td>

对于不匹配任何其它类型的集合的单个文件集合，自定义默认图标。

此设置更改默认图标。您还可以通过其属性对话框更改特定集合的图标。

您可以指定独立的.ICO文件的路径（例如`C:\MyIcon.ico`），或使用数字ID指定.EXE和.DLL文件中的图标以选择特定图标（例如`/system/imageres.dll,101`）。
</td></tr><tr><td>

**collection_icon_find**</td><td>
</td><td>

类似于**collection_icon_default**，但针对为查找结果和搜索查询生成的集合特定。
</td></tr><tr><td>

**collection_icon_flickr**</td><td>
</td><td>

类似于**collection_icon_default**，但针对为Flickr同步生成的集合特定。
</td></tr><tr><td>

**collection_icon_marked**</td><td>
</td><td>

类似于**collection_icon_default**，但针对通过在查看器中标记图像生成的标记图片集合特定。
</td></tr><tr><td>

**collections_icon**</td><td>
</td><td>

[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)根文件夹的自定义图标。

这仅影响实际的“文件集合”根文件夹。上面其它设置涵盖各种类型的单个集合。

您可以指定独立的.ICO文件的路径（例如`C:\MyIcon.ico`），或使用数字ID指定.EXE和.DLL文件中的图标以选择特定图标（例如`/system/imageres.dll,101`）。
</td></tr><tr><td>

**context_menu_icon_set**</td><td>
</td><td>

某些上下文菜单包含Opus自动生成的项目，在这些项目中，您没有机会更改图标的大小或样式，除非将图标集移动到列表顶部并影响*所有*工具栏和菜单图标。由于您可能希望在上下文菜单中使用比在其它任何地方都小的图标集，因此此设置允许您指定另一个集以代替正常集。Opus在生成用于在压缩包中添加和提取的上下文菜单项时将使用此设置。请注意，这仅适用于在Opus内显示菜单时；资源管理器中的类似菜单一开始不使用图标集。

名称应与图标集的XML“name”属性匹配，*不*匹配其“display_name”。例如，如果图标集使用`<iconset name="flat_small"> ... <display_name>Small Icon Set (Flat)</display_name>`定义，那么您应在该设置中键入“flat_small”，而不是“Small Icon Set (Flat)”。
</td></tr><tr><td>

**custom_network_folder_icons**</td><td>
</td><td>

如果设置为 *True*，则当位于网络驱动器上时，可以在位置字段和文件夹标签页中显示单独自定义的文件夹图标。（在本地驱动器上，以及在文件列表本身中，自定义文件夹图标始终受支持，受**[配置/文件夹](../folders/README.zh.md)**下的**显示通用图标...**设置的约束。）

如果您有指向非常慢或无法访问的网络驱动器的文件夹标签页，打开此项可能会导致速度变慢，甚至暂时冻结。自定义文件夹图标通常通过文件夹的“属性”对话框进行配置，但是Windows隐藏了网络文件夹的选项，这可能出于性能原因，或者是因为您需要确保指定的图标路径对所有网络客户端都可访问。您仍可以手动创建自定义图标元数据，或将本地自定义文件夹复制到网络驱动器。因此，在网络驱动器上拥有自定义文件夹图标是可能的，但这很少见，并且只有当您使用它们时才应打开此项。
</td></tr><tr><td>

**glass_status_bar**</td><td>
</td><td>

如果设置为 *True*，则使用Windows的“glass”效果绘制状态栏及其背景。这在Windows 7上看起来不错，但在更新的Windows版本中却毫无意义。

除非在系统范围内启用glass（即启用桌面窗口合成），并且在**配置/显示/状态栏**下打开了**将状态栏保留在文件窗口的底部**，否则此设置无效。
</td></tr><tr><td>

**gloss_and_gradients**</td><td>
</td><td>

启用各种用户界面元素中的光泽和渐变效果。如果您更喜欢更平坦、更单调的外观，请关闭此项。

如果设置为*自动*，则在Windows 8或更高版本上选择平坦简单的外观，在Windows 7上选择具有渐变的光泽外观。


</td></tr><tr><td>

**grid_lines_first_last**</td><td>
</td><td>

更改水平网格线在文件列表中的绘制方式。这主要是为了帮助在视觉上将文件列表列标题与它下面的文件和文件夹分开，因为有些Windows版本绘制标题时没有下边缘，并且背景颜色与它下面的所有内容相同。

如果将其设置为**第一**或**两者**并带有实心网格线，则交替模式从第一个项目开始，而不是从第二个项目开始。如果将其设置为**第一**或**两者**并带有细网格线，则在第一个项目之前（就在列标题下面）绘制额外的网格线（但这仅在文件列表使用视觉样式时，并且行间距为0或1）。

将此选项设置为**最后**或**两者**并带有细网格线，将在最后一个项目之后添加额外的网格线，而不是跳过。**最后**选项对实心网格线没有影响。

在所有情况下，此设置对组标题下的项目没有影响，因为组标题已经有自己的线。
</td></tr><tr><td>

**no_contextmenu_fix**</td><td>
</td><td>

如果为[工具栏](../toolbars/toolbar_appearance.zh.md)选择“Office 2003”风格，Opus必须执行一些操作来使所有者绘制的第三方上下文菜单扩展看起来不错。如果您发现Opus的魔法还不够好，您可以使用此选项禁用它。
</td></tr><tr><td>

**progress_smoothing**</td><td>
</td><td>
在Vista及以上版本中平滑进度条更新。关闭以获得即时跳跃的无延迟进度条当更新时。
</td></tr><tr><td>

**resize_grips**</td><td>
</td><td>
默认情况下，为了提高外观（尤其是在带有内联状态栏的双水平模式下），文件窗口没有可见的调整手柄。如果您愿意，可以使用此选项重新打开手柄。
</td></tr><tr><td>

**thumb_48x48_icons**</td><td>
</td><td>

启用为缩略图和平铺使用48x48图标。这样做会有取舍：

- 如果关闭此设置，则既没有256x256版本也没有32x32版本图标会显得很难看。
- 如果开启此设置，既没有256x256版本也没有48x48版本图标会显得很难看。32x32图标比48x48图标常见得多，因此该设置默认关闭。

（确切的图标大小因系统DPI设置而异。此处使用的尺寸适用于标准DPI。）

每个图标可以包含其不同尺寸的不同版本。无论此设置如何，Opus始终首选具有它们的256x256高质量图标版本。对于没有256x256版本的图标，如果设置关闭，Opus会请求32x32版本；如果设置打开，Opus会请求48x48版本。

当图标不包含任何请求的大小时，将选择其其它大小之一并缩放以适合。这是由Windows本身完成的，并且缩放不是高质量的，调整大小的图标变得模糊和混乱。Windows不会说出哪些尺寸的图标可以缩放，也不会指示图标何时必须缩放以适应请求的大小，因此结果的质量取决于请求的大小，并且某些图标会以任何方式显示得很差。

（此选项会影响类似于.EXE文件的内容的图标。它不会影响实际的.ICO文件，因为Opus能够为它们生成缩略图而不会出现这些问题和妥协。）
</td></tr><tr><td>

**window_corners**</td><td>
</td><td>

允许您覆盖操作系统窗口角的默认样式。“自动”使用您的Windows版本的标准。您还可以选择正方形角和两种大小的圆角。

它还会影响操作系统围绕活动窗口绘制的阴影强度。

（仅在Windows 11或更高版本中可用。）
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：文件系统**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**copy_allow_delegation**</td><td>
</td><td>

如果**True**，允许Opus向Windows委派文件复制方式的详细信息。

Windows提供了一个非常高级别的文件复制API，它以深奥且未记录的方式进行优化，并且也是设备制造商倾向于针对其硬件和驱动程序进行测试和优化的API。对于性能和兼容性，您通常无法击败此API；充其量，您可以与其相等。

Opus还拥有自己的自定义文件复制代码，它在稍低级别的工作，并且至关重要的是，在并非简单文件到文件复制的情况下。此自定义代码通常与其最高级别的API速度相同，但有些情况下它会更慢（例如，对于对缓冲大小或其它参数高度敏感的特定设备或网络配置）。

默认情况下，Opus对普通的文件到文件复制使用非常高级别的API。在无法使用该API的情况下，Opus会自动采用其自己的自定义代码。这些情况包括将内容复制到或从压缩包和FTP网站，在保留稀疏数据的情况下复制，以及拆分和加入文件。

如果您将**copy_allow_delegation**设置为**False**，Opus将始终使用其自定义文件复制代码，即使在不需要使用的情况下也是如此。在某些罕见情况下，出于某种原因Windows文件复制API较慢，或者您希望强制使用非缓冲I/O时，您可能需要这样做。一般情况下，我们不建议您修改此设置。

`Copy DELEGATE`参数可用于覆盖单个按钮、热键等的此设置。
</td></tr><tr><td>

**copy_buffer_size**</td><td>
</td><td>

自定义文件复制代码使用的缓冲区大小。单位可以是KB、MB或GB。如果未指定单位，则默认为KB。

这指定了Opus在使用自己的自定义代码[复制文件](/Manual/file_operations/copying_moving_and_deleting_files/README.zh.md)时，一次读写的数据量。尽管这并不重要，但某些USB设备或网络似乎对复制缓冲区的大小很敏感。如果您发现复制的速度或可靠性远低于预期，请尝试增加或减少缓冲区大小。

`Copy BUFSIZE`命令可用于覆盖单个按钮、热键等的此设置。

此缓冲区是对文件系统、硬件等提供的任何缓冲区的补充；它与由**copy_nonbufferio_threshold**设置控制的非缓冲IO模式无关。

在**copy_allow_delegation**为**True**的通常情况下，**copy_buffer_size**和**copy_nonbufferio_threshold**设置对正常的文件到文件复制没有影响，但仍会影响特殊情况，例如拆分/加入文件、从压缩包中复制等。
</td></tr><tr><td>

**copy_nonbufferio_threshold**</td><td>
</td><td>

文件大小阈值，高于该阈值时，使用自定义文件复制代码进行的到或来自本地设备的复制将在非缓冲模式下执行。非缓冲模式绕过了Windows提供的文件系统缓冲区。单位可以是KB、MB或GB。如果未指定单位，则默认为MB。

对于非常大的文件，以非缓冲模式复制可以提高内存效率、复制速度和UI响应速度。另一方面，非缓冲模式可能会减慢较小文件或某些设备的速度。在极少数情况下，非缓冲模式可能根本无法工作（例如，如果您有报告其扇区大小错误的设备）。

将值设置为0（零）以禁用非缓冲模式。出于兼容性原因，它在默认情况下被禁用。如果您希望启用它，我们建议1 MB是一个很好的起始值。

`Copy NONBUFIO`命令可用于覆盖单个按钮、热键等的此设置。

在**copy_allow_delegation**为**True**的通常情况下，**copy_buffer_size**和**copy_nonbufferio_threshold**设置对正常的文件到文件复制没有影响，但仍会影响特殊情况，例如拆分/加入文件、从压缩包中复制等。
</td></tr><tr><td>

**dos_automap_unc_paths**</td><td>
</td><td>

在[MS-DOS批处理命令](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.zh.md)中为UNC路径自动创建驱动器号映射。这使您可以直接从UNC路径在网络驱动器上运行DOS批处理脚本。
</td></tr><tr><td>

**move_netshare_semantics**</td><td>
</td><td>

移动文件夹时的PGP Netshare特殊处理。与文件相比，当移动文件夹时，PGP Netshare的行为不同 - 如果您发现将文件夹移动到受Netshare保护的位置失败，请打开此选项。
</td></tr><tr><td>

**network_errors**</td><td>
全局</td><td>

指定表示网络身份验证错误的错误代码。某些网络文件系统在用户名/密码身份验证错误的情况下返回未记录的错误代码 - 如果您发现尝试连接到网络驱动器时只会收到错误对话框，您应该注意错误代码并将其添加到此选项中。当Opus接收到该错误代码时，它将将其视为身份验证失败，并提示您输入凭据以访问资源。您可以通过分号分隔多个错误代码来指定它们（例如**50;1003;1245**）。
</td></tr><tr><td>

**no_copy_dir_dates**</td><td>
</td><td>
禁用复制文件夹时间戳。仅在复制时保留文件的时间戳；作为复制操作的一部分创建的文件夹将具有当前时间和日期。
</td></tr><tr><td>

**remember_net_paths**</td><td>
</td><td>

Opus通常记住在系统文件打开或保存对话框中使用的上一个路径（例如，当您使用[配置备份或还原](../../backing_up_and_restoring_preferences.zh.md)功能时），但出于性能原因，它不会记住网络路径。如果您希望Opus也记住网络路径，请打开此选项。
</td></tr><tr><td>

**size_on_disk_thorough**</td><td>
</td><td>

默认情况下关闭。如果打开，文件夹大小计算将显着变慢，但当使用晦涩的NTFS压缩模式时，Opus将在“磁盘大小”列中显示更准确的信息。

这不会影响诸如Zip压缩包和其它非文件系统压缩方法之类的内容报告的大小。类似地，对于标准NTFS压缩模式（例如您可以通过文件的属性对话框打开的模式）报告的大小也不会受到影响。区别在于只能通过Windows compact.exe命令设置的不寻常的NTFS压缩模式，例如/EXE:LZX。Windows中的一个bug意味着用这些模式压缩的文件被错误地报告为未压缩。没有办法知道这些压缩模式是否正在使用，正确报告其磁盘上的大小值的唯一方法是对*每个文件*执行附加查询。这个额外的查询速度非常慢，尤其是在网络驱动器上，并且在重新读取文件夹时，操作系统不会缓存数据。

我们建议关闭此设置，除非您确实需要更准确的信息。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：FTP**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**ftp_copy_buffer_size**</td><td>
</td><td>
FTP复制缓冲区大小（以字节为单位）。这定义了通过FTP传输文件时使用的缓冲区大小。您通常不需要更改此设置。
</td></tr><tr><td>

**ftp_dblclk_cache_time**</td><td>
</td><td>
从[FTP](/Manual/ftp/README.zh.md)站点双击文件进行缓存的时间（以分钟为单位）。当您双击一个文件在FTP站点上打开它时，Opus会下载该文件并将其保存在一个临时文件夹中。如果您在指定的时间内再次双击同一文件，那么已经下载的文件将被用来保存再次下载文件。默认情况下，将其设置为0，这意味着文件不会自动缓存以双击。
</td></tr><tr><td>

**ftp_do_not_cache**</td><td>
</td><td>

通常，[FTP](/Manual/ftp/README.zh.md)系统会缓存远程站点的目录列表以提高性能。如果您想强制在您每次在FTP站点上更改文件夹时刷新远程目录，请打开此选项。
</td></tr><tr><td>

**ftp_no_case_sensitive**</td><td>
</td><td>

FTP站点通常区分大小写（例如，名为*TEST.TXT*的文件不同于名为*test.txt*的文件）。设置此选项以禁用FTP网站的大小写敏感性。
</td></tr><tr><td>

**ftp_no_pasv_change**</td><td>
</td><td>
如果Opus检测到有非路由地址指定为被动（PASV）FTP连接的结果，它将尝试将其更正为该站点的路由地址。如果您打开此选项，那么Opus将尝试使用指定的非路由地址，这只有在FTP服务器与客户端计算机在同一网络上时才会成功。
</td></tr><tr><td>

**ftp_ssl_verbose**</td><td>
</td><td>
导致FTP日志在SSL连接期间显示扩展的输出。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：图像格式**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
Description
</td></tr><tr><td>

**amiga_icon_borders**</td><td>
</td><td>
在缩略图模式下在Amiga图标周围显示边框。
</td></tr><tr><td>

**amiga_icon_palette**</td><td>
</td><td>
显示旧版Amiga图标时使用的调色板。
</td></tr><tr><td>

**clipboard_image_paste**</td><td>
</td><td>

如果您在剪贴板中有一个图像（例如通过PrtScn键）并粘贴到文件夹中，Opus会将剪贴板图像保存为一个文件。此设置更改了将使用的图像格式：JPG、PNG、BMP或GIF。

您还可以设置<kbd>Ctrl+V</kbd>热键运行`Clipboard PASTE AS=ask`，以便在您将图像粘贴到文件夹时让Opus提示您图像格式（和文件名）。在这种情况下，此设置确定默认选定的格式。
</td></tr><tr><td>

**clipboard_image_paste_dpi**</td><td>
</td><td>
当打开，粘贴剪贴板图像数据到一个文件（通过按 <kbd>Ctrl+V</kbd> 在一个文件窗口）将自动缩放它以补偿系统DPI。
</td></tr><tr><td>

**psd_image_preference**</td><td>
</td><td>

Photoshop PSD文件最多可以有三个嵌入图像：一个带有有损压缩的不透明/alpha数据的小（164x164）缩略图；一个全尺寸、压缩的预览图像，存储在一个无损格式，可以包含不透明/alpha数据；最后是Photoshop内部格式的全层图像数据。（Opus不会解码分层数据，除了Photoshop本身之外，其它很少有东西能够渲染它。）


默认情况下，Opus将缩略图用于小缩略图，并将全尺寸预览图像用于查看器。该设置允许您覆盖此设置，以便在缩略图和查看器中使用一个图像或另一个图像。

如果您希望Opus显示大于164x164的PSD缩略图，或带有不透明度/alpha数据，请选择使用预览图像作为查看器和缩略图的选项。

但是，一些PSD文件没有有效的预览图像，因此还有一个选项是永远不使用预览图像，即使在查看器中也是如此，始终使用小缩略图。PSD是否包含平面预览图像取决于它是如何从Photoshop中保存的。“最大化兼容性”或类似的选项应打开以包含预览图像。在Photoshop CC 2015.5.0中，该选项位于配置/文件处理”下。在某些情况下，如果没有“真实”预览图像，将会有一个由Photoshop编写的带有文本的黑白占位符，告诉您没有预览图像。不幸的是，某些版本的Photoshop在某些情况下会写入一个损坏的占位符图像。（数据格式良好，但它所代表的图像却不是。在任何一种情况下，对于Opus来说，很难检测到是否存在“真实”预览图像，或者仅仅是一个占位符，因为两者都只是被编码到与真实预览图像完全相同的文件部分中的不同的像素数据。）如果无法更改工作流程并导致PSD文件预览图像丢失或损坏，您可以告诉Opus始终使用小缩略图，即使在查看器中也是如此，这样您至少可以大致了解每个文件的样貌。
</td></tr><tr><td>

**tiff_assume_alpha**</td><td>
</td><td>
假设未指定其含义的文件中TIFF图像中的第4通道是（非乘）alpha。关闭此选项后，32位TIFF图像必须指定它包含一个有效的alpha通道，Opus才能将其视为有效。
</td></tr><tr><td>

**tiff_max_doc_metadata**</td><td>
</td><td>
Opus将尝试从中提取文档元数据的TIFF图像的最大大小（以兆字节为单位）。这可以防止出现非常大的TIFF图片，例如，由Photoshop保存的图片。
</td></tr><tr><td>

**use_color_management**</td><td>
</td><td>
加载图像时使用色彩管理。如果启用，Opus将检查图像文件是否包含色彩配置文件，如果包含，它将使用您指定的ICC文件（或默认sRGB配置文件）来更准确地渲染图像。目前，这只用于JPEG和PNG图像。
</td></tr><tr><td>

**viewer_disable_internal**</td><td>
</td><td>
允许您在查看器和预览窗格中禁用内置图像格式。不影响查看器插件（这些插件可以直接禁用）；事实上，目的是允许您使用插件和第三方组件覆盖内部查看器，而它们自己无法做到这一点（通常是预览处理程序和ActiveX控件，它们对Opus一无所知）。例如，您可能希望将TIFF查看器转移到处理多页TIFF的第三方ActiveX控件。该设置是一个字符串，列出您要禁用的图像类型。将它设置为**tiff**将禁用内部TIFF查看器。将其设置为**JPG,PNG**将禁用内部JPG和PNG查看器。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：信息显示**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**custom_date_format**</td><td>
</td><td>

Opus通常在显示日期（例如，在文件窗口的日期列中）时使用系统（或当前区域设置）定义的日期格式。此设置允许您覆盖它并指定您自己的自定义格式。

有关日期和时间格式的信息，请参见[日期和时间代码](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.zh.md)页面。
</td></tr><tr><td>

**custom_date_format_long**</td><td>
</td><td>

类似于**custom_date_format**，但用于使用较长（较详细）的日期格式的地方。在许多地方都不会使用较长的日期格式，因此如果不确定，**custom_date_format**可能是您想要的内容。
</td></tr><tr><td>

**custom_time_format**</td><td>
</td><td>

Opus通常在显示时间（例如，在文件窗口的日期/时间列中）时使用系统（或当前区域设置）定义的时间格式。此设置允许您覆盖它并指定您自己的自定义格式。

有关日期和时间格式的信息，请参见[日期和时间代码](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.zh.md)页面。
</td></tr><tr><td>

**deffmt_cloud_availability**</td><td>
</td><td>

防止自动将**Availability**列添加到**Cloud Storage**文件夹格式中。

当您保存新的默认文件夹格式并选择替换所有现有格式的选项时，一些格式会自动添加额外列。在大多数情况下，这些列很重要，但有些可以通过此类选项进行覆盖。
</td></tr><tr><td>

**deffmt_cloud_status**</td><td>
</td><td>

防止自动将**Status** (**状态图标**) 列添加到**Cloud Storage**文件夹格式中。（参见上文所述的**deffmt_cloud_availability**。）
</td></tr><tr><td>

**desc_show_info**</td><td>
</td><td>

对于每个文件，**Description**列通常显示：

- 元数据摘要。（例如，图片类型和尺寸、音频编解码器和比特率。）
- 用户自定义描述（如果有）。（这可以通过默认工具栏上的**属性，说明**命令设置。某些文件类型还允许在其标签中自定义描述/注释。）
- 目标路径（如果文件是快捷方式或链接）。此选项允许您从“说明”列中删除用户定义的说明和/或目标。例如，如果您添加了单独的**用户说明**和**目标**列，则您可能只想将元数据摘要保留在**说明**列中。
</td></tr><tr><td>

**display_folder_extensions**</td><td>
</td><td>

如果启用此选项，则文件夹将被视为具有扩展名（后缀）仅用于显示目的（即在*名称*和*扩展名*列中）。例如，名为“Hello.World”的文件夹将在扩展名列中显示“World”，而不是不显示任何内容。
</td></tr><tr><td>

**file_size_units**</td><td>
</td><td>

指定在显示文件大小和磁盘空间时要使用的单位。传统形式是使用二进制单位（2^10为基数）和“十进制”前缀（1 KB = 1024 字节）。您还可以选择使用十进制单位（10^3为基数）（1 KB = 1000 字节）或二进制单位（1 KiB = 1024 字节）。有关详细信息，请参见[此Wikipedia页面](http://en.wikipedia.org/wiki/Binary_prefix)。
</td></tr><tr><td>

**graphs_separate_files_dirs**</td><td>
</td><td>
在文件列表中显示的条形图（相对大小、相对年龄）分别计算文件和文件夹。如果您关闭此选项，它们将计算所有项目。
</td></tr><tr><td>

**group_column_maxwidth**</td><td>
</td><td>

指定*组*列的最大宽度。当文件列表列被设置为自动大小时，此选项可以防止*组*列增长超过指定像素数。
</td></tr><tr><td>

**image_res_units**</td><td>
</td><td>

用于与图像分辨率相关的列（*分辨率（X），分辨率（Y）*）的单位。如果不设置，则每个图像文件本身指定单位，因此在任何一个目录中都可以混合使用英寸和厘米 - 设置此选项将覆盖图像并始终显示一致的单位。
</td></tr><tr><td>

**image_size_units**</td><td>
</td><td>

用于与图像大小相关的列（*物理宽度，物理高度，物理大小*）的单位。如果不设置，则每个图像文件本身指定单位，因此在任何一个目录中都可以混合使用英寸和厘米 - 设置此选项将覆盖图像并始终显示一致的单位。
</td></tr><tr><td>

**multipart_extensions**</td><td>
</td><td>

“多部分文件扩展名”是一种由多个部分组成的文件扩展名，这些部分由点分隔。例如，在Unix世界中**.tar.gz**文件非常普遍。在许多情况下（重命名、排序等），将此整个字符串视为文件扩展名更有意义，而不仅仅是**.gz**，就像Windows上的标准一样。Opus会自动执行此操作以进行多种压缩包格式，而**multipart_extensions**选项还允许您添加您自己的自定义扩展名。每行输入一个扩展名。
</td></tr><tr><td>

**name_group_high_pri_chars**</td><td>
</td><td>

按文件名[分组](/Manual/basic_concepts/sorting_and_grouping/README.zh.md)文件列表时，以这些字符开头的文件将被放置在列表顶部的“高优先级”组中。通常，以非字母字符或数字开头的文件将被放置在*未指定*组中，但您可以使用此选项（例如）将以**！**或**\#**开头的文件放置在单独的组中。
</td></tr><tr><td>

**show_sharing_overlays**</td><td>
</td><td>

Windows 7去掉了共享文件夹的图标覆盖（![](/Manual/images/media/sharing_overlay.png)），但很多人喜欢这项功能，所以Opus用自己的功能代替了它。如果您不想看到这些覆盖，请关闭此选项。如果通过[文件列表列/图标](/Manual/preferences/preferences_categories/file_display_columns/icons.zh.md)配置页面上的*显示快捷方式箭头和其它图标覆盖*选项完全关闭了覆盖，此选项将不起作用。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：限制**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**context_menu_max_files**</td><td>
</td><td>

由于为大量文件生成上下文菜单可能需要相当长的时间，因此当您右键单击时选择了超过定义数量的文件时，Opus会显示确认消息。限制默认设置为1000，但您可以更改此设置或将其设置为**0**，以便完全不确认。
</td></tr><tr><td>

**everything_max_results**</td><td>
</td><td>
设置Everything搜索可以返回的搜索结果数量限制。
</td></tr><tr><td>

**long_operation_notify_time**</td><td>
</td><td>
如果阻止UI线程的操作花费的时间超过指定时间，Opus将显示一个通知对话框，允许您取消该操作。
</td></tr><tr><td>

**max_folder_thumb_time**</td><td>
</td><td>
指定Opus生成文件夹缩略图时花费的最大时间（以毫秒为单位）。
</td></tr><tr><td>

**max_md5_file_size**</td><td>
</td><td>
指定文件列表中显示校验和列之一时Opus计算其散列的最大文件大小（以千字节为单位）。如果文件大于此大小，则仍可以使用`GetSizes HASH`命令手动生成其校验和。

**特殊值：**

- **0** - 忽略文件大小并始终自动计算文件哈希。
- **1** - 忽略文件大小，切勿自动计算文件哈希。

（此设置的名称具有历史意义，它适用于所有哈希 - 不仅仅是MD5。）
</td></tr><tr><td>

**max_thumbnail_mem_size**</td><td>
</td><td>
每个文件列表的内存中缩略图的最大内存（以兆字节为单位）。Opus将丢弃视外缩略图，以将每个文件列表的缩略图的内存使用量保持在指定大小以下。如果设置为0，则没有限制。
</td></tr><tr><td>

**max_thumbnail_size**</td><td>
</td><td>
Opus生成缩略图的最大像素大小（宽度和高度）。较大的缩略图需要更多内存。这控制了可以在配置中的[缩略图](../file_display_modes/thumbnails_mode/README.zh.md)页面上选择的最大大小缩略图，还可以通过[缩略图大小](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/README.zh.md)滑块。
</td></tr><tr><td>

**suggestion_popup_lines**</td><td>
</td><td>
配置弹出式建议列表中一次显示多少行。
</td></tr><tr><td>

**zip_dblclk_cache_time**</td><td>
</td><td>
从ZIP文件内双击文件的缓存时间（以分钟为单位）。当您双击一个文件从一个ZIP文件中打开它时，Opus会提取该文件（并且可能还有其它文件，这取决于[压缩包选项](../zip_and_other_archives/archive_options.zh.md)配置页面上的自动提取选项），并将其保存到一个临时文件夹。如果您在指定的时间内再次双击同一文件，那么已经提取的文件将被用来保存再次提取的文件。默认情况下，它设置为0，这意味着不会自动缓存文件以双击。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：故障排除**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**clipboard_change_delay**</td><td>
</td><td>
处理剪贴板更改事件之前的延迟（以毫秒为单位）。如果您发现某些软件（例如Microsoft Office）在Opus运行时修改剪贴板时有问题，您可能需要增加此设置。
</td></tr><tr><td>

**collection_change_delay**</td><td>
</td><td>
在[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)中处理外部删除/重命名操作之前的延迟（以毫秒为单位）。如果您发现文件在其它程序（例如Word）中编辑时从文件集合中消失，您可能需要增加此设置。
</td></tr><tr><td>

**context_menu_debug**</td><td>
</td><td>
输出上下文菜单扩展的调试信息。有关调试上下文菜单问题的更多信息，请参见[常见问题解答](https://resource.dopus.com/t/crash-exit-or-high-cpu-when-right-clicking-certain-files/1335)。Directory Opus Light的用户可以设置注册表值**HKEY_CURRENT_USER\SOFTWARE\GPSoftware\Directory Opus\ContextMenuDebug** (DWORD) = 1作为此选项的替代方案。
</td></tr><tr><td>

**crash_debug_button**</td><td>
</td><td>
当打开时，会在Opus崩溃对话框中添加一个“调试”按钮，允许您调用正常的Windows崩溃行为。如果安装了即时调试器，这将允许您在当前状态下调试进程。此选项仅在您是正在开发插件或 Shell 扩展的开发人员时应打开；它不太可能对其它任何人有用。


</td></tr><tr><td>

**crash_handler**</td><td>
</td><td>

Opus包括一个自定义崩溃处理程序，旨在提供有关崩溃的信息，GP Software可以使用这些信息来追踪原因。它保存了进程内存部分的日志（“转储”），您可以使用帮助菜单中的内置崩溃提交工具自动上传这些日志。崩溃处理程序部分由一个单独的进程（dopusrt.exe）管理，Opus自动启动此进程（并且如果它被终止，它将自动重新启动）。

如果您出于某种原因不想使用崩溃处理程序（例如，如果它自己导致了问题），请将此标志设置为**False**。
</td></tr><tr><td>

**crash_log_memory**</td><td>
</td><td>
当打开时，自动生成的崩溃日志（也称为“崩溃转储”）将包括进程中的所有内存。当诊断问题时，这可以使它们更有用，但也大大增加了它们的文件大小和包含私有数据的可能性。除非技术支持要求，否则您不应打开此设置。
</td></tr><tr><td>

**debug_icon_data**</td><td>
</td><td>
您通常不应该修改此设置。技术支持可能要求您启用它以帮助诊断由第三方组件生成的图标的问题。
</td></tr><tr><td>

**mixed_dpi_mitigations**</td><td>
</td><td>

Windows中有大量的错误是由使用具有不同DPI的多个显示器触发（不仅仅是高DPI显示器，而是只有一个屏幕且它们未全部设置为相同的缩放系数）。其中一些Windows错误也可以通过更改DPI而不是重新启动来触发。

**mixed_dpi_mitigations**设置控制Opus用于尝试使Windows在使用多DPI显示器时正常运行的某些解决方法。不幸的是，这些缓解措施本身可能会在某些计算机上引起问题，而解决这些问题则在其它计算机上引起问题。如果关闭缓解措施，则Windows错误的主要症状是弹出菜单和工具提示在错误的位置打开，并且非常大或小。当缓解措施打开时，性能会受到很小的影响，并且如果出现问题，当弹出菜单或工具提示打开时屏幕闪烁的可能性，或其它意外的视觉故障。

当设置为*自动*时，Opus将检测系统是否处于混合DPI模式，并在处于此模式时打开缓解措施，同时在不处于此模式时避免这些缓解措施。

此设置仅在Windows 8.1及更高版本中可见；较早的操作系统版本不支持具有不同DPI的多个显示器。
</td></tr><tr><td>

**mtp_enable**</td><td>
</td><td>
此选项可用于禁用对MTP（便携式）设备的内部支持。关闭后，将通过托管的Windows资源管理器视图访问设备。
</td></tr><tr><td>

**no_external_change_notify**</td><td>
</td><td>
不要监视外部文件更改。这使您可以禁用对Opus外部发生的文件更改的检测 - 只有Opus本身执行的文件操作才能被注意到并在文件窗口中反映出来。
</td></tr><tr><td>

**notify_debug**</td><td>
</td><td>
输出文件通知的调试信息。如果您在Opus无法注意到发生在Opus之外的文件更改时遇到问题，技术支持可能会要求您打开此开关以收集调试信息。

打开此选项会降低性能。除非您正在调查问题，否则请不要打开它，并在完成后将其关闭。

有关详细信息，请参见[常见问题解答](https://resource.dopus.com/t/changes-to-folders-are-not-being-detected/1786)。
</td></tr><tr><td>

**notify_debug_exclude**</td><td>
</td><td>
按路径过滤**notify_debug**输出的正则表达式。如果定义了此正则表达式，则仅当路径（或其子字符串）与正则表达式匹配时才会报告该路径。
</td></tr><tr><td>

**notify_debug_include**</td><td>
</td><td>
按路径过滤**notify_debug**输出的正则表达式。如果定义了此正则表达式，则仅当路径（或其子字符串）与正则表达式不匹配时才会报告该路径。
</td></tr><tr><td>

**notify_max_time**</td><td>
全局</td><td>

每个文件列表用于处理来自文件系统更改通知的最大时间（以毫秒为单位），然后考虑其它输入和事件。

默认为50毫秒。在极少数情况下，如果您生成事件的速度快于使用它们的速度，您可能需要将其从默认值提高。您还可以指定0（零）无限期地处理更改事件，尽管您可能只想将这样做作为测试，而不是永久设置。如果将其设置为零或设置得太高，则当生成大量文件系统事件时，文件列表可能对用户输入的响应较差。

这是一个全局设置。如果您为计算机上的一个用户更改它，它会影响所有其它用户，正如很可能所需要的那样。在多用户系统上，如果一个用户更改了此设置，其它人将看不到此更改，直到他们重新启动Opus。
</td></tr><tr><td>

**notify_min_items**</td><td>
全局</td><td>

在检查**notify_max_time**时间限制之前处理的最小事件数。有关您可能希望提高此设置以及此设置如何对多个用户起作用的情况，请参阅上文中的**notify_max_time**描述。
</td></tr><tr><td>

**script_output_level**</td><td>
</td><td>
允许您调整在*脚本日志*中显示的诊断输出类型（*[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)/其它日志*）。

这会影响来自Opus本身和插件DLL的诊断。从调用**DOpus.Output**方法的脚本发送到日志的输出始终显示。
</td></tr><tr><td>

**script_output_throttle**</td><td>
</td><td>
打开时，在*脚本日志*（*[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)/其它日志*）中显示的诊断输出将抑制重复太频繁的相同消息。

如果某诊断消息触发得太频繁，则通常应将其保留为打开状态，以防止性能问题。如果您正在使用插件DLL并且需要记录重复事件而不丢失任何事件，则将其关闭将很有用。

这会影响来自Opus本身和插件DLL的诊断。从调用**DOpus.Output**方法的脚本发送到日志的输出始终显示。
</td></tr><tr><td>

**shellchange_debug**</td><td>
</td><td>
输出shell文件通知的调试信息。如果您在Opus无法注意到发生在Opus之外的文件或文件夹更改时遇到问题，技术支持可能会要求您打开此开关以收集调试信息。有关详细信息，请参见[常见问题解答](https://resource.dopus.com/t/changes-to-folders-are-not-being-detected/1786)。
</td></tr><tr><td>

**sync_debug**</td><td>
</td><td>
通常应将其关闭，但可能会要求您将其打开以调试[同步工具](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md)做出的决定。如果您在此选项处于打开状态时使用“同步”工具，则桌面上将创建一个包含调试信息的文件。


</td></tr><tr><td>

**thumbnail_debug**</td><td>
</td><td>
输出用于生成缩略图的调试信息。技术支持可能会要求您打开此开关以收集调试信息。将降低性能，并且在不必要时应将其关闭。
</td></tr></tbody>
</table>