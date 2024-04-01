# Directory Opus 13 - 详细发行说明

# 其它脚本

## 一般

- 查看 [脚本 IDE](script_ide.zh.md) 以了解新脚本编辑器和管理 UI 的详情。
- 某些脚本更改已在其它部分中提及，而非此处。

------------------------------------------------------------------------

## 系统设置

- 新的 OnSystemSettingChange 事件，在系统设置更改时触发。SystemSettingChangeData.type 提供更改类型：
  - 环境变量更改时为“Environment”。
  - 触摸/鼠标输入模式在操作系统级别更改时为“UserInteractionMode”。
  - Opus 切换到新 UI 间距方案时为“SpacingScheme”，可能是对“UserInteractionMode”的反应。SystemSettingChangeData.name 提供新方案名称。
  - Opus 在暗模式和亮模式之间切换时为“ColorSet”。
  - 系统主题（视觉样式）更改时为“Theme”。
  - 打开或关闭 DWM 组合时为“DWMComposition”。
  - DWM 窗口框架颜色更改时为“DWMColorization”。
  - WM_SETTINGCHANGE 系统消息也会触发此事件，其它类型值由 Microsoft 定义。其中可能包括“WindowMetrics”、“intl”、“Policy”、“ConvertibleSlateMode”、“SystemDockMode”等。
- 如果 Opus 处于暗模式，则 SysInfo.DarkMode 返回 true。
- 如果暗模式在操作系统级别（对于应用程序）启用，则 SysInfo.DarkModeApps 返回 true。
- SysInfo.DPI 返回应用于 Opus 进程的 DPI 缩放。
- SysInfo.SystemDPI 返回当前系统 DPI（如果它在 Opus 启动后更改，则可能有所不同）。
- 如果系统在操作系统级别处于触摸模式，则 SysInfo.TouchInput 返回 true。
- 如果 Opus 从便携式安装（USB Export）运行，则 SysInfo.USBInstall 会告知您。
- DOpus.SpacingScheme 返回 Opus 中当前 UI 间距方案的名称（如果存在）。

------------------------------------------------------------------------

## 路径

- Path 解析方法，类似于较旧的 DOpus.FSUtil.Resolve，但会修改 Path 对象本身。
- Path.Normalize 通过以下方式标准化路径字符串：
  - 将所有正斜杠转换为反斜杠（对于普通路径 - URL 则相反）。
  - 将重复斜杠合并为单个斜杠（除 UNC 路径和 URL 中需要斜杠的情况）。
  - 将字符串分配给 Path 对象时会自动调用 Path.Normalize，因此通常无需手动调用它。
  - Path.ToUNC 从映射的网络驱动器盘符路径转换为 UNC 路径。
  - 现在如果指定了“w”标志，FSUtil.Exists 可以在最终路径组件中指定通配符。
  - FSUtil.PathType 方法会告诉您路径的类型（“shell”、“filesys”、“ftp”、“zip”、“mtp”、“lib”、“coll”、“plugin”）。

------------------------------------------------------------------------

## 日期

- 现在可以通过 JScript Date 对象直接创建 Opus Date 对象。
- Date.Set 方法现在直接接受 Unix 纪元时间。
- 添加了 Date.ToEpochTime() 方法来反向转换。
- 当在添加/减去结果时会导致无效日期（例如，从 31 日的日期中减去 1 个月，而前一个月只有 30 天）时，改进了 Date.Add() 和 Date.Sub() 方法的逻辑。

------------------------------------------------------------------------

## 文件更改通知

- Dialog.WatchDir(\<id\>, \<dir\>, \<flags\>)
  - 允许脚本通过对话框监视文件夹或文件是否有更改。
  - 发送“dirchange”Msg 事件，并将“control”设置为指定的更改 id。
  - \<id\> 是用户分配的 id。
  - \<dir\> 是文件系统文件夹的完整路径，或者如果设置了“i”标志，则为文件。
  - \<flags\> 是：
    - f - 监视文件夹中的文件更改（例如，创建文件）。
    - d - 监视文件夹中的目录更改（例如，创建目录）。
    - r - 递归 - 监视子文件夹。
    - a - 监视文件属性更改。
    - s - 监视文件大小更改。
    - w - 监视上次写入时间更改。
    - i - 监视单个文件而不是文件夹。
- Dialog.CancelWatchDir(\<id\>)
  - 取消由以前的 WatchDir 调用设置的监视。
  - \<id\> 是前一次监视的 ID，或“\*”以取消所有监视。
- FSUtil.WatchChanges 和 FSUtil.CancelWatchChanges 方法允许脚本加载项在没有对话框的情况下监视文件夹或文件是否有更改：
  - 当发生更改时，将触发新的 OnFilesystemChange 事件，并提供 FilesystemChangeData 参数。
  - FilesystemChangeData.id 提供已更改监视器的 ID。
  - 参数与上述 Dialog.WatchDir 和 CancelWatchDir 中的参数相同。

------------------------------------------------------------------------

## 任务栏通知

- DOpus.Notify(\<title\>, \<msg\>, \<flags\>)
  - 显示系统通知，在屏幕的角落。
  - \<title\> 和 \<msg\> 是显示给用户的文本字符串。
  - 如果 \<flags\> 是“n”，表示通知不会触发声音。
- Dialog.NotifyIcon(\<method\>,\<arguments...\>)
  - 允许脚本对话框向系统任务栏通知区域添加一个图标。
  - 每个对话框仅支持一个图标。
  - \<method\> 是以下之一：
    - “add” - 添加图标。参数：\<icon\>、\<tooltip\>。
    - “update” - 更新图标或工具提示。参数：\<icon\>、\<tooltip\>
    - “remove” - 移除图标。（无参数。）
    - “notify” - 显示通知消息。参数：\<title\>、\<msg\>、\<flags\>，与上述 DOpus.Notify 相同。
  - 对于“add”，如果对话框已分配了“icon”和“title”属性，则 \<icon\> 和 \<tooltip\> 均可选。
  - 对于“update”，\<icon\> 和 \<tooltip\> 均可选。
  - 对于“notify”，\<flags\> 是可选的。
  - 任务栏图标上的鼠标事件会生成“click”、“dblclk”和“rclick”Msg 事件，control 属性设置为“notifyicon”。
  - 该图标在对话框关闭时自动删除。

------------------------------------------------------------------------

## 对话框

- Msg.buttons 属性告诉您生成消息时按下哪些鼠标按钮（“left”、“right”、“middle”）。
- 新标记文本控件允许对话框使用基本标记，包括超链接、粗体、斜体和字体颜色。
  - 通过对话框编辑器添加。
  - 标记属性可以设置为显示信息、帮助、警告或链接，以在控件的左侧显示不同的图标。
  - 超链接会生成 Msg“click”事件。Msg.value 具有链接 ID（当单个控件有多个链接时）。
- 允许两个或多个共享对话框宽度或高度的控件的新“共享宽度”和“共享高度”调整大小选项。
- 标记和静态文本控件的新“文本”调整大小选项。
  - 与“宽度”调整大小相结合时，会使控件自动调整其高度，以便根据需要显示整个文本。
  - 下面的控件会自动向上或向下移动。
- 编辑控件具有新的“cuetext”属性，允许您在运行时获取或设置其提示文本。
  - 现在空编辑控件在获得焦点时会继续显示其提示文本，直到输入内容为止。
- 可以使用 Dialog.title 属性在运行时更改对话框标题。
- 可以使用 Control.label 属性在运行时更改标签页控件标记。（例如，`Control.label(0) = "tab 1";`）
- Control.style 现在适用于标签页控件中的对话框。
- 修复了对话框编辑器语言覆盖。

------------------------------------------------------------------------

## 过滤对象

- 新的过滤对象用于处理过滤器，例如工具>查找文件>高级中使用的过滤器。
- DOpusFactory.Filter() -- 方法。创建新的过滤对象。
- Item.MatchFilter() -- 方法。根据过滤器测试文件或文件夹。
- Command.SetFilter() -- 方法。将过滤器与 Command 对象关联。
- Command.ClearFilter() -- 方法。移除之前关联的过滤器。
- 脚本可以通过运行“选择 FILTER”命令来使用关联的过滤器。
- 脚本还可以运行“Select FILTERDEF ...”以在命令行定义过滤器。（在其它地方有更详细的描述。）

------------------------------------------------------------------------

## 变化

- 添加了“duration”和“durationh”脚本列类型。将提供的（整数）值显示为持续时间：
  - 值表示秒数。
  - “duration”仅在值足够大时才显示小时。
  - “durationh”始终显示小时，即使它们为零。
- Vector.Reverse() -- 方法。反转元素的顺序。
- Tab.dest -- 属性。如果该标签页是目标，则返回 true。
  - 在某些情况下，标签页既不是源头也不是目标，因此仅使用“source”属性有时是不够的。
  - 对于非活动（隐藏）标签页，Tab.source 和 Tab.dest 现在始终为 false。（以前，非活动标签页从上次活动的标签页中返回过时的信息。）
- DOpus.文件窗口s.ToFront() -- 方法。将一个或多个窗口移至最前。
  - 接受窗口句柄或窗口句柄的向量。
  - 最后一个窗口将位于其它窗口的顶部。其余的将堆叠在它下面，按相反的顺序。
-文件窗口.WindowState -- 属性。提供窗口状态（“min”、“max”、“hidden”、“normal”）。
-文件窗口.ViewPaneFile -- 属性。提供当前查看器窗格中（如果有）的文件路径。
- Viewer.Parent文件窗口-- 属性。提供启动了独立查看器的列表（如果有）。
- Viewer.Parent文件窗口Linked -- 属性。如果查看器与列表相关联，则返回 true。（请参阅 [查看器](#查看器)，列表相关联的查看器。）
- Format.group_by -- 属性。现在适用于脚本列。
- Item.nested -- 属性。如果文件或文件夹位于展开的文件夹下，则为 True。（请参阅 [文件列表](#文件列表)，可展开文件夹。）
- ItemCollection.RemoveNested() -- 方法。从集合中移除所有嵌套项，并返回已移除项的数目。
- 收藏对象：
  - 当使用“sep”关键字添加新分隔符时，标题文本可以写成“sep:标题文本”。
  - 分隔符项具有 SetHeading() 方法，可用来修改标题。
- StringTools.LanguageStr -- 方法。返回字符串的翻译版本。（仅适用于支持的字符串。）
- StringTools.MakeLegal -- 方法。替换文件名或路径中无效的字符。
- StringTools.RemoveDiacritics() -- 方法。从字符串中的字符中移除重音符号等内容：
  - 类似于 Opus 中模式匹配的“忽略重音符号”选项。
  - 接受字符串并返回字符串的新版本。
  - 示例（JScript）：\<WRAP\>

    function OnClick(clickData)
    {
        var st = DOpus.Create.StringTools();
        for (var eSel = new Enumerator(clickData.func.sourcetab.files); !eSel.atEnd(); eSel.moveNext())
        {
            var conv = st.RemoveDiacritics(eSel.item().Name);
            DOpus.Output('"' + eSel.item().Name + '" -> "' + conv + '"');
        }
    }

\</WRAP\>

- StringTools.Truncate -- 方法。将字符串或路径截断为指定的宽度。
- QuickFilter.flatview -- 属性。告诉您是开启还是关闭了 Flat View 文件夹的过滤。
  - 旧的 QuickFilter.overrideflatview 属性保留以实现兼容性，但可能不太有用。它只告诉您是否覆盖了全局配置设置，但没有告诉您配置设置或最终结果实际上是什么。
  - 新的属性直接给您最终结果。
- 现在可以将传递给 Command.AddFiles、Command.SetFiles、DOpus.SetClip 和 Dialog.Drag 的文件列表包含在全路径字符串的 StringSet 或 UnorderedSet 中。
- FSUtil.Hash 现在支持“blake3”作为哈希方法。
- 脚本 clickData.func.sourcetab.lister.utilpage -- 现在返回“ScriptLog”以供脚本日志使用。
- 在 JScript 中（但不在 VBScript 中），现在可以使用方括号和圆括号对集合进行索引。例如，DOpus.文件窗口s\[0\].activetab 的作用与 DOpus.文件窗口s(0).activetab 相同。
- GetNewNameData.tab 为重命名脚本提供启动重命名命令的标签页（即列表）。如果不存在标签页，则返回 false。
- 当某个标签页变为活动标签页，因为另一个标签页被关闭，现在将同步触发 OnActivateTab 方法，因此“oldtab”值保持有效。
- 添加了 ActivateTabData.closing 属性，当激活更改是由于旧标签页关闭时，该属性变为 True。
- 现在，脚本可以使用标准 LoadImage 函数从 DLL 和 EXE 中提取图标。
- 现在，脚本可以访问内部图标图像。传递带有＃前缀的图标名称（例如“#copy”）。默认情况下，返回大尺寸；对于小尺寸，请使用“#0:name”。您还可以使用“#set:icon”或“#0:set:icon”指定特定集。
- 现在可以要求 DOpus.GetClipFormat 区分通过复制放置到剪贴板的文件和通过剪切放置的文件。
- 如果给 FSUtil: Exists、GetType 和 PathType 方法提供涉及加密压缩包的路径，它们将不再触发密码提示。

------------------------------------------------------------------------

下一篇：[已删除](/Manual/release_history/opus13_detailed/removed.zh.md)