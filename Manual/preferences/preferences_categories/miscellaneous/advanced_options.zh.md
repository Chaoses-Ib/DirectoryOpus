# 高级

此页面包含被认为是“高级”选项的列表。它们通常是一些大多数用户不需要了解更不用说更改的晦涩设置。

每个选项都有一个名称和一个值。值可以是布尔值（true/false）、数字、字符串或从下拉列表中选择。要编辑选项的值，双击现有值，或选择该选项并按 <kbd>F2</kbd>。当选项未设置为其默认值时，会以粗体显示。

选择一个选项后，其描述将显示在页面底部。用星号标记的项目是全局设置 - 它们会影响计算机的所有用户。你可以选择一个选项并单击底部的 **重置** 按钮将其重置为默认值。

如果您正在寻找一个特定的选项，您可以使用顶部的搜索字段按名称或描述进行搜索。如果您只想查看已从其默认值修改的设置，可以使用搜索字段右侧的 **隐藏未更改的设置** 复选框。

<table>
<thead><tr><th>

**类别：行为**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
说明
</td></tr><tr><td>

**clipboard_datestamps**</td><td>
</td><td>
粘贴剪贴板中的图像或文本数据到新文件中时，会使用类似“Clipboard Image.bmp”和“Clipboard Text.txt”这样的名称，如果需要，还会添加一个数字后缀以使其唯一。打开此选项将在这些文件名开头添加一个 YYYY-MM-DD HH-MM-SS 时间戳。当粘贴和转换多个数据片段时，以及在标准文件打开对话框中选择它们时（否则无法正确地对名称进行分类），这有助于按顺序排列它们。
</td></tr><tr><td>

**clipboard_text_encoding**</td><td>
</td><td>
指定在将剪贴板中的文本粘贴到文件中时要使用的默认文本编码。
</td></tr><tr><td>

**compress_collections**</td><td>
</td><td>

压缩 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 以节省磁盘空间。如果关闭，文件集合将另存为未压缩的 XML 文件 - 如果集合中有很多文件，这会导致文件占用大量空间。
</td></tr><tr><td>

**config_backup_name**</td><td>
</td><td>

用于生成配置备份的默认名称的模板。在执行备份时仍然可以手动编辑名称，但这会更改其初始值。

模板支持日期和时间的 `D#`、`T#` 和 `A#` 前缀（如 [此处](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.zh.md) 所述）和环境变量。请注意，要使用日期和时间代码，必须将它们括在 `{}` 大括号中（例如 `D#yyyy-MM-dd`）。

（Opus 13.3.4 及以上版本：）默认使用本地时间，但你可以使用 `UTC#` 前缀来代替使用 UTC（例如 `UTC#T#HH-mm`）。
</td></tr><tr><td>

**dblclk_distance**</td><td>
</td><td>
鼠标光标在双击时移动的距离（以像素为单位）。
</td></tr><tr><td>

**display_release_history**</td><td>
</td><td>
打开后，在安装新版本后首次使用 Directory Opus 时，帮助文件中的版本历史记录页面将自动打开。这有助于了解新版本中的新功能、修复和其他更改。关闭此选项以防止版本历史记录页面自动出现。
</td></tr><tr><td>

**drag_distance**</td><td>
</td><td>
鼠标光标需要移动以初始化拖放的像素距离。如果要完全禁用拖放，请将其设置为 0。
</td></tr><tr><td>

**find_extension_func**</td><td>
</td><td>

在 Windows XP 上，Opus 会注册一个 [搜索处理程序](http://msdn.microsoft.com/en-us/library/bb776834(v=vs.85).aspx) ，该处理程序使你可以从开始菜单访问 Opus 查找功能。你可以使用此选项配置 Opus 作为对搜索处理程序做出响应而运行的命令。如果未指定，将使用默认的 [查找](/Manual/reference/command_reference/internal_commands/find.zh.md) 命令。
</td></tr><tr><td>

**find_unique_collections**</td><td>
</td><td>

不要让同时进行的 [查找](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md) 操作为结果使用相同的集合。查找功能默认在 *查找结果* [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 中呈现其结果。如果并行运行两个或更多查找操作，此选项将导致为第二个和后续任务的输出文件集合的名称进行修改以使其唯一，以便结果不会混杂。
</td></tr><tr><td>

**flatview_folder_filters**</td><td>
</td><td>

启用 [扁平视图](/Manual/basic_concepts/flat_view.zh.md) 中的子文件夹过滤。默认情况下，当文件列表为扁平视图时，快速过滤器（即由 [过滤器栏](/Manual/basic_concepts/searching_and_filtering/filter_bar.zh.md) 设置的过滤器）不会应用于文件夹。这样做是因为从列表中过滤出文件夹时，其所有内容也会自动被过滤出，这可能会导致不希望的结果。当文件列表为扁平视图模式时，过滤器栏会显示一个复选框选项，让你可以打开或关闭文件夹过滤，并且可以使用此选项来控制该复选框的默认状态（也就是说，如果你通常确实希望快速查看过滤器同时适用于扁平视图中的文件夹和文件，请打开此选项。）
</td></tr><tr><td>

**go_up_always_back**</td><td>
</td><td>

`后退` 命令通常会重新读取父文件夹，即使你之前访问过它并且它在历史列表中，而且你可以添加 **返回** 参数（即 **后退 返回**）以使 Opus 在可能的情况下（在转到父文件夹时保留文件选择）使用历史。如果你打开此选项，那么 **后退** 始终会表现得好像它也指定了 **返回** 参数。
</td></tr><tr><td>

**image_locate_services**</td><td>
</td><td>

让你可以配置 `图像定位` 命令使用的图像定位服务。每行由用于引用服务的关键字、等号和将在默认 Web 浏览器中打开的 URL 组成。插入代码 `%lat%` 和 `%lon%` 用于传递图像的纬度和经度。
</td></tr><tr><td>

**layout_string**</td><td>
</td><td>

此选项让你可以定义给保存在桌面上的 [列表布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md) 的名称（通过偏好设置中的 [布局](../layouts_and_styles/layouts.zh.md) 页面）。您必须指定包含代码 `%1` 的字符串 - 该代码将用布局名称替换为生成的快捷方式。如果未对此选项指定任何内容，则默认为 `布局 '%1'`。
</td></tr><tr><td>

**manual_sort_names**</td><td>
</td><td>

让你可以定义其他 [手动排序](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.zh.md) 顺序。Opus 可以记住不止一个手动排序顺序，你可以轻松地在你的命名顺序之间切换。例如，你可以在工作时使用一个手动排序顺序，在家里使用另一个手动排序顺序。你必须将每个名称输入单独的一行。如果您未指定任何名称，则将只有一个未命名的手动排序顺序。
</td></tr><tr><td>

**navlock_warn_verbose**</td><td>
</td><td>

在导航锁开启时，输入其中一方无法镜像的相对路径会在文件列表上显示一条警告。默认情况下，当 **navlock_warn_verbose** 为 **True** 时，这条警告很长，并且解释可以通过返回上一个文件夹，让两边重新同步，同时还提供了手动重新同步当前文件夹对或完全关闭导航锁的选项。如果你将 **navlock_warn_verbose** 设置为 **False**，将显示一条更短且不那么显眼的讯息。如果你已经理解导航锁的工作原理，并且已经多次阅读过较长的讯息，请切换到较短的讯息。
</td></tr><tr><td>

**pinyin_support**</td><td>
</td><td>
Opus 对拼音提供了一些支持（一种使用西方键盘输入中文字符的方法）。默认情况下，如果 Opus 以中文运行，即时查找和过滤器栏都支持拼音来进行搜索/过滤。此选项允许你覆盖自动设置并特别启用或禁用拼音支持。
</td></tr><tr><td>

**powermode_singledrag**</td><td>
</td><td>

[增强模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 文件列表默认具有持久选择 - 当你点击未选项目时，它会将其选中，但不会自动取消选取任何其他已选项目。通常当你点击项目并将其拖出时，也会拖动所有其他已选文件。当此选项开启时，如果你点击单个文件并将其拖动到左侧或右侧，只有该文件将成为拖动的一部分 - 任何其他已选文件都不会。
</td></tr><tr><td>

**powershell_exe**</td><td>
</td><td>
允许你指定将要使用的默认 PowerShell 可执行文件。例如，你可能希望将默认 PowerShell 菜单项打开 PowerShell 7，而不是 Windows PowerShell。
</td></tr><tr><td>

**rename_default_focus**</td><td>
</td><td>
选择 [重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md) 对话框中的哪个字段默认获得输入焦点 - *旧的名称* 或 *新的名称* 字段。重命名脚本可以覆盖此设置。
</td></tr><tr><td>

**save_button_editor_pos**</td><td>
</td><td>
保存 [命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md) 对话框的默认位置。如果你启用此选项，Opus 会在关闭命令编辑器时记住其位置，并在下次打开它时使用该已保存的位置。如果关闭，命令编辑器将显示在其父窗口的中央。
</td></tr><tr><td>

**searchfield_autostart**</td><td>
</td><td>
让你可以控制从文件窗口搜索字段停止键入搜索后多长时间自动开始。如果设置为 0，则使用在 [即时查找](/Manual/preferences/preferences_categories/filtering_and_sorting/find_as_you_type/README.zh.md) 页面上为即时查找配置的值。
</td></tr><tr><td>

**scroll_lock**</td><td>
</td><td>
如果 **Scroll Lock** 键开启，光标键将滚动文件列表而不更改焦点项目。
</td></tr><tr><td>

**search_warn_nonindexed**</td><td>
</td><td>
如果为真，如果你在未编入索引的文件夹上使用 Windows 搜索，并且搜索花费了超过几秒钟，Opus 将显示横幅警告你搜索可能会很慢，因为该文件夹未编入索引。如果关闭，将不会显示警告。（这不会对 Opus 的内置查找文件功能产生影响。查找文件独立于 Windows 搜索索引，并且不会显示类似的横幅。）
</td></tr><tr><td>

**setwallpaper_file**</td><td>
</td><td>
`Properties SETWALLPAPER` 命令可用于将选定的图像文件设置为桌面壁纸。默认情况下，选定文件会被复制到你的文档文件夹，但你可以通过为此选项指定一个完整路径和文件名来覆盖此位置。指定的文件名必须以 **.bmp** 或（在 Vista 及更高版本中）**.jpg** 结尾。
</td></tr><tr><td>

**single_click_rename**</td><td>
</td><td>
如果你启用了 [单点模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/single-click_mode.zh.md)，并且文件列表处于 [详细信息模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 且在 [偏好设置](../file_display_modes/details_mode.zh.md) 中启用了整行选择，通常无法使用鼠标发起 [内联重命名](/Manual/file_operations/renaming_files/inline_rename.zh.md)，因为在该行上的任何一点点击都会打开该项目。启用此选项后，你可以使用鼠标发起内联重命名 - 通过悬停选择该项后，你可以点击文件名 *以外* 的该行上的任意位置以开始重命名。
</td></tr><tr><td>

**slow_dblclk_rename**</td><td>
</td><td>
将其设置为 **False** 以禁用可以通过“慢速双击”（在双击时间之外点击已选文件或文件夹）进入内联重命名模式的标准功能。如果禁用了慢速双击重命名，你仍然可以使用 **F2** 键进入内联重命名模式。
</td></tr><tr><td>

**status_metadata_trigger**</td><td>
</td><td>
控制状态栏（如果显示选定或总媒体持续时间（时间长度））何时可能会触发计算该数据，如果文件列表中的其他任何内容尚未触发它。

计算媒体持续时间涉及独立地打开和解析每个文件中的数据，并且这可能需要一些时间并占用磁盘或网络，尤其是在文件很多的情况下。

如果已经为文件列表中的某一列（例如 **持续时间** 列）计算了持续时间，则此设置无效，因为状态栏会重新使用这些计算。此设置仅更改状态栏本身是否可以触发计算。

如果状态栏定义不包含任何 [媒体持续时间代码](/Manual/reference/status_bar_codes/codes_for_music_and_video_duration.zh.md) - 即 **{smp3}** 或 **{tmp3}** - 那么此设置也不适用，因为状态栏不会触发其不感兴趣的数据计算。

默认设置为 **从不**，这意味着状态栏本身永远不会触发计算，只有当其他内容计算出持续时间信息时才会显示它。

选择 **始终** 设置意味着状态栏将在所有情况下触发持续时间计算。

选择 **始终，平板视图和集合除外** 设置意味着状态栏可以触发持续时间计算，但启用 [平板视图](/Manual/basic_concepts/flat_view.zh.md) 或处于 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 中时除外。平板视图和集合通常涉及大量文件，因此是极端情况。
</td></tr><tr><td>

**styles_update_previous**</td><td>
</td><td>
如果你已经更改了文件窗口的外观（通过手动打开或关闭用户界面元素，或通过 [文件窗口样式](/Manual/basic_concepts/the_lister/styles.zh.md)），`Prefs STYLE` 命令让你可以将文件窗口返回到其初始外观。如果你启用此选项，那么当选择新的文件窗口样式时，将被认为是“上一个”样式的内容会被更新（因此从那时起 `Prefs STYLE=^prev` 将重置文件窗口为该样式，而不是其初始布局）。
<table>
<thead><tr><th>

**Category: General **</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>

Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**tab_click_nofocus**</td><td>
</td><td>

点击 [文件夹标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md) 将其置于前面时，通常会激活该文件列表并将其设置为源。如果此选项处于打开状态，则单击目标文件列表中的标签页将使源/目标状态保持不变。
</td></tr><tr><td>

**utility_panel_autoshrink**</td><td>
</td><td>
可以使用此设置使实用程序面板在执行查找、重复文件或同步操作后自动缩小到仅包含其标题。单击设置以打开一个菜单，您可以在其中为每个操作打开或关闭自动缩小功能。
</td></tr><tr><td>

**wheel_acceleration**</td><td>
</td><td>
Opus 在使用鼠标滚轮在文件列表中滚动的过程中通常会应用少量的加速，但是您可以在需要时使用此选项禁用它。
</td></tr><tr><td>

**wordbreak_char_names**</td><td>
</td><td>

这可以让你指定一个或多个将在编辑文本框中用作“单词分隔”字符的字符，在编辑文件名（例如内联重命名）时。单词分隔字符会影响当您按下 **Ctrl+向左** 或 **Ctrl+向右** 键时光标停止的位置。空格始终被视为单词分隔。
</td></tr><tr><td>

**wordbreak_char_paths**</td><td>
</td><td>

这可以让你配置在编辑路径（例如在 [Breadcrumb 路径字段](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.zh.md) 中）时编辑文本框中的其他单词分隔字符。标准路径分隔符（**:/\\**) 始终被视为单词分隔符。
</td></tr><tr><td>

**wsl_distribution**</td><td>
</td><td>
如果您安装了多个 WSL 发行版，此选项可以让您控制 Opus 使用哪个发行版来启动 WSL 命令。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**Category: Compatibility**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**convert_descriptions**</td><td>
</td><td>

将旧描述文件转换成 *descript.ion* 格式。除非您从非常老版本的 Directory Opus 迁移，否则您可能永远不需要设置此。
</td></tr><tr><td>

**def_func_cd_sourcedir**</td><td>
</td><td>

从未指定当前目录的按钮启动程序时，将当前源目录用作默认当前目录。出于安全原因，此类功能的默认设置是将当前目录设置为 *C:\Windows\System32* 目录。
</td></tr><tr><td>

**direct2d**</td><td>
</td><td>

控制 Direct2D 如何用来渲染 UI 的某些部分。某些地方使用 Direct2D 来提供更好的性能或质量更高的渲染。

**Normal** 是默认选项，它启用 Direct2D，并允许操作系统决定使用硬件（GPU）还是软件（CPU）渲染。

如果您认为您的 GPU 硬件或驱动程序有问题，并且希望强制 Direct2D 在您的 CPU 上渲染所有内容，则可以选择“**强制 CPU 渲染**”。

可以选择“**禁用**”来阻止使用 Direct2D。

在编写本文时，该选项会影响进度对话框的速度图。
</td></tr><tr><td>

**dlldir_security**</td><td>
</td><td>

此选项默认处于启用状态，可防止 Opus 从当前工作目录加载 DLL。这降低了“二进制植入”漏洞的风险，当您从有人隐藏了恶意 DLL 的文件夹中打开照片或音乐等内容时，该漏洞会欺骗您的计算机运行不受信任的软件。

关闭此选项会降低您的安全性，但如果您遇到的问题是由计算机上安装的编写不良的 shell 扩展程序或其他第三方软件引起的，则可能需要。 （此类软件通常仅与 Windows资源管理器兼容，而 Windows资源管理器并未采用 Opus 默认使用的更为安全的方式。）

此选项仅影响 Opus，以及您从 Opus 启动的软件（如果有）。这不是一个系统范围的设置（尽管如果您希望它更安全，则可以设置一个系统范围的设置；搜索网络了解更多 CWDIllegalInDllSearch 相关信息）。

从便携式 USB 安装运行时无法修改此选项。
</td></tr><tr><td>

**dragdrop_async**</td><td>
</td><td>

当文件从另一个程序拖放到 Opus 中时，Opus 通常会将其处理放到后台，这样窗口就会一直处于响应状态。如果您拖放内容的程序支持异步拖放的 Windows API，那么这永远不会是个问题；但是，很多程序不支持该 API。

当 **dragdrop_async** 处于启用状态时，Opus 会尝试在后台处理 *所有* 拖放，如有必要则会曲解规则，除非它检测到是从已知存在此问题程序拖放而来。如果此选项处于关闭状态，Opus 将变得更加严格，并将仅处理明确支持它的程序的后台拖放。

如果您在从某些程序将文件拖放到 Opus 时遇到问题，请尝试关闭此选项，看看是否可以提高兼容性。缺点是，您有时可能必须等到拖放完成，然后才能继续使用拖放到的窗口。
</td></tr><tr><td>

**flush_com_libraries**</td><td>
</td><td>

默认情况下，Opus 在不再需要 COM 库（通常是 shell 扩展 DLL）时，会积极要求它们卸载。这会导致组件崩溃，如果它们说可以在仍然在进程中执行代码时，它们可以卸载是不正确的。将此设置切换为 **False** 可能会减少这些故障组件的问题。
</td></tr><tr><td>

**function_default_async**</td><td>
</td><td>

默认情况下，包含单个命令的功能将作为 [异步](/Manual/customize/creating_your_own_buttons/synchronous_and_asynchronous_functions.zh.md) 运行，而包含两个或更多个命令的功能将作为 [同步](/Manual/customize/creating_your_own_buttons/synchronous_and_asynchronous_functions.zh.md) 运行。此选项可以让您覆盖此行为，并默认让所有功能（单个或多个命令）都作为异步。
</td></tr><tr><td>

**global_explorer_replacement**</td><td>
全局</td><td>

[资源管理器替换](/Manual/basic_concepts/explorer_replacement.zh.md) 模式通常是每个用户的设置，但如果您打开此选项，资源管理器替换模式设置将对机器的所有用户生效。这可以提高 Opus 拦截某些对资源管理器的调用的能力，但通常您会将其关闭。
</td></tr><tr><td>

**mp3_custom_comments**</td><td>
</td><td>

MP3 ID3v2 标签用于注释并没有严格定义，并且不同的第三方工具经常使用自己的此标签表单。您可以使用此选项让 Opus 用指定的描述来写 COMM 标签，当使用 [元数据窗格](/Manual/basic_concepts/the_lister/metadata_pane.zh.md) 时，这可以使它与这些工具兼容。例如，MediaMonkey 将其 COMM 标签标记为 **Songs-DB_Custom1**，所以您应该将此字符串放入 **mp3_custom_comments** 值中，以便使 Opus MP3 注释与 MediaMonkey 兼容。如果您使用多个工具，您可以在每行添加多个注释描述，Opus 将为每个注释写一个单独的 COMM 标签。
<table>
<thead><tr><th>

分类：外观 </th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

**是否全局**</td><td>
描述
</td></tr><tr><td>

**collection_icon_default**</td><td>
</td><td>

不匹配任何其他类型的单独文件集合的自定义默认图标。

此设置会更改默认图标。也可以通过属性对话框更改特定集合的图标。

你可以指定独立的 .ICO 文件的路径（如 `C:\MyIcon.ico`），也可以指定 .EXE 和 .DLL 文件中的图标，使用数字 ID 来选择特定的图标（如 `/system/imageres.dll,101`）。
</td></tr><tr><td>

**collection_icon_find**</td><td>
</td><td>

与 **collection_icon_default** 类似，但具体针对为查找结果和搜索查询生成的集合。
</td></tr><tr><td>

**collection_icon_flickr**</td><td>
</td><td>

与 **collection_icon_default** 类似，但具体针对为 Flickr 同步生成的集合。
</td></tr><tr><td>

**collection_icon_marked**</td><td>
</td><td>

与 **collection_icon_default** 类似，但具体针对通过在查看器中标记图像生成的标记图片集合。
</td></tr><tr><td>

**collections_icon**</td><td>
</td><td>

[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 根文件夹的自定义图标。

这只影响真正的“文件集合”根文件夹。上述其他设置涵盖了各种类型的单独集合。

你可以指定独立的 .ICO 文件的路径（如 `C:\MyIcon.ico`），也可以指定 .EXE 和 .DLL 文件中的图标，使用数字 ID 来选择特定的图标（如 `/system/imageres.dll,101`）。
</td></tr><tr><td>

**context_menu_icon_set**</td><td>
</td><td>

某些上下文菜单包含 Opus 自动生成的项，而且除了将图标集移动到列表顶部并影响 *所有* 工具栏和菜单图标之外，你没有机会更改其中使用的图标尺寸或样式。由于你可能希望在上下文菜单中使用比其他所有地方都更小的图标集，因此此设置允许你指定另一个集来代替普通集。Opus 会在生成上下文菜单项以添加到压缩包和从压缩包提取时使用此设置。请注意，这仅适用于在 Opus 内部显示菜单时；资源管理器中的类似菜单一开始不使用图标集。

名称应与图标集的 XML “name”属性匹配，*而不是* “display_name”。例如，如果图标集定义为 `<iconset name="flat_small"> ... <display_name>Small Icon Set (Flat)</display_name>` 那么你应在设置中键入 “flat_small”，而不是 “Small Icon Set (Flat)”。
</td></tr><tr><td>

**custom_network_folder_icons**</td><td>
</td><td>

当设置为 *True* 时，在网络驱动器上的位置字段和文件夹标签页中，可以显示单独的自定义文件夹图标。（在本地驱动器上以及文件列表本身中，系统始终支持自定义文件夹图标，但受 **[配置 / 文件夹](../folders/README.zh.md)** 下 **显示以下内容的常规图标...** 设置的约束。）

如果你有指向非常慢或无法访问的网络驱动器的文件夹标签页，那么打开此设置可能会导致性能下降，甚至暂时冻结。自定义文件夹图标通常通过文件夹的属性对话框进行配置，但 Windows 会隐藏网络文件夹的选项，这可能是出于性能原因，也可能是因为你需要确保你指定的图标路径对所有网络客户端都可以访问。你仍可以手动创建自定义图标元数据，或将本地自定义文件夹复制到网络驱动器。因此，在网络驱动器上拥有自定义文件夹图标是有可能的，但这种情况很少见，你只有在使用它们时才应打开此设置。
</td></tr><tr><td>

**glass_status_bar**</td><td>
</td><td>

当设置为 *True* 时，使用 Windows“玻璃”效果绘制其背景的状态栏。这在 Windows 7 上看起来不错，但在较新版本的 Windows 上几乎没有意义。

除非在全系统范围内启用了玻璃（即，可以使用桌面窗口组成），并且在 **配置 / 显示 / 状态栏** 下打开了 **保持状态栏位于文件窗口底部**，否则此设置无效。
</td></tr><tr><td>

**gloss_and_gradients**</td><td>
</td><td>

启用各种用户界面元素中的光泽和渐变效果。如果你更喜欢扁平、更无聊的外观，请将其关闭。

当设置为 *自动* 时，如果仍在 Windows 8 或更高版本上，则会选择一个平坦简单的外观，如果在 Windows 7 上，则会选择一个带有渐变的闪亮外观。
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

为 **True** 时，允许 Opus 将如何复制文件的详细信息委派给 Windows。

Windows 提供了一个用来复制文件的高级 API，该 API 以难以理解且未记录的方式进行优化，并且设备制造商倾向于根据该 API 来测试和优化自己的硬件和驱动程序。通常情况下，你无法在性能和兼容性方面超越此 API；在最好的情况下，你只能与之相等。

Opus 还拥有自己的自定义文件复制代码，其工作级别稍低，并且至关重要的是，适用于并非简单文件到文件复制的情况。此自定义代码通常与高级 API 速度相同，但在某些情况下，它的速度较慢（例如，对于非常关注缓冲区大小或其他参数的特定设备或网络配置）。

默认情况下，Opus 对普通的文件到文件复制使用高级 API。在无法使用该 API 的情况下，Opus 会自动回退到其自己的自定义代码。这些情况包括复制到压缩包或 FTP 站点或从中复制、在保存稀疏数据时复制以及拆分和合并文件。

如果你将 **copy_allow_delegation** 设置为 **False**，则 Opus 将始终使用其自定义文件复制代码，即使在不需要的情况下也是如此。在某些罕见的情况下，如果 Windows 文件复制 API 出于某种原因较慢，或者你想要强制使用非缓冲 I/O，你可能需要这么做。一般来说，我们不建议你修改此设置。

`Copy DELEGATE` 参数可用于针对各个按钮、热键等覆盖此设置。
</td></tr><tr><td>

**copy_buffer_size**</td><td>
</td><td>

自定义文件复制代码使用的缓冲区大小。单位可以是 KB、MB 或 GB。如果未指定单位，则默认为 KB。

这指定了 Opus 在使用其自己的自定义代码[复制文件](/Manual/file_operations/copying_moving_and_deleting_files/README.zh.md) 时一次读取或写入的数据量。虽然这无关紧要，但某些 USB 设备或网络似乎对复制缓冲区的尺寸很敏感。如果你发现复制的速度或可靠性远低于预期，请尝试增大或减小缓冲区大小。

`Copy BUFSIZE` 命令可用于针对各个按钮、热键等覆盖此设置。

此缓冲区是除了文件系统、硬件等提供的任何缓冲之外的缓冲；它与由 **copy_nonbufferio_threshold** 设置控制的非缓冲 IO 模式无关。

在 **copy_allow_delegation** 为 **True** 的通常情况下，**copy_buffer_size** 和 **copy_nonbufferio_threshold** 设置对普通的文件到文件复制没有影响，但仍然可以影响拆分/合并文件、从压缩包复制等特殊情况。
</td></tr><tr><td>

**copy_nonbufferio_threshold**</td><td>
</td><td>

文件大小阈值，高于此阈值时，将使用自定义文件复制代码以非缓冲模式执行到本地设备或从本地设备执行的复制。非缓冲模式绕过了 Windows 提供的文件系统缓冲区。单位可以是 KB、MB 或 GB。如果未指定单位，则默认为 MB。

对于非常大的文件，以非缓冲模式复制可以提高内存效率、复制速度和 UI 响应能力。另一方面，对于较小的文件或某些设备，非缓冲模式可能会减慢速度。在极少数情况下，非缓冲模式可能根本不起作用（例如，如果你有错误报告其扇区大小的设备）。
将值设为 0（零）以禁用非缓冲模式。出于兼容性原因，其默认情况下处于禁用状态。如果你希望启用它，我们建议 1 MB 作为良好的起始值。

`Copy NONBUFIO` 命令可用于覆盖单个按钮、热键等处的此设置。

在通常情况下，如果 **copy_allow_delegation** 为 **True**，则 **copy_buffer_size** 和 **copy_nonbufferio_threshold** 设置对普通文件到文件拷贝没有影响，但仍会影响特殊情况，例如拆分/合并文件、从压缩包中拷贝等。
</td></tr><tr><td>

**dos_automap_unc_paths**</td><td>
</td><td>

在 [MS-DOS 批处理命令](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.zh.md) 中自动创建 UNC 路径的驱动器映射。这使你能够通过 UNC 路径直接在网络驱动器上运行 DOS 批处理脚本。
</td></tr><tr><td>

**move_netshare_semantics**</td><td>
</td><td>

在移动文件夹时对 PGP Netshare 进行特殊处理。与文件相比，移动文件夹时 PGP Netshare 的行为有所不同 - 如果发现移动文件夹到受 Netshare 保护的位置会失败，请启用此选项。
</td></tr><tr><td>

**network_errors**</td><td>
全局</td><td>

指定指示网络身份验证错误的错误代码。某些网络文件系统在用户名/密码身份验证错误的情况下会返回未记录的错误代码 - 如果你发现尝试连接到网络驱动器时只得到一个错误对话框，你应当记录错误代码并将其添加到此选项。当 Opus 收到该错误代码时，它将把它视为一个身份验证故障，并提示你提供凭证来访问该资源。你可以使用分号将其分隔开来以指定多个错误代码（例如 **50;1003;1245**）。
</td></tr><tr><td>

**no_copy_dir_dates**</td><td>
</td><td>
禁用文件夹时间戳的拷贝。在拷贝时仅保护文件的时间戳；作为一个拷贝操作的一部分创建的文件夹将有当前的时间和日期。
</td></tr><tr><td>

**remember_net_paths**</td><td>
</td><td>

Opus 通常记住在系统文件打开或保存对话框中使用的前一个路径（例如，当你使用 [配置备份或恢复](../../backing_up_and_restoring_preferences.zh.md) 功能时），但出于性能原因，它并不记住网络路径。如果你希望 Opus 也记住网络路径，请启用此选项。
</td></tr><tr><td>

**size_on_disk_thorough**</td><td>
</td><td>

默认情况下处于关闭状态。如果启用，文件夹大小计算将显著变慢，但当使用特别的 NTFS 压缩模式时，Opus 将在“磁盘大小”列中显示更准确的信息。

这不会影响像 Zip 压缩包和其他非文件系统压缩方法的报告大小。同样，对于通过文件属性对话框可以开启的标准 NTFS 压缩模式，所报告的大小也不会受到影响。差异在于只能通过 Windows compact.exe 命令设置的特殊 NTFS 压缩模式，例如 /EXE:LZX。Windows 中的一个错误导致用这些模式压缩的文件被错误地报告为未压缩。没有办法知道这些压缩模式正在使用，报告这些模式的磁盘大小值的正确方法是在 *每个文件* 进行额外的查询。这个额外的查询非常慢，尤其是在网络驱动器上，并且在重新读取文件夹时，该数据不会被操作系统缓存。

我们建议除非你确实需要更准确的信息，否则将此设置保留关闭状态。
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
FTP 拷贝缓冲区大小（以字节为单位）。这定义了通过 FTP 传输文件时使用的缓冲区的大小的。你通常不需要更改此项。
</td></tr><tr><td>

**ftp_dblclk_cache_time**</td><td>
</td><td>

从 [FTP](/Manual/ftp/README.zh.md) 网站双击文件时的缓存时间（以分钟为单位）。当你在 FTP 网站上双击一个文件来打开它时，Opus 会下载该文件并将它保存到一个临时文件夹。如果你在指定的时间内再次双击同一个文件，它将使用已下载的文件来保存再次文件的下载。默认情况下，它被设为 0，这就意味着文件不会为了双击而自动缓存。
</td></tr><tr><td>

**ftp_do_not_cache**</td><td>
</td><td>

通常，[FTP](/Manual/ftp/README.zh.md) 系统会缓存远程网站的目录列表以提高性能。如果你希望在每次更改 FTP 网站的文件夹时强制刷新远程目录，请启用此选项。
</td></tr><tr><td>

**ftp_no_case_sensitive**</td><td>
</td><td>

FTP 网站通常是区分大小写的（例如，名为 *TEST.TXT* 的文件将与名为 *test.txt* 的文件不同）。设置此选项以禁用 FTP 站点的区分大小写。
</td></tr><tr><td>

**ftp_no_pasv_change**</td><td>
</td><td>
如果 Opus 检测到作为被动 (PASV) FTP 连接结果指定的地址是一个不可路由的地址，它将尝试将此地址更正为该网站的可路由地址。如果你启用此选项，那么 Opus 将尝试使用指定的不可路由地址，这仅在 FTP 服务器与客户端机器位于同一网络上的情况下才成功。
</td></tr><tr><td>

**ftp_ssl_verbose**</td><td>
</td><td>
导致 FTP 日志在 SSL 连接时显示扩展输出。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：图像格式**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
描述
</td></tr><tr><td>

**amiga_icon_borders**</td><td>
</td><td>
在缩略图模式中显示 Amiga 图标周边的边框。
</td></tr><tr><td>

**amiga_icon_palette**</td><td>
</td><td>
在显示传统 Amiga 图标时使用的调色板。
</td></tr><tr><td>

**clipboard_image_paste**</td><td>
</td><td>

如果你在你的剪贴板中有图像（例如通过 PrtScn 键），并粘贴到文件夹中，Opus 将保存剪贴板图像到一个文件中。此设置更改了将要使用的图像格式：JPG、PNG、BMP 或 GIF。

你还可以设置你的 <kbd>Ctrl+V</kbd> 热键来运行 `Clipboard PASTE AS=ask`，当你在文件夹中粘贴图像时，使 Opus 提示你输入图像格式（和文件名）。在这种情况下，此设置决定了默认选择的格式。
</td></tr><tr><td>

**clipboard_image_paste_dpi**</td><td>
</td><td>
当启用时，粘贴剪贴板图像数据到一个文件（通过在列表中按下 <kbd>Ctrl+V</kbd>）会自动缩放它以补偿系统 DPI。
</td></tr><tr><td>

**psd_image_preference**</td><td>
</td><td>

Photoshop PSD 文件最多可以有三个嵌入图像：一个非常有损的压缩和没有不透明/α 数据的小型（164x164）缩略图；一个存储在无损格式中的全尺寸扁平预览图像，可以包括不透明度/α 数据；最后是 Photoshop 内部格式的完整分层图像数据。（分层数据不会被 Opus 解码，而且除了 Photoshop 本身之外，很少有其他东西会呈现它。）
默认情况下，Opus 将小的缩略图图像用于缩略图，并将全尺寸预览图像用于查看器。此设置允许你覆盖此设置，以便在缩略图和查看器中使用一张图像或另外一张图像。

如果你希望 Opus 显示大于 164x164 像素或有透明度/alpha 数据的 PSD 缩略图，请选择在查看器和缩略图中使用预览图像的选项。

但是，某些 PSD 文件没有有效的预览图像，所以也有永远不使用预览图像并始终使用小缩略图（即使在查看器中）的选项。PSD 是否包含一个平面预览图像取决于它是如何从 Photoshop 中保存的。“最大化兼容性”或类似的选项应该开启，以便包含预览图像。在 Photoshop CC 2015.5.0 中，该选项位于配置/文件处理下方。在某些情况下，如果没有“真实”的预览图像，就会有一个由 Photoshop 所写的带有文本的黑白色占位符，告诉你没有预览图像。不幸的是，某些版本的 Photoshop 在某些情况下会写一个损坏的占位符图像。（数据格式良好，但它表示的图像不是。在任何一种情况下，Opus 都很难检测到是否有“真实”的预览图像，还是只是一个占位符，因为两者都是经过编码后存在于文件中的不同像素数据，该部分与真实预览图像完全相同。）如果你的工作流程无法更改并导致 PSD 文件缺失或损坏的预览图像，你可以告诉 Opus 始终使用小的缩略图，即使在查看器中也是如此，这样你至少可以大致了解每个文件的样子。
</td></tr><tr><td>

**tiff_assume_alpha**</td><td>
</td><td>

假设没有指定含义的 TIFF 图像中的第四个频道是（非倍增的）alpha。如果关闭此选项，则 32 位 TIFF 图像必须指定它包含一个有效的 alpha 通道，以便 Opus 将其视为这样。
</td></tr><tr><td>

**tiff_max_doc_metadata**</td><td>
</td><td>

Opus 将尝试从中提取文档元数据的 TIFF 图像的最大大小（以兆字节为单位）。这可以防止非常大的 TIFF 出现问题，例如那些由 Photoshop 保存的图像。
</td></tr><tr><td>

**use_color_management**</td><td>
</td><td>

在加载图像时使用颜色管理。如果启用，Opus 将检查图像文件是否包含颜色配置文件，如果包含，它将使用你指定的 ICC 文件（或默认的 sRGB 配置文件）来更准确地渲染图像。目前，仅用于 JPEG 和 PNG 图像。
</td></tr><tr><td>

**viewer_disable_internal**</td><td>
</td><td>

允许你禁用查看器和预览窗格中的内置图像格式。这不会影响查看器插件（它们已经可以直接禁用）；事实上，其目的是允许你使用插件和第三方组件覆盖内部查看器，而在它们无法自行完成的情况下（通常是不知道任何关于 Opus 的预览处理程序和 ActiveX 控件）。例如，你可能希望将 TIFF 查看器转移到可以处理多页 TIFF 的第三方 ActiveX 控件。该设置是一个字符串，用于列出你想禁用的图像类型。将其设置为 **tiff** 将禁用内部 TIFF 查看器。将其设置为 **JPG,PNG** 将禁用内部 JPG 和 PNG 查看器。
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

通常，Opus 会在显示日期（例如在文件窗口的日期列中）时使用由系统（或当前语言环境）定义的日期格式。此设置允许你覆盖它并指定你自己的自定义格式。

请参阅 [日期和时间代码](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.zh.md) 页面，了解有关日期和时间格式的信息。
</td></tr><tr><td>

**custom_date_format_long**</td><td>
</td><td>

类似于 **custom_date_format**，但用在使用长（更详细）日期格式的地方。许多地方没有使用长日期格式，因此如果你不确定，**custom_date_format** 更可能是你想要的。
</td></tr><tr><td>

**custom_time_format**</td><td>
</td><td>

通常，Opus 会在显示时间（例如在文件窗口的日期/时间列中）时使用由系统（或当前语言环境）定义的时间格式。此设置允许你覆盖它并指定你自己的自定义格式。

请参阅 [日期和时间代码](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.zh.md) 页面，了解有关日期和时间格式的信息。
</td></tr><tr><td>

**deffmt_cloud_availability**</td><td>
</td><td>

防止 **云存储** 文件夹格式自动添加 **可用性** 列。

当你保存新的默认文件夹格式并选择替换所有现有格式的选项时，一些格式会自动添加额外的列。在大多数情况下，这些列很重要，但是可以通过像这样的选项来覆盖某些列。
</td></tr><tr><td>

**deffmt_cloud_status**</td><td>
</td><td>

防止 **云存储** 文件夹格式自动添加 **状态**（**状态图标**）列。（请参阅上文中的 **deffmt_cloud_availability**。）
</td></tr><tr><td>

**desc_show_info**</td><td>
</td><td>

对于每个文件，**说明** 列通常会显示：

- 元数据摘要。（例如图片类型和尺寸、音频编解码器和比特率。）
- 用户定义的描述（如果有）。（这可以通过默认工具栏上的 **属性、描述** 命令设置。某些文件类型也允许在它们的标签中设置用户定义的描述/注释。）
- 目标路径（如果文件是快捷方式或链接）。此选项允许你从“说明”列中删除用户定义的描述和/或目标。例如，如果你已添加了单独的 **用户说明** 和 **目标** 列，那么你可能只想将元数据摘要保留在 **说明** 列中。
</td></tr><tr><td>

**display_folder_extensions**</td><td>
</td><td>

如果启用此选项，则文件夹将被视为具有扩展名（后缀），仅用于显示（即在 *名称* 和 *扩展名* 列中）。例如，名为“Hello.World”的文件夹将显示“World”在扩展名列中，而不是不显示任何内容。
</td></tr><tr><td>

**file_size_units**</td><td>
</td><td>

指定在显示文件大小和磁盘空间时要使用的单位。传统形式是使用二进制单位（基于 2^10）和“十进制”前缀（1 KB = 1024 字节）。你还可以选择使用十进制（基于 10^3）单位（1 KB = 1000 字节）或二进制单位（1 KiB = 1024 字节）。请参阅 [此维基百科页面](http://en.wikipedia.org/wiki/Binary_prefix) 了解更多信息。
</td></tr><tr><td>

**graphs_separate_files_dirs**</td><td>
</td><td>

出现在文件列表中的条形图（相对大小、相对年龄）是针对文件和文件夹分别计算的。如果你关闭此选项，它们将针对所有项目进行计算。
</td></tr><tr><td>

**group_column_maxwidth**</td><td>
</td><td>
指定**组**列的最大宽度。当文件列表列设置为自动调整大小时，此选项可防止**组**列增长超过指定的像素数。
</td></tr><tr><td>

**image_res_units**</td><td>
</td><td>

用于与图像分辨率相关的列（**分辨率（X)），分辨率（Y）**）。如果未设置，则每个图像文件本身都会指定单位，因此您可能在任何一个目录中都会出现英寸和厘米的混合 - 设置此选项将覆盖图像并始终显示一致的单位。
</td></tr><tr><td>

**image_size_units**</td><td>
</td><td>

用于与图像大小相关的列（**物理宽度，物理高度，物理大小**）。如果未设置，则每个图像文件本身都会指定单位，因此您可能在任何一个目录中都会出现英寸和厘米的混合 - 设置此选项将覆盖图像并始终显示一致的单位。
</td></tr><tr><td>

**multipart_extensions**</td><td>
</td><td>

“多部分文件扩展名”是由多个部分组成的文件扩展名，这些部分由点分隔。例如，在 Unix 世界中，**.tar.gz** 文件非常常见。在许多情况下（重命名、排序等），将整个字符串视为文件扩展名，而不仅仅是 Windows 中的标准**gz**，这很有意义。Opus 会对多种档案格式自动执行此操作，并且**multipart_extensions** 选项也允许您添加您自己的自定义扩展名。每行输入一个扩展名。
</td></tr><tr><td>

**name_group_high_pri_chars**</td><td>
</td><td>

当按文件名[分组](/Manual/basic_concepts/sorting_and_grouping/README.zh.md) 文件列表时，以这些字符开头的文件将被放入列表顶部的“高优先级”组中。通常，以非字母字符或数字开头的文件将被放置在*未指定*组中，但是您可以使用此选项，例如，将以 **!** 或 **\#** 开头的文件放在一个单独的组中。
</td></tr><tr><td>

**show_sharing_overlays**</td><td>
</td><td>

Windows 7 删除了共享文件夹的图标覆盖（![](/Manual/images/media/sharing_overlay.png)），但许多人喜欢此功能，所以 Opus 替换了自己的功能。如果您不想看到这些覆盖层，请关闭此选项。如果通过 [文件列表列/图标](/Manual/preferences/preferences_categories/file_display_columns/icons.zh.md) 选项页面中*显示快捷方式箭头和其他图标覆盖*选项完全关闭覆盖层，则此选项将不起作用。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：限制**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
说明
</td></tr><tr><td>

**context_menu_max_files**</td><td>
</td><td>

由于为大量文件生成上下文菜单可能需要花费 काफी时间，因此当您右键单击选定的大于一定数量的文件时，Opus 会显示确认消息。该限制默认为 1000，但您可以更改此限制，也可以将其设置为 **0** 以完全不进行确认。
</td></tr><tr><td>

**everything_max_results**</td><td>
</td><td>
设置 Everything 搜索可以返回的搜索结果数量限制。
</td></tr><tr><td>

**long_operation_notify_time**</td><td>
</td><td>
如果 UI 线程中的操作花费的时间超过指定的时间，Opus 将显示一个通知对话框，让您取消操作。
</td></tr><tr><td>

**max_folder_thumb_time**</td><td>
</td><td>
指定 Opus 在为文件夹生成缩略图时花费的最大时间（以毫秒为单位）。
</td></tr><tr><td>

**max_md5_file_size**</td><td>
</td><td>

指定 Opus 在文件窗口中显示其中一个校验和列时将计算其哈希的最大文件大小（以千字节为单位）。如果文件大于此大小，则仍可以通过 `GetSizes HASH` 命令手动生成其校验和。

**特殊值：**

- **0** - 忽略文件大小，始终自动计算文件哈希。
- **1** - 忽略文件大小，从不自动计算文件哈希。

（此设置的名称具有历史意义，它适用于所有哈希 - 不仅限于 MD5。）
</td></tr><tr><td>

**max_thumbnail_mem_size**</td><td>
</td><td>
每个文件列表的内存中缩略图的最大内存（以兆字节为单位）。Opus 将丢弃超出视图的缩略图，以将每个文件列表的缩略图的内存使用率保持在指定的大小以下。如果设置为 0，则没有限制。
</td></tr><tr><td>

**max_thumbnail_size**</td><td>
</td><td>

Opus 将生成的缩略图的最大像素大小（宽度和高度）。较大的缩略图需要更多内存。这控制了可在 [缩略图](../file_display_modes/thumbnails_mode/README.zh.md) 页面的“选项”中选择的最大尺寸缩略图，还通过 [缩略图大小](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/README.zh.md) 滑块控制。
</td></tr><tr><td>

**suggestion_popup_lines**</td><td>
</td><td>
配置弹出式建议列表中一次显示的行数。
</td></tr><tr><td>

**zip_dblclk_cache_time**</td><td>
</td><td>

从 ZIP 文件中双击文件并缓存的时间（以分钟为单位）。当您双击文件以从 ZIP 文件中将其打开时，Opus 会提取文件（以及可能的是其他文件，视 [压缩包选项](../zip_and_other_archives/archive_options.zh.md) 选项页面中的自动提取选项而定），并将其保存到临时文件夹中。如果您在指定时间内再次双击同一文件，则已提取的文件将用于再次提取文件。默认情况下，此设置设置为 0，这意味着不会自动缓存文件以进行双击。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**类别：故障排除**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
选项</td><td>

** 全局？ **</td><td>
说明
</td></tr><tr><td>

**clipboard_change_delay**</td><td>
</td><td>
处理剪贴板更改事件前的延迟（以毫秒为单位）。如果 Opus 正在运行时，某些软件（例如 Microsoft Office）在修改剪贴板时遇到问题，您可能需要增加这个延迟。
</td></tr><tr><td>

**collection_change_delay**</td><td>
</td><td>

处理 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 中外部删除/重命名操作前的延迟（以毫秒为单位）。如果您发现将文件保存在其他程序（例如 Word）中编辑时，它们会从文件集合中消失，则您可能需要增加这个延迟。
</td></tr><tr><td>

**context_menu_debug**</td><td>
</td><td>
输出上下文菜单扩展的调试信息。有关调试上下文菜单问题的更多信息，请参阅[常见问题解答](https://resource.dopus.com/t/crash-exit-or-high-cpu-when-right-clicking-certain-files/1335)。Directory Opus Light 的用户可以将注册表值 **HKEY_CURRENT_USER\SOFTWARE\GPSoftware\Directory Opus\ContextMenuDebug** (DWORD) = 1 设置为此选项的替代方案。
</td></tr><tr><td>

**crash_debug_button**</td><td>
</td><td>
打开后，在 Opus 崩溃对话框中添加一个“调试”按钮，允许您调用常规 Windows 崩溃行为。如果安装了即时调试器，则这将允许您在其当前状态下调试该进程。此选项仅在您是正在开发插件或 Shell 扩展的开发人员时才应打开；不太可能对其他人有用。
</td></tr><tr><td>

**crash_handler**</td><td>


Opus 包含一个自定义崩溃处理程序，旨在提供有关崩溃的信息，以便 GP Software 可以使用这些信息来追踪原因。它会保存进程内存部分的日志（“转储”），并且你可以使用帮助菜单中的内置的崩溃提交工具将这些信息自动上传。崩溃处理程序部分由一个单独的进程（dopusrt.exe）进行管理，Opus 会自动启动该进程（并且如果该进程终止，则会自动重启该进程）。

如果你由于某些原因不希望使用崩溃处理程序（例如，如果该程序本身导致了问题），请将此标志设置为 **False**。
</td></tr><tr><td>

**crash_log_memory**</td><td>


当启用此设置时，自动生成的崩溃日志（也称为“崩溃转储”）将包含进程中的所有内存。当诊断问题时，这可能会更有用，但也会显著增加文件大小以及包含私有数据的可能性。除非技术支持要求你这样做，否则不应该启用此设置。
</td></tr><tr><td>

**debug_icon_data**</td><td>


通常情况下，你不应该修改此设置。技术支持人员可能会要求你启用此设置，以帮助诊断第三方组件生成的图标存在的问题。
</td></tr><tr><td>

**mixed_dpi_mitigations**</td><td>


Windows 有大量错误，这些错误是由使用具有不同 DPI 的多个显示器触发的（不仅是高 DPI 显示器，还有多个屏幕且未将所有屏幕设置为相同缩放比例时）。使用某些 Windows 错误还可能通过更改 DPI 并在不重启的情况下触发。

**mixed_dpi_mitigations** 设置控制 Opus 用于尝试使 Windows 在使用具有多个 DPI 的显示器时正常运行的某些权宜措施。不幸的是，这些权宜措施在解决某些电脑上的问题时可能会导致其他问题。如果关闭了这些权宜措施，则 Windows 错误的主要症状是弹出菜单和工具提示在错误的地方打开，并且非常大或小。当启用这些权宜措施时，会造成轻微的性能损失，如果出现问题，则弹出菜单或工具提示打开或其他意外视觉故障时，屏幕闪烁。

当设置为 *Automatic* 时，Opus 会检测系统是否处于混合 DPI 模式，并在处于该模式时启用权宜措施，而在不处于该模式时避免它们。

此设置仅在 Windows 8.1 及更高版本中可见；更早的操作系统版本不支持具有不同 DPI 的多个显示器。
</td></tr><tr><td>

**mtp_enable**</td><td>


此选项可用于禁用对 MTP（便携式）设备的内部支持。当关闭此选项时，将通过承载的 Windows资源管理器视图访问设备。
</td></tr><tr><td>

**no_external_change_notify**</td><td>


不要监控外部文件更改。这使你可以禁用检测在 Opus 外部发生的更改 - Opus 本身执行的文件操作将被注意到并在文件窗口中反映出来。
</td></tr><tr><td>

**notify_debug**</td><td>


为文件通知输出调试信息。如果你在处理 Opus 没有注意到在 Opus 之外发生的更改的问题时，技术支持人员可能会要求你启用此设置以收集调试信息。

启用此选项将降低性能。除非在调查问题时，否则不要启用此设置，并在完成后将其关闭。

请参阅 [常见问题](https://resource.dopus.com/t/changes-to-folders-are-not-being-detected/1786) 了解更多信息。
</td></tr><tr><td>

**notify_debug_exclude**</td><td>


正则表达式按路径过滤 **notify_debug** 输出。如果定义了此正则表达式，则只有路径（或子字符串）与正则表达式匹配时才会报告该路径。
</td></tr><tr><td>

**notify_debug_include**</td><td>


正则表达式按路径过滤 **notify_debug** 输出。如果定义了此正则表达式，则只有路径（或子字符串）与正则表达式不匹配时才会报告该路径。
</td></tr><tr><td>

**notify_max_time**</td><td>
全局</td><td>

每次文件列表在考虑其他输入和事件之前花费处理来自文件系统更改通知的最高时间量（以毫秒为单位）。

默认为 50 毫秒。在极少数情况下，如果事件生成速度快于消耗速度，则可能需要将其从默认值升高。你还可以指定 0（零）来无限期地处理更改事件，尽管你可能只想将其作为测试执行，而不是作为永久设置。如果将其设置为零或设置得太高，则当生成大量文件系统事件时，文件列表可能不太能对用户输入做出响应。

这是一个全局设置。如果你为一台机器上的一个用户更改它，那么它将影响所有其他用户，这很可能是必需的。在多用户系统上，如果设置由一个用户更改，则其他人将看不到更改，直到他们重新启动 Opus。
</td></tr><tr><td>

**notify_min_items**</td><td>
全局</td><td>

在检查 **notify_max_time** 时间限制之前要处理的最小事件数。请参见上面 **notify_max_time** 的描述，了解你可能希望提高此设置的情况，以及该设置对多个用户如何起作用。
</td></tr><tr><td>

**script_output_level**</td><td>


可让你调整 *脚本日志* (*[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md) / 其他日志*) 中显示的诊断输出类型。

这会影响来自 Opus 本身和插件 DLL 的诊断。始终会显示从调用 **DOpus.Output** 方法的脚本发送到日志的输出。
</td></tr><tr><td>

**script_output_throttle**</td><td>


当启用时，*脚本日志* (*[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md) / 其他日志*) 中显示的诊断输出将抑制重复得太频繁的相同消息。

如果诊断消息被触发得太频繁，则通常应该将其保留为启用状态以防止性能问题。如果你正在处理插件 DLL，并且需要记录重复事件而没有任何事件被丢弃，则关闭它可能会很有用。

这会影响来自 Opus 本身和插件 DLL 的诊断。始终会显示从调用 **DOpus.Output** 方法的脚本发送到日志的输出。
</td></tr><tr><td>

**shellchange_debug**</td><td>


输出 Shell 文件通知的调试信息。如果你在处理 Opus 没有注意到在 Opus 之外发生的更改的问题时，技术支持人员可能会要求你启用此设置以收集调试信息。请参阅 [常见问题](https://resource.dopus.com/t/changes-to-folders-are-not-being-detected/1786) 了解更多信息。
</td></tr><tr><td>

**sync_debug**</td><td>


通常应该将其保留为关闭状态，但你可能会被要求将其启用以调试 [同步工具](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md) 做出的决策。如果你在启用此选项时使用同步工具，则将在桌面上创建一个包含调试信息的
**缩略图调试**

<td>

</td>

<td>

输出缩略图生成的调试信息。技术支持可能会让你打开此开关来收集调试信息。这会降低性能，因此在不需要时应该将其关闭。
</td></tr></tbody>