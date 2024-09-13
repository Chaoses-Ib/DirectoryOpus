# DOpus

**DOpus** 对象是由 Opus 提供的两个全局脚本对象之一，*所有* 脚本均能使用。它提供了各种助手方法和集合，让你可以访问列表程序和工具栏等内容。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
aliases</td><td>

*object:***[Aliases](aliases.zh.md)**</td><td>

**[Aliases](aliases.zh.md)**对象授予脚本对定义的 [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)的访问权限。
</td></tr><tr><td>
favoriteformats</td><td>

*collection*:**[Format](format.zh.md)**</td><td>

返回一个 **[Format](format.zh.md)** 对象集合，该集合表示已使用定义的收藏夹格式。
</td></tr><tr><td>
favorites</td><td>

*object:***[Favorites](favorites.zh.md)**</td><td>

返回一个 **[Favorites](favorites.zh.md)** 对象，它允许你查询和修改用户定义的收藏夹文件夹。
</td></tr><tr><td>
filetypegroups</td><td>

*object*:**[FiletypeGroups](filetypegroups.zh.md)**</td><td>

返回一个 **[FiletypeGroups](filetypegroups.zh.md)** 对象，它让你可以列举和查询已配置的 [文件类型组](/Manual/file_types/file_type_groups.zh.md)。
</td></tr><tr><td>
filters</td><td>

*object:***[GlobalFilters](/Manual/basic_concepts/folder_options/folder_options_dialog/filters.zh.md)**</td><td>

返回一个 **[GlobalFilters](globalfilters.zh.md)** 对象，它允许你访问关于全局过滤器设置的信息（在配置中的 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面上配置）。
</td></tr><tr><td>
language</td><td>

*string*</td><td>
返回一个表示当前用户界面语言的字符串。
</td></tr><tr><td>
listers</td><td>

*object:***[Listers](listers.zh.md)**</td><td>

返回一个 **[Listers](listers.zh.md)** 对象，它表示任何当前打开的列表程序窗口（每个窗口都由 **[文件窗口](lister.zh.md)** 对象表示）。
</td></tr><tr><td>
smartfavorites</td><td>

*object:***[智能收藏夹](smartfavorites.zh.md)**</td><td>

返回一个 **[智能收藏夹](smartfavorites.zh.md)** 对象，它允许你查询 [智能收藏夹](/Manual/basic_concepts/the_lister/navigation/smartfavorites.zh.md) 数据。
</td></tr><tr><td>
spacingscheme</td><td>

*string*</td><td>

返回当前 [UI 间距方案](/Manual/preferences/preferences_categories/user_interface/spacing.zh.md) 的名称（如果有的话）。
</td></tr><tr><td>
strings</td><td>

*object:***[ScriptStrings](scriptstrings.zh.md)**</td><td>

返回一个 **[ScriptStrings](scriptstrings.zh.md)** 对象，它允许脚本访问任何定义为 [字符串资源](/Manual/scripting/resources/string_resources.zh.md) 的字符串。
</td></tr><tr><td>
tabgroups</td><td>

*object:***[TabGroups](tabgroups.zh.md)**</td><td>

返回一个 **[TabGroups](tabgroups.zh.md)** 对象，它允许脚本访问和操作已配置的 [文件夹标签页组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md)。
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.zh.md)**</td><td>

这个 **[Vars](vars.zh.md)** 对象表示所有已定义的 *全局作用域* 变量。
</td></tr><tr><td>
version</td><td>

*object:***[Version](version.zh.md)**</td><td>

**[Version](version.zh.md)** 对象提供有关当前 Opus 程序版本的信息。
</td></tr><tr><td>
viewers</td><td>

*object:***[Viewers](viewers.zh.md)**</td><td>

返回一个 **Viewers** 对象，该对象表示任何当前打开的 [独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md)（每个都由 **[Viewer](viewer.zh.md)** 对象表示）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**Arguments**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
ClearOutput</td><td>

*none*</td><td>

*none*</td><td>
清除脚本输出日志。
</td></tr><tr><td>
Create</td><td>

*none*</td><td>

*object:***[DOpusFactory](dopusfactory.zh.md)**</td><td>

创建并返回一个新的 **[DOpusFactory](dopusfactory.zh.md)** 对象，它可用于创建各种轻量级助手对象，如 **[Blob](blob.zh.md)**、**[Map](map.zh.md)** 和 **[Vector](vector.zh.md)**。
</td></tr><tr><td>
Delay</td><td>

\<int:time\></td><td>

*none*</td><td>
延迟指定毫秒数后再返回。
</td></tr><tr><td>
Dlg</td><td>

*none*</td><td>

*object:***[Dialog](dialog.zh.md)**</td><td>

创建一个新的 **[Dialog](dialog.zh.md)** 对象，让你可以显示对话框和弹出菜单。

**注意：** 脚本通常不应在响应由工具栏或文件夹标签页触发的事件时使用此方法。**DOpus.Dlg** 返回的 **Dialog** 不会配置其父窗口。大多数脚本事件会为你提供一个对象，该对象既可以创建预配置的 **Dialog**，也可以包括 **SourceTab** 属性或类似属性（做同样的事情）。在几乎所有情况下，你都应该使用它们。
</td></tr><tr><td>
DPI</td><td>

*none*</td><td>

*object:***[DPI](dpi.zh.md)**</td><td>

创建 **[DPI](dpi.zh.md)** 助手对象，它在处理不同的系统缩放设置（如高 DPI 监视器）时提供帮助。
</td></tr><tr><td>
FSUtil</td><td>

*none*</td><td>

*object:***[FSUtil](fsutil.zh.md)**</td><td>

创建一个新的 **[FSUtil](fsutil.zh.md)** 对象，它提供用于访问文件系统的助手方法。
</td></tr><tr><td>
GetClip</td><td>

*none*  
或 \<string:type\></td><td>

*string*  
或 *object:***[Items](items.zh.md)**</td><td>

检索系统剪贴板的当前内容（如果它包含文本或文件）。

你可以通过传递 **"text"** 或 **"files"** 来控制返回的类型，具体取决于 *\<type\>* 参数 - 如果可能，Opus 将转换为请求的类型。

如果未指定 *\<type\>*，内容将以其本机格式返回。
</td></tr><tr><td>
GetClipFormat</td><td>

*none* 或 \<string:flags\></td><td>

*string*</td><td>

返回一个字符串，指示剪贴板内容的本机格式。

可选标志：

|       |                                            |
|-------|--------------------------------------------|
| **c** | 区分剪切和复制的文件 |

可能返回值：

|                  |                                                      |
|------------------|------------------------------------------------------|
| **files**        | 文件，如果 **flags** 省略或不包含 **c** |
| **files_copy**   | 通过复制（Ctrl-C）获取的文件，如果 **flags** 包含 **c** |
| **files_cut**    | 通过剪切（Ctrl-X）获取的文件，如果 **flags** 包含 **c**  |
| **image**        | 位图数据                                          |
| **text**         | 文本数据                                            |
| \<empty string\> | 空剪贴板，或任何其它类型的数据           |
</td></tr><tr><td>
GetListers</td><td>

*none*  
or \<string:flags\></td><td>

*object:***[Listers](listers.zh.md)**</td><td>

返回一个 **[Listers](listers.zh.md)** 对象，它表示任何当前打开的列表程序窗口（每个窗口都由 **[Lister](lister.zh.md)** 对象表示）。这与使用 **listers** 属性相同，只不过你可以指定可选标志：
|       |                                                                              |
|-------|------------------------------------------------------------------------------|
| **c** | 当前桌面。仅返回当前桌面中的文件窗口。                 |
</td></tr><tr><td>
GetQualifiers</td><td>

*无*</td><td>

*string*</td><td>

返回一个表示当前按下的限定键的字符串。如无按下的限定键，字符串为“**无**”。否则，字符串可包含下列任意或全部内容，内容以逗号分隔：“**shift**”、“**ctrl**”、“**alt**”、“**lwin**”、“**rwin**”。

请注意，许多事件会传递给您类似的限定键列表。如果您传递的是限定键列表，则通常应使用该列表而不是调用 DOpus.GetQualifiers。

例如，传递给脚本命令一个包含 *限定 *属性的 **[Func](func.zh.md)** 对象。该属性会告诉您在触发命令时按下了哪些键，这可能与几秒钟后按下的键不同。当用户单击按钮运行命令时，他们通常希望命令使用他们单击时按下的键，而不是在等待命令完成时稍后按下的键。

类似地，**[OnBeforeFolderChange](../scripting_events/onbeforefolderchange.zh.md)** 等事件通常会向您传递一个包含 *限定* 属性的对象（例如 **[BeforeFolderChangeData](beforefolderchangedata.zh.md)**），当触发事件时，该属性指示键的状态。通常，您应该使用该属性，而不是调用 DOpus.GetQualifiers。

如果您确实调用了 DOpus.GetQualifiers，通常希望尽快调用它，然后存储结果，这样，用户在触发脚本后松开某个键的时间就会缩短。

如果您多次调用 DOpus.GetQualifiers，由于在调用之间按下或松开了某个键，每次可能会得到不同的结果。如果需要进行多次检查且需要这些检查保持一致，请调用一次该命令并存储结果。这通常不会影响前面提到的 *qualifiers* 属性，因为它们通常存储键状态的快照。
</td></tr><tr><td>
LoadImage</td><td>

\<string:filename\> 或 \<object:**[Blob](blob.zh.md)**\>  
\[\<int:width\>\]  
\[\<int:height\>\]  
\[\<bool:alpha\>\]</td><td>

object:**[Image](image.zh.md)**</td><td>

从指定的文件加载图像文件。可以选择指定要加载图像的所需大小，以及是否加载 Alpha 通道（如果有的话）。

可以使用 “#iconname” 从内部图标集中加载图标。例如，`#copy` 将从默认集中加载复制图像。默认情况下返回较大的尺寸；对于较小的尺寸，请使用 `#0:iconname`。您还可以使用 `#setname:iconname` 或 `#0:setname:iconname` 指定特定的图标集。

可以通过附加图标索引到文件名，从 DLL 和 EXE 中提取图像，例如 `/system/zipfldr.dll,1`。

您还可以提供包含图像数据而不是文件名的 **[Blob](blob.zh.md)** 对象。

返回的 **[Image](image.zh.md)** 对象可以作为脚本对话框（当该控件处于“图像”模式时）中静态控件的 **[Control](control.zh.md).label** 属性的值（请参见 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)）。您还可以将其指定为 **[Dialog](dialog.zh.md)** 对象的 **icon** 属性，以便为脚本对话框指定自定义窗口图标。
</td></tr><tr><td>
LoadThumbnail</td><td>

\<string:filename\>  
\[\<int:timeout\>\]  
\[\<int:width\>\]  
\[\<int:height\>\]  
\[\<string:flags\>\]</td><td>

object:**[Image](image.zh.md)**  
或  
*bool* (**False**)</td><td>

从指定的外部文件中提取缩略图。可以选择指定超时（以毫秒为单位）和要加载缩略图的所需大小。

可选的 **flags** 值支持以下标志（作为字符串提供）：

|       |                                                                                                                                                                 |
|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **i** | 阻止 Opus 等待可能需要一段时间才能生成的缩略图，而是在无法立即生成缩略图时返回大图标 |
| **c** | 将 **i** 标志修改为仅应用于云存储文件夹                                                                                                  |

如果加载失败（或在可以生成缩略图之前超时），此方法会返回 **False**。

返回的 **[Image](image.zh.md)** 对象可以作为脚本对话框（当该控件处于“图像”模式时）中静态控件的 **[Control](control.zh.md).label** 属性的值（请参见 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)）。您还可以将其指定为 **[Dialog](dialog.zh.md)** 对象的 **icon** 属性，以便为脚本对话框指定自定义窗口图标。
</td></tr><tr><td>
MusicGenres</td><td>

*无*</td><td>

object:**[Vector](vector.zh.md)**</td><td>

返回一个由字符串组成的 [Vector](vector.zh.md) ，表示在元数据面板的流派字段中配置为显示的音乐流派。
</td></tr><tr><td>
Notify</td><td>

\<string:title\>  
\<string:message\>  
\[\<string:flags\>\]</td><td>

*无*</td><td>

显示系统通知（或在 Windows 7 中显示气泡工具栏）。这要求将 Opus 任务栏图标添加到任务栏通知区域，因此，如果在配置中将其关闭，它会暂时添加，然后再次删除。

可选标志为：

|       |                                                                                        |
|-------|----------------------------------------------------------------------------------------|
| **n** | 无声音。阻止系统在显示通知时播放声音。                                |
</td></tr><tr><td>
Output</td><td>

\<string:text\>  
\[\<bool:error\>\]  
\[\<bool:timestamp\>\]</td><td>

*无*</td><td>

将指定文本字符串打印到脚本输出日志（可在下列位置找到： [实用面板、](/Manual/basic_concepts/the_lister/utility_panel.zh.md) 脚本模式下的 [CLI](/Manual/additional_functionality/cli.zh.md)，*重命名* 对话框和脚本模式下的 *命令编辑器*）。

如果提供了第二个参数并将其设置为 **True**，则消息将显示为错误。这意味着文本将显示为红色，并且如果当前没有打开的日志窗口，文件窗口状态栏中将闪烁一个警告图标，以提醒用户存在错误情况。

如果提供了可选的第三个参数并将其设置为 **True**，则会为日志消息加上一个时间戳。时间戳仅出现在实用面板中，而不是出现在命令编辑器的输出面板等位置。错误消息始终带有时戳，因此，如果第二个参数为 **True**，则会忽略第三个参数
</td></tr><tr><td>
ReloadScript</td><td>

\<string:file\></td><td>

*无*</td><td>

导致 Opus 重新加载并重新初始化指定的脚本。您必须提供磁盘上的脚本完整路径（如果脚本加载项要重新加载自身，您可以传递 **[Script](script.zh.md).file** 属性的值）。
</td></tr><tr><td>
SendKey</td><td>

\<string:key\></td><td>

*bool*</td><td>

发送指定的击键到系统。该击键将发送到当前具有焦点的任何窗口。例如，`DOpus.SendKey("win+v");` 向系统发送 <kbd>Win</kbd>+<kbd>V</kbd> 键，该键会打开 Windows 剪贴板查看器。

支持的限定键为 `shift`, `ctrl`, `alt` 以及 `win`。

除了字母和数字，还支持以下命名键：`backspace`, `capslock`, `delete`, `down`, `end`, `enter`, `escape`, `home`, `insert`, `left`, `numlock`, `pagedown`, `pageup`, `pause`, `printscr`, `right`, `scrlock`, `space`, `tab`, `up`。
</td></tr><tr><td>
SetClip</td><td>

\<string:text\>  
或 *object:***[Items](items.zh.md)**  
或 *none*</td><td>

*none*</td><td>

将指定文本或 **[Items](items.zh.md)** 对象（或类似对象，见下文）放入系统剪贴板。如果以无参数方式调用，则将清除剪贴板。

传递文件列表时，还可以给出一个 **[Vector](vector.zh.md)** **[Item](item.zh.md)** 或 **[Path](path.zh.md)** 对象，或完整路径字符串（而不是集合）。或者也可以给出一个 **[StringSet](stringset.zh.md)** 或 **[UnorderedSet](unorderedset.zh.md)** 完整路径字符串。
</td></tr><tr><td>
Toolbars</td><td>

\<string:type\></td><td>

object:**[Toolbars](toolbars.zh.md) **</td><td>

返回一个 **[Toolbars](toolbars.zh.md)** 对象，该对象可以枚举所有已定义的工具栏（无论它们当前是否打开）。

你可以通过指定可选的 *type* 参数将此对象限制为仅返回正在使用的工具栏 - 指定 **"listers"** 以仅返回目前在文件窗口中打开的工具栏，指定 **"docks"** 以仅返回当前浮动的工具栏。
</td></tr><tr><td>
TypeOf</td><td>

*any*</td><td>

*string*</td><td>
返回一个字符串，指示对象或变量的类型。
</td></tr></tbody>