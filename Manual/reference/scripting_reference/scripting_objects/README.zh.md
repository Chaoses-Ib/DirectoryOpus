# 脚本对象

脚本可以使用许多不同的对象与 Opus 进行交互。例如，**文件窗口** 对象表示一个物理 [文件窗口](/Manual/basic_concepts/the_lister/README.zh.md) 窗口，向脚本提供有关该文件窗口的信息，并允许脚本修改或控制该文件窗口。

一个对象有两个主要类型的接口可以调用：

- *属性*使脚本能够查询（有时还会设置）一个简单值。例如，**文件窗口** 对象具有一个 **title** 属性，该属性使脚本能够检索文件窗口窗口的标题字符串。
- *方法*是对象提供的函数，脚本可以调用它们来执行任务。例如，**DOpus** 对象有一个 **Output** 方法，该方法使脚本能够向脚本日志中输出一个文本字符串。

属性和方法之间的主要区别是，方法可以（但并不总是）接受修改其行为的参数，并且不必（但通常会）返回结果。

## 变量类型

返回结果的属性和方法可以返回许多不同类型的变量，方法通常使用一个或多个参数，这些参数也可以是多种类型。ActiveX 脚本语言通常是 *无类型的* - 也就是说，不必预先定义变量的类型，并且从一种类型转换为另一种类型通常（但并非总是）自动进行。Opus 脚本主要使用以下类型的变量：

- *Int* - 一个整数（有符号；有效范围为 -2147483648 到 2147483647）。
- *Currency* - 这是一个标准的变体类型，并且仅在需要比 *Int* 能够容纳的更大的数字的少数情况下使用它（不幸的是，ActiveX 脚本并不总是支持 64 位整数类型）。
- *Decimal* - 一个无符号的 64 位值（最大值为 18,446,744,073,709,551,616）。并非所有语言都支持此功能 - JScript 支持，但 VBScript 不支持。
- *String* - 一个文本字符串
- *Bool* - 一个布尔值（**True** 或 **False**）
- *Date* - 一个日期/时间值
- *Collection* - 一个集合，其中包含多个（通常）相同类型的对象。在一些语言中（例如，在 VBScript 中，使用 *For Each* 构造）中，可以轻松枚举集合。仅由 Opus 返回集合 - 与数组（或 Vector 对象）不同，它们永远不会被直接创建或修改（尽管在某些情况下可以使用一些脚本方法来修改它们）。例如，**Tab** 对象有一个名为 **selected** 的属性，它表示该标签页中当前选择的所有项 - 它是一个项的 *集合*。
- *Object* - 一个具有已定义方法和属性的 Opus 脚本对象（如下所列的对象类型之一）。某些对象既可以是对象，又可以是集合 - 也就是说，它们具有方法和属性，但也可以像集合一样进行枚举。某些对象还具有一个 *默认值* - 也就是说，仅使用对象名称而不使用任何方法或属性将返回它们自己的值。例如，**Metadata** 对象的默认值是一个表示可用主要元数据类型的字符串。还可以使用特殊 **def_value** 属性名称引用对象的默认值。
- *Variant* - 任何类型的变量（这与几个对象一起使用 - 例如，**Var** 对象可以存储一个变体）

## 全局对象

Opus 在通过 Opus 调用脚本时为脚本提供了两个作为全局变量的对象：

- **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.zh.md)**: 此**对象可供 *所有* 脚本使用。它提供了各种辅助方法和集合，可用于访问诸如文件窗口和工具栏之类的对象。
- **[Script](/Manual/reference/scripting_reference/scripting_objects/script.zh.md)**: 当调用其各种事件处理程序时，此**对象将提供给 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)**。它提供了与脚本本身相关的信息。

## 事件对象

Opus 在脚本中的一个方法中提供许多对象作为参数。例如，当调用 [脚本函数](/Manual/scripting/script_functions.zh.md)（例如，单击按钮时），Opus 将调用其 **OnClick** 方法，并向其传递一个 **ClickData** 对象。

- **[AboutData](/Manual/reference/scripting_reference/scripting_objects/aboutdata.zh.md)**: 此对象提供给 **[OnAboutScript](scripting_events/onaboutscript.zh.md)** 方法，该方法在用户单击 **[脚本管理](/Manual/scripting/script_management/README.zh.md)** 对话框中某个脚本的 *关于* 按钮时调用。
- **[Activate文件窗口Data](/Manual/reference/scripting_reference/scripting_objects/activatelisterdata.zh.md)**: 此对象提供给 **[OnActivate文件窗口](scripting_events/onactivatelister.zh.md)** 方法，该方法在文件窗口窗口被激活或取消激活时调用。
- **[ActivateTabData](/Manual/reference/scripting_reference/scripting_objects/activatetabdata.zh.md)**: 此对象提供给 **[OnActivateTab](scripting_events/onactivatetab.zh.md)** 方法，该方法在标签页被激活时调用。
- **[AddCmdData](/Manual/reference/scripting_reference/scripting_objects/addcmddata.zh.md)**: 此对象提供给 **[OnAddCommands](scripting_events/onaddcommands.zh.md)** 方法，该方法允许脚本 [添加新的内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)。
- **[AddColData](/Manual/reference/scripting_reference/scripting_objects/addcoldata.zh.md)**: 此对象提供给 **[OnAddColumns](scripting_events/onaddcolumns.zh.md)** 方法，该方法允许脚本 [添加新的信息列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。
- **[AfterFolderChangeData](/Manual/reference/scripting_reference/scripting_objects/afterfolderchangedata.zh.md)**: 此对象提供给 **[OnAfterFolderChange](scripting_events/onafterfolderchange.zh.md)** 方法，该方法在读取新文件夹后调用。
- **[BeforeFolderChangeData](/Manual/reference/scripting_reference/scripting_objects/beforefolderchangedata.zh.md)**: 此对象提供给 **[OnBeforeFolderChange](scripting_events/onbeforefolderchange.zh.md)** 方法，该方法在读取新文件夹之前调用。
- **[ClickData](/Manual/reference/scripting_reference/scripting_objects/clickdata.zh.md)**: 此对象提供给 **[OnClick](scripting_events/onclick.zh.md)** 方法，该方法在每次调用 [脚本函数](/Manual/scripting/script_functions.zh.md)（例如，单击按钮或按下热键）时调用。
- **[Close文件窗口Data](/Manual/reference/scripting_reference/scripting_objects/closelisterdata.zh.md)**: 此对象提供给 **[OnClose文件窗口](scripting_events/oncloselister.zh.md)** 方法，该方法在文件窗口关闭之前调用。
- **[CloseTabData](/Manual/reference/scripting_reference/scripting_objects/closetabdata.zh.md)**: 此对象提供给 **[OnCloseTab](scripting_events/onclosetab.zh.md)** 方法，该方法在标签页关闭之前调用。
- **[ConfigChangeData](/Manual/reference/scripting_reference/scripting_objects/configchangedata.zh.md)**: 此对象提供给 **[OnScriptConfigChange](scripting_events/onscriptconfigchange.zh.md)** 方法，当用户编辑脚本的配置时，该方法会通知脚本。
- **[DisplayModeChangeData](/Manual/reference/scripting_reference/scripting_objects/displaymodechangedata.zh.md)**：此对象传递给 **[OnDisplayModeChange](scripting_events/ondisplaymodechange.zh.md)** 方法，此方法在标签页中显示模式发生更改时调用。
- **[DoubleClickData](/Manual/reference/scripting_reference/scripting_objects/doubleclickdata.zh.md)**：此对象传递给 **[OnDoubleClick](scripting_events/ondoubleclick.zh.md)** 方法，此方法在文件或文件夹双击时调用。
- **[FileOperationCompleteData](/Manual/reference/scripting_reference/scripting_objects/fileoperationcompletedata.zh.md)**：此对象传递给 **[OnFileOperationComplete](scripting_events/onfileoperationcomplete.zh.md)** 方法，可让你在某些文件操作完成后接收到通知。
- **[FilesystemChangeData](/Manual/reference/scripting_reference/scripting_objects/filesystemchangedata.zh.md)**：此对象传递给 **[OnFilesystemChange](scripting_events/onfilesystemchange.zh.md)** 方法，即通过 **[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.zh.md).WatchChanges** 方法建立文件或文件夹更改的监控之后。
- **[FlatViewChangeData](/Manual/reference/scripting_reference/scripting_objects/flatviewchangedata.zh.md)**：此对象传递给 **[OnFlatViewChange](scripting_events/onflatviewchange.zh.md)** 方法，此方法在标签页中平面视图模式发生更改时调用。
- **[GetCopyQueueNameData](/Manual/reference/scripting_reference/scripting_objects/getcopyqueuenamedata.zh.md)**：此对象传递给 **[OnGetCopyQueueName](scripting_events/ongetcopyqueuename.zh.md)** 事件，此事件在每次使用自动管理的复制队列开始复制操作时调用。
- **[GetCustomFieldData](/Manual/reference/scripting_reference/scripting_objects/getcustomfielddata.zh.md)**：此对象传递给 **[OnGetCustomFields](scripting_events/ongetcustomfields.zh.md)** 事件，此事件可让 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md) 将其自己的字段添加到 *重命名* 对话框。
- **[GetNewNameData](/Manual/reference/scripting_reference/scripting_objects/getnewnamedata.zh.md)**：此对象传递给 **[OnGetNewName](scripting_events/ongetnewname.zh.md)** 方法，此方法是 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md) 可以提供的受支持方法之一。
- **[文件窗口ResizeData](/Manual/reference/scripting_reference/scripting_objects/listerresizedata.zh.md)**：此对象传递给 **[On文件窗口Resize](scripting_events/onlisterresize.zh.md)** 事件，此事件在文件窗口窗口每次调整大小时调用。
- **[文件窗口UIChangeData](/Manual/reference/scripting_reference/scripting_objects/listeruichangedata.zh.md)**：此对象传递给 **[On文件窗口UIChange](scripting_events/onlisteruichange.zh.md)** 方法，此方法在文件窗口中打开或关闭各种用户界面元素（树、查看器等）时调用。
- **[Open文件窗口Data](/Manual/reference/scripting_reference/scripting_objects/openlisterdata.zh.md)**：此对象传递给 **[OnOpen文件窗口](scripting_events/onopenlister.zh.md)** 方法，此方法在新文件窗口打开时调用。
- **[OpenTabData](/Manual/reference/scripting_reference/scripting_objects/opentabdata.zh.md)**：此对象传递给 **[OnOpenTab](scripting_events/onopentab.zh.md)** 方法，此方法在新标签页打开时调用。
- **[ScriptColumnData](/Manual/reference/scripting_reference/scripting_objects/scriptcolumndata.zh.md)**：此对象传递给用于将新列添加到 Opus 的 [脚本指定的方法](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。
- **[ScriptCommandData](/Manual/reference/scripting_reference/scripting_objects/scriptcommanddata.zh.md)**：此对象传递给用于向 Opus [添加新**内部**命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 的 [脚本指定的方法](scripting_events/onscriptcommand.zh.md)。
- **[Script即时查找CommandData](/Manual/reference/scripting_reference/scripting_objects/scriptfaytcommanddata.zh.md)**：此对象传递给用于 [扩展即时查找字段](/Manual/scripting/example_scripts/extending_the_fayt.zh.md) 的 [脚本指定的方法](scripting_events/onscriptcommand.zh.md)。
- **[ScriptInitData](/Manual/reference/scripting_reference/scripting_objects/scriptinitdata.zh.md)**：此对象传递给 **[OnInit](scripting_events/oninit.zh.md)** 方法，此方法在 *脚本加载项* 文件夹中初始化每个脚本时调用一次。
- **[ShutdownData](/Manual/reference/scripting_reference/scripting_objects/shutdowndata.zh.md)**：此对象传递给 **[OnShutdown](scripting_events/onshutdown.zh.md)** 方法，此方法在 Opus 关闭之前调用。
- **[SourceDestData](/Manual/reference/scripting_reference/scripting_objects/sourcedestdata.zh.md)**：此对象传递给 **[OnSourceDestChange](scripting_events/onsourcedestchange.zh.md)** 方法，此方法在标签页的源或目标状态发生更改时调用。
- **[StartupData](/Manual/reference/scripting_reference/scripting_objects/startupdata.zh.md)**：此对象传递给 **[OnStartup](scripting_events/onstartup.zh.md)** 方法，此方法在 Opus 启动时调用。
- **[StyleSelectedData](/Manual/reference/scripting_reference/scripting_objects/styleselecteddata.zh.md)**：此对象传递给 **[OnStyleSelected](scripting_events/onstyleselected.zh.md)** 方法，此方法在文件窗口中选择新 [样式](/Manual/basic_concepts/the_lister/styles.zh.md) 时调用。
- **[SystemSettingChangeData](/Manual/reference/scripting_reference/scripting_objects/systemsettingchangedata.zh.md)**：此对象传递给 **[OnSystemSettingChange](scripting_events/onsystemsettingchange.zh.md)** 方法，此方法在各种系统设置发生更改时调用。
- **[TabClickData](/Manual/reference/scripting_reference/scripting_objects/tabclickdata.zh.md)**：此对象传递给 **[OnTabClick](scripting_events/ontabclick.zh.md)** 事件，此事件在按住限定符键时单击标签页时调用。
- **[ViewerEventData](/Manual/reference/scripting_reference/scripting_objects/viewereventdata.zh.md)**：此对象传递给 **[OnViewerEvent](scripting_events/onviewerevent.zh.md)** 事件，此事件在独立 [图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中发生某些事件时调用。

## 其它对象

其余对象全部使用上面列出的对象提供的属性或方法来获取。例如，**文件窗口** 对象是使用 **DOpus.listers** 集合属性获取的，并且 **Vector** 对象是使用 **DOpusFactory.Vector** 方法获取的。

- **[Alias](/Manual/reference/scripting_reference/scripting_objects/alias.zh.md)**：此对象表示 [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)，并且使用 **Aliases** 对象检索。
- **[Aliases](/Manual/reference/scripting_reference/scripting_objects/aliases.zh.md)**：此对象是所有已定义文件夹别名的集合。它使用 **DOpus.aliases** 集合属性检索。
- **[Args](/Manual/reference/scripting_reference/scripting_objects/args.zh.md)**：该对象表示为 [脚本定义的内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 提供的命令行参数。它可从 **ScriptCommandData.Func.args** 属性获取。
- **[AudioMeta](/Manual/reference/scripting_reference/scripting_objects/audiometa.zh.md)**：该对象提供与音频文件相关的元数据属性。它从 **Metadata** 对象获取。
- **[AudioCoverArt](/Manual/reference/scripting_reference/scripting_objects/audiocoverart.zh.md)**：该对象提供访问音频文件嵌入的封面图片。它从 **AudioMeta.coverart** 属性获取。
- **[Blob](/Manual/reference/scripting_reference/scripting_objects/blob.zh.md)**：该对象提供简单界面来处理二进制数据。它从 **DOpusFactory.Blob** 方法获取，也由 **AudioCoverArt.data** 属性返回。
- **[BusyIndicator](/Manual/reference/scripting_reference/scripting_objects/busyindicator.zh.md)**：使用 **BusyIndicator** 对象，可以通过脚本控制面包屑栏的忙碌指示器。
- **[Column](/Manual/reference/scripting_reference/scripting_objects/column.zh.md)**：该对象表示已添加到某标签页显示中的某列。列集合可从 **Format** 对象获取。
- **[Command](/Manual/reference/scripting_reference/scripting_objects/command.zh.md)**：该对象用于运行 Opus 命令。它从 **ScriptCommandData.func** 或 **ClickData.func** 属性获取，也可以通过 **DOpusFactory.Command** 方法创建。
- **[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md)**：**Control** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 的控件；它允许你读取和修改控件的值（和内容）。
- **[CustomFieldData](/Manual/reference/scripting_reference/scripting_objects/customfielddata.zh.md)**：**CustomFieldData** 对象通过 **[GetNewNameData](/Manual/reference/scripting_reference/scripting_objects/getnewnamedata.zh.md).custom** 属性提供给 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md)。它提供对脚本添加到*重命名*对话框的任何 [自定义字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md) 的值访问。
- **[Date](/Manual/reference/scripting_reference/scripting_objects/date.zh.md)**：该对象提供，以方便处理表示日期的变量。它从 **DOpusFactory.Date** 方法以及其它对象中的各种属性获取。
- **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md)**：该对象用于显示对话框或弹出菜单。它从 **Func.Dlg**, **Command.Dlg** 或 **DOpus.Dlg** 方法获取。
- **[DialogListColumn](/Manual/reference/scripting_reference/scripting_objects/dialoglistcolumn.zh.md)**：**DialogListColumn** 对象表示 [脚本对话框。](/Manual/scripting/script_dialogs/README.zh.md) 中*详细信息*模式*列表视图*控件中的某列。通过枚举**[DialogListColumns](/Manual/reference/scripting_reference/scripting_objects/dialoglistcolumns.zh.md)**对象获取.**~control**
- **[DialogListColumns](/Manual/reference/scripting_reference/scripting_objects/dialoglistcolumns.zh.md)**：**DialogListColumns** 对象允许查询或修改 [脚本对话框。](/Manual/scripting/script_dialogs/README.zh.md) 中*详细信息*模式*列表视图*控件中的列。使用 **[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md).columns** 属性获取 **DialogListColumns** 对象。
- **[DialogListGroup](/Manual/reference/scripting_reference/scripting_objects/dialoglistgroup.zh.md)**：**DialogListGroup** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中*列表视图*控件中的某组。它由 **[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md).GetGroupById** 方法返回。
- **[DialogListItem](/Manual/reference/scripting_reference/scripting_objects/dialoglistitem.zh.md)**：**DialogListItem** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中*组合框*或*列表框*控件中的某项。它由 **[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md).GetItemAt** 和 **[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md).GetItemByName** 方法返回。
- **[DialogOption](/Manual/reference/scripting_reference/scripting_objects/dialogoption.zh.md)**：该对象与 **Dialog** 对象联合使用。它允许指定要添加到对话框的复选框选项。
- **[Dock](/Manual/reference/scripting_reference/scripting_objects/dock.zh.md)**：该对象表示浮动工具栏。工具栏对象提供集合，表示当前处于浮动状态的所有该工具栏的实例。
- **[DocMeta](/Manual/reference/scripting_reference/scripting_objects/docmeta.zh.md)**：该对象提供与文档文件相关的元数据属性。它从 **Metadata** 对象获取。
- **[DOpusFactory](/Manual/reference/scripting_reference/scripting_objects/dopusfactory.zh.md)**：该对象是帮助对象，可用于创建其它各类对象，如 **Map** 和 **Vector**。它从 **DOpus.Create** 方法获取。
- **[DPI](/Manual/reference/scripting_reference/scripting_objects/dpi.zh.md)**：**DPI** 对象是帮助对象，提供若干与系统 DPI 设置相关的属性和方法。它通过 **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.zh.md).DPI** 属性返回。
- **[Drive](/Manual/reference/scripting_reference/scripting_objects/drive.zh.md)**：**Drive** 对象提供有关系统上某驱动器（硬盘驱动器、CD ROM 等）的信息。系统上驱动器的 **Vector** 可从 **[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.zh.md).Drives** 方法获取。
- **[ExeMeta](/Manual/reference/scripting_reference/scripting_objects/exemeta.zh.md)**：该对象提供与可执行（程序）文件相关的元数据属性。它从 **Metadata** 对象获取。
- **[Favorite](/Manual/reference/scripting_reference/scripting_objects/favorite.zh.md)**：**Favorite** 对象表示 [收藏文件夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md)。通过枚举或编制 [Favorites](/Manual/reference/scripting_reference/scripting_objects/favorites.zh.md) 对象索引获取它。
- **[Favorites](/Manual/reference/scripting_reference/scripting_objects/favorites.zh.md)**：**Favorites** 对象保存所有定义的 [收藏文件夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md) 的集合。它从 **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.zh.md).favorites** 方法获取。
- **[File](/Manual/reference/scripting_reference/scripting_objects/file.zh.md)**：该对象允许从文件读取或写入二进制数据。它从 **FSUtil.OpenFile** 和 **Item.Open** 方法获取。
- **[FileAttr](/Manual/reference/scripting_reference/scripting_objects/fileattr.zh.md)**：该对象表示文件属性（例如只读、压缩包等）。它由 **Item** 和 **Format** 对象使用，并且可以通过 **[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.zh.md).NewFileAttr** 方法创建。
- **[FileGroup](/Manual/reference/scripting_reference/scripting_objects/filegroup.zh.md)**：该对象公开有关文件组的信息（当 **Tab** 设置为按特定列分组时）。它由 **Item** 和 **Tab** 对象使用。
- **[FileSize](/Manual/reference/scripting_reference/scripting_objects/filesize.zh.md)**：该对象用于表示字节大小（主要是因为 ActiveX 脚本不支持 64 位整数）。它由 **Item** 和 **TabStats** 对象使用。
- **[FiletypeGroup](/Manual/reference/scripting_reference/scripting_objects/filetypegroup.zh.md)**：该对象表示文件类型组（如 [文件类型组](/Manual/file_types/file_type_groups.zh.md) 部分的 [文件类型编辑器](/Manual/file_types/README.zh.md) 中所配置）。
- **[FiletypeGroups](/Manual/reference/scripting_reference/scripting_objects/filetypegroups.zh.md)**：该对象表示一个或多个文件类型组的集合。
- **[Filter](/Manual/reference/scripting_reference/scripting_objects/filter.zh.md)**：让你创建复杂过滤器，当从脚本运行时可与诸如 **Copy** 的命令一起使用。
- **[FilterParseError](/Manual/reference/scripting_reference/scripting_objects/filterparseerror.zh.md)**：用于在使用 **Filter** 对象时访问有关解析错误的信息。
- **[FolderEnum](/Manual/reference/scripting_reference/scripting_objects/folderenum.zh.md)**：该对象让脚本枚举文件夹的内容。它使用 **FSUtil.ReadDir** 方法获取。
- **[FontMeta](/Manual/reference/scripting_reference/scripting_objects/fontmeta.zh.md)**：该对象提供与字体文件相关的元数据属性。它从 **Metadata** 对象获取。
- **[Format](/Manual/reference/scripting_reference/scripting_objects/format.zh.md)**：该对象在标签页中提供有关显示格式的信息。它从 **Tab.format** 属性获取。
- **[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.zh.md)**：该对象提供与文件系统活动相关的多种实用程序方法。它从 **DOpus.FSUtil** 属性获取。
- **[Func](/Manual/reference/scripting_reference/scripting_objects/func.zh.md)**：该对象传给 [脚本函数](/Manual/scripting/script_functions.zh.md)（通过 **ClickData.func**）或 [脚本定义的内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)（通过 **ScriptCommandData.func**）。它提供与函数调用（源和目标标签页、参数等）相关的信息。
- **[GlobalFilters](/Manual/reference/scripting_reference/scripting_objects/globalfilters.zh.md)**：该对象让你访问有关全局过滤器设置的信息（配置中 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面上配置）。
- **[Image](/Manual/reference/scripting_reference/scripting_objects/image.zh.md)**：该对象从磁盘加载可显示在 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中的图像文件或图标。
- **[ImageMeta](/Manual/reference/scripting_reference/scripting_objects/imagemeta.zh.md)**：该对象提供与图像文件相关的元数据属性。它从 **Metadata** 对象获取。
- **[IncludeFileInitData](/Manual/reference/scripting_reference/scripting_objects/includefileinitdata.zh.md)**：如果 [包含文件](/Manual/scripting/script_add-ins/include_files.zh.md) 脚本实现可选的 **[oninitincludefile](scripting_events/oninitincludefile.zh.md)** 方法，那么它将接收该对象，以便其提供有关包含文件的信息。
- **[Item](/Manual/reference/scripting_reference/scripting_objects/item.zh.md)**：该对象表示文件或文件夹。它可以从 **Tab** 对象的各种方法中返回，在使用 **FSUtil.ReadDir** 方法枚举文件夹时，以及用于为使用 **Command** 对象执行命令提供文件时。
- **[Items](/Manual/reference/scripting_reference/scripting_objects/items.zh.md)**：**Items** 对象让你枚举一个或多个 **Item** 对象的列表。
- **[文件窗口](/Manual/reference/scripting_reference/scripting_objects/lister.zh.md)**：该对象表示 [文件窗口](/Manual/basic_concepts/the_lister/README.zh.md) 窗口。
- **[文件窗口s](/Manual/reference/scripting_reference/scripting_objects/listers.zh.md)**：**[文件窗口s](/Manual/reference/scripting_reference/scripting_objects/listers.zh.md)** 对象是所有当前打开的文件窗口窗口的集合（每个窗口由 **[文件窗口](/Manual/reference/scripting_reference/scripting_objects/lister.zh.md)** 对象表示）。它可以从 **DOpus.listers** 属性中获取。
- **[Map](/Manual/reference/scripting_reference/scripting_objects/map.zh.md)**：该对象类似于数组或向量（例如 **[Vector](/Manual/reference/scripting_reference/scripting_objects/vector.zh.md)**），因为它可以存储一个或多个对象，但其优点在于使用字典系统定位对象，而不是数值索引。它从 **DOpusFactory.Map** 方法获取。
- **[Metadata](/Manual/reference/scripting_reference/scripting_objects/metadata.zh.md)**：该对象表示文件或文件夹的元数据。它可以从 **Item.metadata** 属性以及 **FSUtil.GetMetadata** 方法中获取。
- **[Msg](/Manual/reference/scripting_reference/scripting_objects/msg.zh.md)**：**Msg** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 输入事件消息。它由 **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md).GetMsg** 方法返回，当为你运行 [分离的对话框](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.zh.md) 的消息循环时，你会调用该方法。
- **[OtherMeta](/Manual/reference/scripting_reference/scripting_objects/othermeta.zh.md)**：该对象提供与文件和文件夹相关的常规元数据属性。它从 **Metadata** 对象获取。
- **[PairedFolder](/Manual/reference/scripting_reference/scripting_objects/pairedfolder.zh.md)**：该对象表示从 **FSUtil.GetFolderPair** 方法中获取的 [配对文件夹](/Manual/preferences/preferences_categories/frequently_used_paths/paired_folders.zh.md)。
- **[Path](/Manual/reference/scripting_reference/scripting_objects/path.zh.md)**：该对象表示文件系统路径。它包含用于操作该路径的几个方法。路径对象由几个属性返回，并且可以通过 **FSUtil.NewPath** 方法创建。
- **[Progress](/Manual/reference/scripting_reference/scripting_objects/progress.zh.md)**：该对象表示进度对话框，它让你在视觉上向用户指示脚本函数的进度。它从 **Command.progress** 属性获取。
- **[QuickFilter](/Manual/reference/scripting_reference/scripting_objects/quickfilter.zh.md)**：此对象提供了一个标签中的快速过滤状态的信息。它从 **[Tab](/Manual/reference/scripting_reference/scripting_objects/tab.zh.md).quickfilter** 属性中获取。
- **[Rect](/Manual/reference/scripting_reference/scripting_objects/rect.zh.md)**: **Rect** 对象代表一个矩形。
- **[Results](/Manual/reference/scripting_reference/scripting_objects/results.zh.md)**: 此对象代表命令的结果（发生错误时的错误代码，以及命令创建的任何新标签或文件窗口）。它从 **Command.results** 属性中获取。
- **[ScriptColorPair](/Manual/reference/scripting_reference/scripting_objects/scriptcolorpair.zh.md)**：此对象捆绑了一对颜色（文本 / 背景）。
- **[ScriptColumn](/Manual/reference/scripting_reference/scripting_objects/scriptcolumn.zh.md)**：此对象代表一个 [脚本定义的列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。它从 **ScriptInitData.AddColumn** 方法中获取，同时处理 **OnInit** 事件。
- **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.zh.md)**：此对象代表一个 [脚本定义的内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)。它从 **ScriptInitData.AddCommand** 方法中获取，同时处理 **OnInit** 事件。
- **[Script即时查找Command](/Manual/reference/scripting_reference/scripting_objects/scriptfaytcommand.zh.md)**：此对象为延伸了即时查找字段（/Manual/scripting/example_scripts/extending_the_fayt.zh.md）的脚本加载项的 **ScriptCommand** 对象提供为一个属性。
- **[ScriptConfig](/Manual/reference/scripting_reference/scripting_objects/scriptconfig.zh.md)**：此对象代表 Opus 为每个脚本存储的脚本定义的配置数据。配置项目通过 **ScriptInitData.config** 属性初始化，然后通过 **Script.config** 属性可用于脚本。
- **[ScriptStrings](/Manual/reference/scripting_reference/scripting_objects/scriptstrings.zh.md)**：**ScriptStrings** 对象由 **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.zh.md).strings** 属性返回。它允许你访问通过 [字符串资源](/Manual/scripting/resources/string_resources.zh.md) 定义的任何字符串。
- **[ShellProperty](/Manual/reference/scripting_reference/scripting_objects/shellproperty.zh.md)**：**ShellProperty** 对象代表一个 shell 属性 - 一个来自 Windows 或第三方扩展的有关文件或文件夹的元数据项。**[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.zh.md).GetShellPropertyList** 方法让你可以获取一个可用的 shell 属性列表。
- **[SmartFavorite](/Manual/reference/scripting_reference/scripting_objects/smartfavorite.zh.md)**：**SmartFavorite** 对象代表一个文件夹在 [智能收藏夹](/Manual/basic_concepts/the_lister/navigation/smartfavorites.zh.md) 表中的条目。通过枚举或索引 **[智能收藏夹](/Manual/reference/scripting_reference/scripting_objects/smartfavorites.zh.md)** 对象来检索它。
- **[智能收藏夹](/Manual/reference/scripting_reference/scripting_objects/smartfavorites.zh.md)**：**智能收藏夹** 对象让你可以查询 [智能收藏夹](/Manual/basic_concepts/the_lister/navigation/smartfavorites.zh.md) 表的内容。它从 **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.zh.md).smartfavorites** 属性中获取。
- **[SortOrder](/Manual/reference/scripting_reference/scripting_objects/sortorder.zh.md)**：如果 [手动排序模式](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.zh.md) 处于活动状态，则 **SortOrder** 对象由 **[Format](/Manual/reference/scripting_reference/scripting_objects/format.zh.md).manual_sort_order** 属性返回。它允许你查询和修改排序顺序。
- **[StringTools](/Manual/reference/scripting_reference/scripting_objects/stringtools.zh.md)**：此对象提供用于字符串编码和解码的实用函数。它从 **DOpusFactory.StringTools** 方法中获取。
- **[StringSet](/Manual/reference/scripting_reference/scripting_objects/stringset.zh.md)**：此对象与字符串的数组或向量（例如 **[Vector](/Manual/reference/scripting_reference/scripting_objects/vector.zh.md)**）类似，但其优势在于使用词典系统来定位字符串，而不是使用数字索引。它从 **DOpusFactory.StringSet** 和 **StringSetI** 方法中获取。
- **[SysInfo](/Manual/reference/scripting_reference/scripting_objects/sysinfo.zh.md)**：**SysInfo** 对象由 **DOpusFactory.SysInfo** 方法创建。它允许脚本访问各种系统信息，脚本可能无法通过其它方式获取。
- **[Tab](/Manual/reference/scripting_reference/scripting_objects/tab.zh.md)**：此对象代表一个文件窗口中的文件夹标签。文件窗口的标签通过各种文件窗口对象属性（例如 **文件窗口.activetab**）提供，并且还用于指定命令的来源/目标（例如 **Command.sourcetab**）。
- **[TabGroup](/Manual/reference/scripting_reference/scripting_objects/tabgroup.zh.md)**：此对象代表一个 [文件夹标签组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md)。通过枚举 **[TabGroups](/Manual/reference/scripting_reference/scripting_objects/tabgroups.zh.md)** 对象来访问它。
- **[TabGroups](/Manual/reference/scripting_reference/scripting_objects/tabgroups.zh.md)**：此对象提供访问权限，并且允许你修改已配置的 [文件夹标签组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md) 列表。它从 **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.zh.md).tabgroups** 属性中获取。
- **[TabGroupTabEntry](/Manual/reference/scripting_reference/scripting_objects/tabgrouptabentry.zh.md)**：此对象代表一个 [标签组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md) 中的文件夹标签。
- **[TabGroupTabList](/Manual/reference/scripting_reference/scripting_objects/tabgrouptablist.zh.md)**：此对象代表一个 [标签组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md) 中的文件夹标签列表。
- **[TabStats](/Manual/reference/scripting_reference/scripting_objects/tabstats.zh.md)**：此对象提供有关文件夹标签的各种统计信息（所选文件数、总项数等）。它从 **Tab.stats** 和 **Tab.selstats** 属性中获取。
- **[Toolbar](/Manual/reference/scripting_reference/scripting_objects/toolbar.zh.md)**：此对象代表一个工具栏。它通过 **DOpus.toolbars** 和 **文件窗口.toolbars** 属性获取。
- **[Toolbars](/Manual/reference/scripting_reference/scripting_objects/toolbars.zh.md)**：**Toolbars** 对象允许你枚举 Directory Opus 配置中定义的所有工具栏（无论当前是否启用）。
- **[UnorderedSet](/Manual/reference/scripting_reference/scripting_objects/unorderedset.zh.md)**：类似于 **[StringSet](/Manual/reference/scripting_reference/scripting_objects/stringset.zh.md)**，但可以存储任何类型的元素，而不仅仅是字符串。
- **[Var](/Manual/Reference/Scripting_Reference/Scripting_Objects/Var.zh.md)**：这个对象表示变量。工具栏按钮、热键和脚本可以读取和存储变量，变量可以从 Opus 的一次会话保存到另一次会话。**Var** 对象是从 **Vars** 集合获得的。
- **[Vars](/Manual/Reference/Scripting_Reference/Scripting_Objects/Vars.zh.md)**：这个对象表示变量的集合。根据变量的范围，它可以从 **DOpus.vars**、**文件窗口.vars**、**Tab.vars**、**Command.vars** 或 **Script.vars** 属性获得。
- **[Vector](/Manual/Reference/Scripting_Reference/Scripting_Objects/Vector.zh.md)**：这个对象类似于数组——它可以存储无限数量的任何类型的元素。Opus 脚本界面中的许多属性和方法都使用 Vector，在大多数情况下你可以将它们与数组互换使用。之所以提供 Vector，是因为有些脚本语言仅提供不完整或不兼容的数组——使用 Vector 表示对象可以在任何 ActiveX 脚本语言中一致使用。**Vector** 由 **DOpusFactory.Vector** 方法创建。
- **[Version](/Manual/Reference/Scripting_Reference/Scripting_Objects/Version.zh.md)**：这个对象表示有关当前 Opus 版本的信息。它可以从 **DOpus.Version** 属性获得。
- **[VideoMeta](/Manual/Reference/Scripting_Reference/Scripting_Objects/VideoMeta.zh.md)**：这个对象提供与电影文件相关的元数据属性。它可以从 **Metadata** 对象获得。
- **[Viewer](/Manual/Reference/Scripting_Reference/Scripting_Objects/Viewer.zh.md)**：**Viewer** 对象表示一个独立的 [图像查看器](/Manual/Additional_Functionality/Viewing_Images/README.zh.md)。
- **[Viewers](/Manual/Reference/Scripting_Reference/Scripting_Objects/Viewers.zh.md)**：**Viewers** 对象是当前所有打开的独立的 [图像查看器](/Manual/Additional_Functionality/Viewing_Images/README.zh.md) 的集合。可以通过 **[DOpus](/Manual/Reference/Scripting_Reference/Scripting_Objects/Dopus.zh.md).viewers** 属性获得它
- **[Wild](/Manual/Reference/Scripting_Reference/Scripting_Objects/Wild.zh.md)**：这个对象允许脚本访问 Opus 中内置的模式匹配函数。它可以从 **FSUtil.NewWild** 方法获得。
- **[WinVer](/Manual/Reference/Scripting_Reference/Scripting_Objects/WinVer.zh.md)**：这个对象表示有关当前 Windows 版本的信息。它可以从 **Version.winver** 属性获得。