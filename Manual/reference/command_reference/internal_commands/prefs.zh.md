# Prefs

**Prefs** 内部命令可以用于：

- 显示 [配置](/Manual/preferences/README.zh.md) 对话框，让你更改大多数配置选项
- 显示 [自定义](/Manual/customize/README.zh.md) 对话框以编辑工具栏、菜单和热键
- 显示 [文件类型](/Manual/file_types/README.zh.md) 对话框以配置上下文菜单、双击操作和其他特定于文件类型设置
- 显示并编辑 [FTP 通讯簿](/Manual/ftp/ftp_address_book/README.zh.md)
- [备份和恢复](/Manual/preferences/backing_up_and_restoring_preferences.zh.md) 你的配置
- 加载并保存 [文件查看器布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md)
- 更新 [默认文件查看器](/Manual/basic_concepts/the_lister/the_default_lister.zh.md) 设置
- 加载并保存 [文件查看器样式](/Manual/basic_concepts/the_lister/styles.zh.md)
- 加载并保存 [文件查看器主题](/Manual/basic_concepts/the_lister/themes/README.zh.md)
- 管理 [VFS 插件](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_and_vfs_plugins.zh.md)
- 安装、管理和编辑 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)。

**命令自变量：**

<table>
<thead><tr><th>
自变量</th><th>
类型</th><th>
可能值</th><th>
描述
</th></tr></thead><tbody><tr><td>

*(无自变量)*</td><td>
-</td><td>
-</td><td>

显示 **[配置](/Manual/preferences/README.zh.md)** 对话框。

*范例：* `Prefs`
</td></tr><tr><td>
ADDFTPSITE</td><td>
/S</td><td>

*(无值)*</td><td>

添加当前连接的 FTP 站点作为 [FTP 通讯簿](/Manual/ftp/ftp_address_book/README.zh.md) 中的新条目。如果您当前没有查看 FTP 目录，此命令无效。

*范例：* `Prefs ADDFTPSITE`
</td></tr><tr><td>
BACKUP</td><td>
/O</td><td>

*(无值)*</td><td>

自动化配置备份进程。默认情况下，您的所有配置设置、工具栏、菜单和热键都将包含在备份中，但不会包括图像和声音等额外数据。此自变量的可选项用于控制哪些额外数据包含在备份中。使用 **TO** 自变量指定备份文件名称，**PASSWORD**、**DESC** 和 **QUIET** 自变量提供其他控制。

*范例：* `Prefs BACKUP TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**images**</td><td>

在自动配置备份时，将图像文件包含在您的备份中（对应于 *[备份和恢复配置](/Manual/preferences/backing_up_and_restoring_preferences.zh.md)* 向导中的 **备份图像** 选项）。

*范例：* `Prefs BACKUP=images TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**sounds**</td><td>

在备份中包含声音文件（对应于 **备份声音** 选项）。

*范例：* `Prefs BACKUP=sounds TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**data**</td><td>

在备份中包含其他数据（对应于 **备份其他数据** 选项）。

*范例：* `Prefs BACKUP=data TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**localstate**</td><td>

包含本地状态数据（对应于 **备份本地状态数据** 选项）。

*范例：* `Prefs BACKUP=data,localstate TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

备份所有内容（相当于 **BACKUP=images,sounds,data,localstate**）。

*范例：* `Prefs BACKUP=all TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**notabs**</td><td>

（Opus 13.3.1 及以上版本）从备份中排除当前打开的窗口和标签（仅在备份本地状态时相关）。

*范例：* `Prefs BACKUP=all,notabs TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
BACKUPRESTORE</td><td>
/S</td><td>

*(无值)*</td><td>

启动 *[备份和恢复配置](/Manual/preferences/backing_up_and_restoring_preferences.zh.md)* 向导，它允许您备份和恢复配置，以及将 Opus 导出到 USB 驱动器。您可以使用 **TO** 自变量覆盖默认备份名称，并使用 **PASSWORD** 或 **DESC** 自变量在创建备份时预先提供默认密码或描述。

*范例：* `Prefs BACKUPRESTORE`  
*范例：* `Prefs BACKUPRESTORE TO="/desktop\Backup for %username% on {date\|yyyy-MM-dd}" PASSWORD="cat" DESC="Quick Backup."`

如果您希望在不显示交互式向导的情况下自动化备份或还原过程，请使用单独的 **BACKUP** 或 **RESTORE** 自变量。
</td></tr><tr><td>
COLLAPSEALL</td><td>
/S</td><td>

*(无值)*</td><td>

在 **[配置](/Manual/preferences/README.zh.md)** 对话框中折叠所有类别。与 `PAGE` 自变量结合使用以显示新页面并折叠所有其他类别。

*范例：* `Prefs PAGE=folderformats COLLAPSEALL`
</td></tr><tr><td>
CUSTOMIZE</td><td>
/O</td><td>

*(无值)*</td><td>

显示 **[自定义](/Manual/customize/README.zh.md)** 对话框。该对话框将在上次使用的页面上打开。

*范例：* `Prefs CUSTOMIZE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<page\>*</td><td>

在 **定制** 对话框上显示指定的标签。此自变量允许的值为 **commands**、**toolbars**、**keys** 和 **menus**。

*范例：* `Prefs CUSTOMIZE=toolbars`
</td></tr><tr><td>
DESC</td><td>
/K</td><td>

*\<描述\>*</td><td>

为配置备份分配一个描述（与 **BACKUP** 或 **BACKUPRESTORE** 自变量一起使用）。请记住，如果描述字符串包含空格，则需要用引号将其括起来。

*范例：* `Prefs BACKUP TO="/desktop/PrefsBackup" DESC="My Opus Config"`
</td></tr><tr><td>
FILETYPES</td><td>
/S</td><td>

*(无值)*</td><td>

显示 **[文件类型](/Manual/file_types/README.zh.md)** 对话框。

*范例：* `Prefs FILETYPES`
</td></tr><tr><td>
FROM</td><td>
/K</td><td>

*\<备份文件\>*</td><td>

指定要还原的配置备份文件（与 **RESTORE** 自变量结合使用以自动化配置还原过程）。

*范例：* `Prefs RESTORE FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
FTPSITES</td><td>
/O</td><td>

*(无值)*</td><td>

显示 **[FTP 通讯簿](/Manual/ftp/ftp_address_book/README.zh.md)**。

*范例：* `Prefs FTPSITES`
</td></tr><tr><td>
</td><td>
</td><td>

*\<站点名称\>*</td><td>

显示 **[FTP 通讯簿](/Manual/ftp/ftp_address_book/README.zh.md)** 并自动选择指定站点。如果站点位于通讯簿的一个子文件夹中，则需要提供站点的完整路径。

*范例：* `Prefs FTPSITES="WorkServers\Production"`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

当与生成项目列表的命令一起使用时（请参阅 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 自变量在列表开头添加一个小标题。当列表为空时小标题将被隐藏。小标题仅适用于那些可能在与按钮本身相同的级别生成多个项目的命令。

当 **HEADING** 自身使用且没有指定文本值时，主按钮的标签文本将用于小标题。
*示例：* `Prefs LAYOUTLIST 标题`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题文本\>*</td><td>

如果要将标题文本与按钮的标记不同，则可以指定标题文本。

*示例：* `Prefs STYLELIST HEADING="Styles"`
</td></tr><tr><td>
KEYS</td><td>
/S</td><td>

*（无值）*</td><td>

显示**自定义**对话框的**密钥**页面（等同于`Prefs CUSTOMIZE=keys`）。

*示例：* `Prefs KEYS`
</td></tr><tr><td>
LAYOUT</td><td>
/K</td><td>

*\<布局名称\>*</td><td>

加载命名的[文件窗口布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md)。

*示例：* `Prefs LAYOUT="Music Albums"`
</td></tr><tr><td>
LAYOUTCLOSELISTERS</td><td>
/K</td><td>

**是**</td><td>

使用 **LAYOUT** 参数加载布局时，它将覆盖为该布局设置的**加载此布局时关闭所有现有的文件窗口**标志，并强制关闭所有现有的文件窗口。使用 **LAYOUTSAVE** 参数保存布局时，它将设置布局中该标志的状态。

*示例：* `Prefs LAYOUT="FTP Sync" LAYOUTCLOSELISTERS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**否**</td><td>

加载布局时不会关闭所有现有的文件窗口。

*示例：* `Prefs LAYOUT="Photo Album" LAYOUTCLOSELISTERS=no`
</td></tr><tr><td>
</td><td>
</td><td>

**当前**</td><td>

仅关闭当前虚拟桌面的文件窗口。

*示例：* `Prefs LAYOUT="Work" LAYOUTCLOSELISTERS=yes,current`
</td></tr><tr><td>
</td><td>
</td><td>

**所有**</td><td>

关闭所有桌面上的文件窗口。

*示例：* `Prefs LAYOUT="Photo Organising" LAYOUTCLOSELISTERS=yes,all`
</td></tr><tr><td>
LAYOUTEDIT</td><td>
/S</td><td>

*（无值）*</td><td>

打开配置对话框并显示**[布局和样式 / 布局](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.zh.md)**页面（等同于`Prefs PAGE=layouts`）。

*示例：* `Prefs LAYOUTEDIT`
</td></tr><tr><td>
LAYOUTIGNOREFORMATS</td><td>
/K</td><td>

**是**</td><td>

使用 **LAYOUT** 参数加载布局时，它将覆盖为该布局设置的**忽略在此布局中保存的文件夹格式**标志，并强制忽略布局的[文件夹格式](/Manual/basic_concepts/folder_options/folder_formats.zh.md)。使用 **LAYOUTSAVE** 参数保存布局时，它将设置布局中该标志的状态。

*示例：* `Prefs LAYOUT="Photo Viewing" LAYOUTIGNOREFORMATS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**否**</td><td>

不忽略布局的文件夹格式。

*示例：* `Prefs LAYOUT="Photos" LAYOUTIGNOREFORMATS=no`
</td></tr><tr><td>
LAYOUTIGNORETOOLBARS</td><td>
/K</td><td>

**是**</td><td>

使用 **LAYOUT** 参数加载布局时，它将覆盖为该布局设置的**忽略在此布局中保存的工具栏**标志，并强制忽略布局的工具栏，而改用默认工具栏集。使用 **LAYOUTSAVE** 参数保存布局时，它将设置布局中该标志的状态。

*示例：* `Prefs LAYOUT="Photos" LAYOUTIGNORETOOLBARS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**否**</td><td>

不忽略布局的工具栏。

*示例：* `Prefs LAYOUT="Photos" LAYOUTIGNORETOOLBARS=no`
</td></tr><tr><td>
LAYOUTLIST</td><td>
/S</td><td>

*（无值）*</td><td>

显示已保存的[文件窗口布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md) 列表（充当[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。从生成的列表中选择一个项目将加载指定的布局。**LAYOUTCLOSELISTERS**、**LAYOUTIGNOREFORMATS** 和 **LAYOUTMOUSERELATIVE** 标志可以与此参数结合使用，以控制生成的按钮的行为。

*示例：* `Prefs LAYOUTLIST LAYOUTCLOSELISTERS=yes`
</td></tr><tr><td>
LAYOUTMOUSERELATIVE</td><td>
/K</td><td>

**是**</td><td>

使用 **LAYOUT** 参数加载布局时，它将覆盖为该布局设置的**相对于鼠标当前所在的监视器打开布局**标志，并强制布局的位置相对于鼠标。使用 **LAYOUTSAVE** 参数保存布局时，它将设置布局中该标志的状态。

*示例：* `Prefs LAYOUT="Find" LAYOUTMOUSERELATIVE=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**否**</td><td>

不会相对于鼠标指针打开布局。

*示例：* `Prefs LAYOUT="BackupFiles" LAYOUTMOUSERELATIVE=no`
</td></tr><tr><td>
LAYOUTNAME</td><td>
/K</td><td>

*\<布局名称\>*</td><td>

使用 **LAYOUTSAVE** 参数保存[布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md) 时指定一个名称。如果没有提供，Opus 将提示输入新布局的名称。

*示例：* `Prefs LAYOUTNAME="My Layout" LAYOUTSAVE`
</td></tr><tr><td>
LAYOUTNOVIRTDESKTOP</td><td>
/K</td><td>

**是**</td><td>

加载布局时，防止文件窗口还原到其原始虚拟桌面（覆盖布局中的设置）。

*示例：* `Prefs LAYOUT="Find" LAYOUTNOVIRTDESKTOP=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**否**</td><td>

允许文件窗口还原到其原始虚拟桌面。

*示例：* `Prefs LAYOUT="Find" LAYOUTNOVIRTDESKTOP=no`
</td></tr><tr><td>
LAYOUTSAVE</td><td>
/O</td><td>

*（无值）*</td><td>

将当前打开的文件窗口保存为[布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md)。可以使用 **LAYOUTNAME** 参数指定布局名称。你还可以使用 **LAYOUTCLOSELISTERS**、**LAYOUTIGNOREFORMATS** 和 **LAYOUTMOUSERELATIVE** 参数来控制已保存布局的那些标志的状态。

*示例：* `Prefs LAYOUTSAVE`
</td></tr><tr><td>
</td><td>
</td><td>

**单个**</td><td>

仅将活动文件窗口保存为布局。任何其他当前打开的文件窗口都不会包括在内。

*示例：* `Prefs LAYOUTSAVE=single LAYOUTNAME="Current文件窗口"`
</td></tr><tr><td>
</td><td>
</td><td>

**未更新设置**</td><td>

如果不使用 **LAYOUTNAME** 参数为布局提供名称，Opus 就会显示一个对话框提示输入名称——此对话框还包含布局的各种选项（忽略格式、相对于鼠标等）。对这些选项所做的更改将保存为 **LAYOUTSAVE** 函数的默认设置，除非你指定 **未更新设置** 值。

*示例：* `Prefs LAYOUTSAVE=未更新设置 LAYOUTMOUSERELATIVE=yes LAYOUTNAME="My Layout"`
</td></tr><tr><td>
</td><td>
</td><td>

**更新当前**</td><td>

如果当前文件窗口已经是布局的一部分，则该布局将被更新，并且不会提示你输入布局名称或其他任何选项。

*示例：* `Prefs LAYOUTSAVE=更新当前`
</td></tr><tr><td>
LAYOUTTHISLISTER</td><td>
/O</td><td>

*（无值）*</td><td>

结合 **LAYOUT** 参数，此参数将指定布局的设置应用于当前文件窗口，而不是打开新文件窗口。

如果没有向 **LAYOUTTHISLISTER** 参数提供值，则布局的小面板（例如查看器面板、双栏、实用工具面板）将应用于当前文件窗口，但窗口大小和位置以及当前路径将保持不变。
*示例：* `Prefs LAYOUT="PhotoViewing" LAYOUTTHISLISTER`
</td></tr><tr><td>
</td><td>
</td><td>

**nopanels**</td><td>

不将布局的面板（例如查看器窗格、双栏、实用工具面板）应用到当前窗口。（如果没有指定其他值，则根本什么都不会做。）

*示例：* `Prefs LAYOUT="Small文件窗口" LAYOUTTHISLISTER=nopanels,size`
</td></tr><tr><td>
</td><td>
</td><td>

**size**</td><td>

使用指定布局的窗口大小。

*示例：* `Prefs LAYOUT="Small文件窗口" LAYOUTTHISLISTER=size`
</td></tr><tr><td>
</td><td>
</td><td>

**pos**</td><td>

使用指定布局的窗口位置。

*示例：* `Prefs LAYOUT="NiceSized文件窗口" LAYOUTTHISLISTER=pos,size`
</td></tr><tr><td>
</td><td>
</td><td>

**paths**</td><td>

使用指定布局的路径/标签（和文件夹格式）。

*示例：* `Prefs LAYOUT="CurrentWork" LAYOUTTHISLISTER=pos,size,paths`

您还可以将 **LAYOUTIGNOREFORMATS** 与 **LAYOUTTHISLISTER=paths** 结合使用，以覆盖是否应用布局的文件夹格式（这通常由您在保存和编辑每个布局时可以设置的标志决定）。

*示例：* `Prefs LAYOUT="My Layout" LAYOUTTHISLISTER=paths LAYOUTIGNOREFORMATS=yes`
</td></tr><tr><td>
LIMITPATH</td><td>
/K/M</td><td>

*\<路径\>*</td><td>

使用 **LAYOUT** 参数打开新布局时，这允许您将新打开的文件窗口限制为一个或多个路径（及其子路径）。尝试在允许的路径之外导航将显示错误。

*示例：* `Prefs LAYOUT="Focus On Work" LIMITPATH "C:\Work"`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

如果布局已使用受限路径保存，则这允许您在打开布局时覆盖这些限制。

*示例：* `Prefs LAYOUT="Locked文件窗口" LIMITPATH=reset`
</td></tr><tr><td>
MENUMARKERS</td><td>
/S</td><td>

*(无值)*</td><td>

与 **LAYOUTLIST** 一起使用时，如果生成的布局列表包含任何子菜单，则顶级按钮将显示一个指示下拉菜单的标志。

*示例：* `Prefs LAYOUTLIST MENUMARKERS`
</td></tr><tr><td>
NOSCRIPT</td><td>
/S</td><td>

*(无值)*</td><td>

允许 [脚本](/Manual/scripting/README.zh.md) 运行 `Prefs LAYOUT` 命令，而无需触发其他脚本（或其本身）。添加 **NOSCRIPT** 参数将禁用 **[OnBeforeFolderChange](../../scripting_reference/scripting_events/onbeforefolderchange.zh.md)**、**[OnAfterFolderChange](../../scripting_reference/scripting_events/onafterfolderchange.zh.md)**、**[OnOpenTab](../../scripting_reference/scripting_events/onopentab.zh.md)** 和 **[OnOpen文件窗口](../../scripting_reference/scripting_events/onopenlister.zh.md)** 事件，这些事件原本会因打开文件窗口布局而触发。

*示例：* `Prefs LAYOUT="My Layout" NOSCRIPT`
</td></tr><tr><td>
PAGE</td><td>
/K</td><td>

*\<配置页面\>*</td><td>

将配置对话框打开到指定的页面。如果未提供此参数，则配置对话框将打开到上次使用的页面。

如果您打开配置对话框，进入所需的页面，然后选择窗口顶部的 **文件/复制页面快捷方式到剪贴板**，Opus 可以为您弄清命令。

一些页面允许将数据传递给它们以指示要编辑的项目。例如，**scripts** 允许通过名称选择脚本并自动显示其配置对话框。为此，请在页面名称后面加上冒号和相应数据。

*示例：* `Prefs PAGE=transitionanimations`  
*示例：* `Prefs PAGE=scripts:dopstack.js`
</td></tr><tr><td>
PASSWORD</td><td>
/K</td><td>

*\<密码\>*</td><td>

加密配置备份（与 **BACKUP** 或 **BACKUPRESTORE** 参数一起使用）。还原备份时，您需要输入密码。

*示例：* `Prefs BACKUP TO="/desktop/PrefsBackup" PASSWORD="abc123"`
</td></tr><tr><td>
QUIET</td><td>
/S</td><td>

*(无值)*</td><td>

在备份或还原是自动执行时（与 **BACKUP** 和 **RESTORE** 参数一起使用时）防止出现 **备份和还原配置** 向导。如果在还原配置时指定，Opus 将自动重新启动 - 您可以使用 **Close AUTOLISTER** 命令控制以这种方式重新启动 Opus 时是否打开新的文件窗口。

*示例：* `Prefs RESTORE FROM="/desktop/PrefsBackup" QUIET`
</td></tr><tr><td>
RESTORE</td><td>
/O</td><td>

*(无值)*</td><td>

自动化配置还原进程。默认情况下，将还原备份中的所有配置设置、工具栏、菜单和快捷键，但图像和声音等额外数据除外。此参数的可选值可用于控制还原中包括哪些额外数据。使用 **FROM** 参数指定备份文件的文件名。如果备份文件已加密，您可以使用 **PASSWORD** 参数提供密码。**QUIET** 参数会阻止显示任何用户界面，而且还原完成后，Opus 会自动重新启动。

*示例：* `Prefs RESTORE FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**images**</td><td>

从配置备份还原图像（对应于 *[备份和还原配置](/Manual/preferences/backing_up_and_restoring_preferences.zh.md)* 向导中的 **还原图像** 选项）。

*示例：* `Prefs RESTORE=images FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**sounds**</td><td>

从配置备份还原声音（对应于向导中的 **还原声音** 选项）。

*示例：* `Prefs RESTORE=images,sounds FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**data**</td><td>

还原杂项数据（对应于向导中的 **还原杂项数据** 选项）。

*示例：* `Prefs RESTORE=data FROM="/desktop/PrefsBackup" QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**localstate**</td><td>

还原本地状态数据（对应于向导中的 **还原本地状态数据（窗口位置等）** 选项）。

*示例：* `Prefs RESTORE=data,localstate FROM="/desktop/PrefsBackup" QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

完全替换现有配置（对应于向导中同名的选项）。如果您选择此项，则在还原操作完成之前，您的现有配置会被删除。如果没有这个选项，则还原的配置文件会被覆盖到现有配置的上面 - 但这样做的效果是将诸如工具栏和具有不同名称的图像合并起来。

*示例：* `Prefs RESTORE=replace,images,sounds FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

还原配置备份中的所有项目（相当于 **RESTORE=images,sounds,data,localstate**）。

*示例：* `Prefs RESTORE=replace,all FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
SCRIPTDISABLE</td><td>
/O</td><td>

*(无值)*</td><td>

如果没有给出脚本名称，则此命令将切换全局选项以禁用所有脚本加载项。这将禁用您安装的任何事件脚本、命令脚本和列脚本。这通常用于测试问题是由于脚本还是其他原因造成的。
全局选项不会影响任何单独脚本的启用/禁用状态。换句话说，如果某个脚本已被禁用，而你随后全局禁用脚本，然后再次全局启用脚本，该脚本仍将处于禁用状态。全局设置和单独禁用所有脚本之间的另一个不同之处在于，全局设置还将影响在更改后安装的脚本。

*示例：* `Prefs SCRIPTDISABLE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<脚本名称\>*</td><td>

启用或禁用指定的脚本。脚本名应与你要影响的脚本加载项文件名相匹配。

如果已启用全部禁用所有脚本加载项的全局选项，则无法启用任何单独的脚本。

脚本名可以使用简单的\ *通配符匹配多个文件名。虽然这可用于一次启用或禁用多个脚本，但其目的是为了避免担心脚本是安装时扩展名为“.js”且“.vbs”还是“.js.txt”且“vbs.txt”样式的。

（作为特例，如果脚本名称通配符实际上为“\*”或“\*.\*”，则该命令的作用与未指定脚本名称相同，并切换全局选项以禁用所有脚本加载项。）

如果脚本名称是惟一参数，则脚本将切换（如果当前已禁用，则启用；如果当前已启用，则禁用）。如果多个脚本匹配该模式，则它们都将被设置为与第一次匹配相同的状态，而不是单独切换。

*示例：* `Prefs SCRIPTDISABLE="My Script.js\*"`

如果脚本位于脚本包（.osp文件）中，则必须在名称中包含该包：

*示例：* `Prefs SCRIPTDISABLE="My Package.osp\My Script.vbs"`

通配符可以使处理脚本包变得更容易，还可以处理包含多个脚本或以.osp格式分发脚本给其他人，但作为文本文件私下处理它的脚本包：

*示例：* `Prefs SCRIPTDISABLE="My Package.osp\*"`  
*示例：* `Prefs SCRIPTDISABLE="\*My Script.vbs\*"`
</td></tr><tr><td>
</td><td>
</td><td>

**启用**</td><td>

启用所指定的脚本或者（如果没有指定脚本名称）所有脚本。

*示例：* `Prefs SCRIPTDISABLE="My Script.js\*,enable"`  
*示例：* `Prefs SCRIPTDISABLE=enable`
</td></tr><tr><td>
</td><td>
</td><td>

**禁用**</td><td>

禁用所指定的脚本或者（如果没有指定脚本名称）所有脚本。

*示例：* `Prefs SCRIPTDISABLE="My Script.js\*,disable"`  
*示例：* `Prefs SCRIPTDISABLE=disable`
</td></tr><tr><td>
</td><td>
</td><td>

**切换**</td><td>

切换指定的脚本或者（如果没有指定脚本名称）所有脚本。

（这是默认设置，如果没有指定“enable”或“disable”，但你可以包含它以使其更明确。）

*示例：* `Prefs SCRIPTDISABLE="My Script.js\*,toggle"`  
*示例：* `Prefs SCRIPTDISABLE=toggle`

请注意，当**SCRIPTDISABLE**按钮为切换时，当脚本*禁用*时，按钮将显示为活动（例如，选中或突出显示）。与大多数命令一样，可以在命令序列顶部的第一行添加**@toggle:invert**以反转此设置。

//<Example://>

    @toggle:invert
    Prefs SCRIPTDISABLE="Viewer Select.js,toggle"
</td></tr><tr><td>
SCRIPTEDIT</td><td>
/K</td><td>

*\<脚本名称\>*</td><td>

为指定的脚本启动[脚本编辑器](/Manual/scripting/script_editor/README.zh.md)。如果你正在处理某个特定脚本，这可以让你快速编辑它，而无需通过[脚本管理](/Manual/scripting/script_management/README.zh.md)界面。

脚本名可以使用简单的\ *通配符来避免担心脚本是安装时扩展名为“.js”且“.vbs”还是“.js.txt”且“vbs.txt”样式的。

*示例：* `Prefs SCRIPTEDIT="My Script.js\*"`

如果脚本位于脚本包（.osp文件）中，则必须在名称中包含该包：

*示例：* `Prefs SCRIPTEDIT="My Package.osp\My Script.vbs"`
</td></tr><tr><td>
SCRIPTINSTALL</td><td>
/O</td><td>

*(无值)*</td><td>

启动[安装程序](/Manual/scripting/script_management/installer.zh.md)来安装当前选定的脚本文件。

*示例：* `Prefs SCRIPTINSTALL`
</td></tr><tr><td>
</td><td>
</td><td>

*\<文件路径\>*</td><td>

启动脚本安装程序以安装指定脚本文件。

*示例：* `Prefs SCRIPTINSTALL /downloads/CoolScript.osp`
</td></tr><tr><td>
SCRIPTS</td><td>
/O</td><td>

*(无值)*</td><td>

显示[脚本管理](/Manual/scripting/script_management/README.zh.md)对话框——创建、编辑、管理和共享脚本加载项的集中枢纽。

*示例：* `Prefs SCRIPTS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<脚本名称\>*</td><td>

显示脚本管理对话框，在列表中选择指定的脚本，并（如果脚本有配置项）显示其配置对话框。脚本名称应与你要编辑其配置的脚本加载项的文件名相匹配。

脚本名可以使用简单的\ *通配符来避免担心脚本是安装时扩展名为“.js”且“.vbs”还是“.js.txt”且“vbs.txt”样式的。

*示例：* `Prefs SCRIPTS="My Script.js\*"`

如果脚本位于脚本包（.osp文件）中，则必须在名称中包含该包：

*示例：* `Prefs SCRIPTS="My Package.osp\My Script.vbs"`

通配符可以使处理脚本包变得更容易，还可以处理包含多个脚本或以.osp格式分发脚本给其他人，但作为文本文件私下处理它的脚本包：

*示例：* `Prefs SCRIPTS="My Package.osp\*"`  
*示例：* `Prefs SCRIPTS="\*My Script.vbs\*"`
</td></tr><tr><td>
</td><td>
</td><td>

**!scriptlist**</td><td>

生成所有脚本加载项的列表（充当[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。

从生成列表中选择一个项目将显示包含已选择项目（以及如果有的话，显示其配置对话框）的脚本管理对话框。

*示例：* `Prefs SCRIPTS=!scriptlist`
</td></tr><tr><td>
SETLISTERDEFAULTS</td><td>
/O</td><td>

*(无值)*</td><td>

让你选择一个文件窗口保存为[默认文件窗口](/Manual/basic_concepts/the_lister/the_default_lister.zh.md)，或设置其他默认参数。

*示例：* `Prefs SETLISTERDEFAULTS`
</td></tr><tr><td>
</td><td>
</td><td>

**强制**</td><td>

手动设置默认文件窗口时取消确认和成功提示。

*示例：* `Prefs SETLISTERDEFAULTS=force`
</td></tr><tr><td>
</td><td>
</td><td>

**安静**</td><td>

设置默认文件窗口时取消成功提示。

*示例：* `Prefs SETLISTERDEFAULTS=quiet`
</td></tr><tr><td>
</td><td>
</td><td>

**nodeflister**</td><td>

关闭保存*默认文件窗口*的同时，仍保存其他默认参数。

*示例：* `Prefs SETLISTERDEFAULTS=quiet,nodeflister`
</td></tr><tr><td>
</td><td>
</td><td>

**工具栏**</td><td>

从所选文件窗口保存默认[工具栏集](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.zh.md)。

*示例：* `Prefs SETLISTERDEFAULTS=toolbars,nodeflister`
</td></tr><tr><td>
VFSPLUGINHELP</td><td>
/K</td><td>

*\<plugin name\>*</td><td>

Displays the **Help** file for the specified VFS plugin, if any.

*Example:* `Prefs VFSPLUGINHELP opus7zip.dll`
</td></tr><tr><td>
VFSPLUGINLIST</td><td>
/S</td><td>

*(no value)*</td><td>

Displays a list of your installed VFS plugins (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)). Selecting a plugin from the generated list displays its **About** dialog.

*Example:* `Prefs VFSPLUGINLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**<mark class="highlight">installed</mark>**</td><td>

Lists only the currently installed plugins.

*Example:* `Prefs VFSPLUGINLIST=<mark class="highlight">installed</mark>`
</td></tr><tr><td>
</td><td>
</td><td>

**<mark class="highlight">all</mark>**</td><td>

Lists both installed and uninstalled plugins.

*Example:* `Prefs VFSPLUGINLIST=<mark class="highlight">all</mark>`
</td></tr><tr><td>
</td><td>
</td><td>

**<mark class="highlight">showfiles</mark>**</td><td>

Includes a list of the files a particular VPS plugin is registered to handle.

*Example:* `Prefs VFSPLUGINLIST=<mark class="highlight">showfiles</mark>`
</td></tr><tr><td>
VFSPLUGINONOFF</td><td>
/O</td><td>

*\<plugin name\>*</td><td>

Enable or disable the specified VFS plugin. If the plugin is currently enabled it will be disabled, and vice versa.

*Example:* `Prefs VFSPLUGINONOFF opus7zip.dll`

A single VFS plugin DLL may present itself as multiple types. For example, the Archives plugin (opus7zip.dll) which comes with Opus has separate types for 7z, RAR, ISO, and so on. If you specify just the name of the DLL, the entire plugin will be toggled. You can also toggle individual types (assuming the plugin as a whole is still enabled) by adding a ':' character after the DLL name and then the name of the type, as found in the Preferences VFS Plugins page.
</td></tr><tr><td>
VFSPLUGINREGISTER</td><td>
/K</td><td>

*\<plugin name\>*</td><td>

Registers the specified VFS plugin with Opus. Requires that (a) the specified VFS plugin is installed on your system, and (b) you know the exact name of the file.

*Example:* `Prefs VFSPLUGINREGISTER opus7zip.dll`

A single VFS plugin DLL may present itself as multiple types. For example, the Archives plugin (opus7zip.dll) which comes with Opus has separate types for 7z, RAR, ISO, and so on. You can either specify just the name of the DLL, in which case all types within that DLL will be registered, or you can specify a particular type by adding a ':' character after the DLL name and then the name of the type, as found in the Preferences VFS Plugins page.

*Example:* `Prefs VFSPLUGINREGISTER opus7zip.dll:7z`
</td></tr><tr><td>
VFSPLUGINS</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the **VFS Plugins** page in Preferences (equivalent to `Prefs PAGE=vfs`).

*Example:* `Prefs VFSPLUGINS`
</td></tr><tr><td>
VFSPLUGINSETTYPEGROUP</td><td>
/K</td><td>

*\<plugin name\>*</td><td>

The default subtype (as displayed in the VFS Plugins page in Preferences) for the specified VFS plugin.

*Example:* `Prefs VFSPLUGINSETTYPEGROUP opus7zip.dll "Data Archives"`
</td></tr><tr><td>
VFSPLUGINUNREGISTER</td><td>
/K</td><td>

*\<plugin name\>*</td><td>

Unregisters the specified VFS plugin from Opus.

*Example:* `Prefs VFSPLUGINUNREGISTER opus7zip.dll`

A single VFS plugin DLL may present itself as multiple types. For example, the Archives plugin (opus7zip.dll) which comes with Opus has separate types for 7z, RAR, ISO, and so on. You can either specify just the name of the DLL, in which case all types within that DLL will be unregistered, or you can specify a particular type by adding a ':' character after the DLL name and then the name of the type, as found in the Preferences VFS Plugins page.

*Example:* `Prefs VFSPLUGINUNREGISTER opus7zip.dll:7z`
</td></tr><tr><td>
VIEW</td><td>
/K</td><td>

*\<view mode\>*</td><td>

Sets the view mode of the active文件窗口to the specified value. If used on its own, without a value, it will toggle between two of the following:

* <mark class="highlight">Details</mark> (alternatively: <mark class="highlight">Extended</mark>)
* <mark class="highlight">List</mark>
* <mark class="highlight">Tiles</mark>

The following values can also be used:

* <mark class="highlight">Mini Icons</mark> (alternatively: <mark class="highlight">Thumbnails</mark>)
* <mark class="highlight">Preview</mark>
* <mark class="highlight">Thumbnails</mark>

*Example:* `Prefs VIEW="Details"`
</td></tr>
*示例：* `Prefs VFSPLUGINDISABLE opus7zip.dll:rar`
</td></tr><tr><td>
</td><td>
</td><td>

**启用**</td><td>

启用指定 VFS 插件。

*示例：* `Prefs VFSPLUGINDISABLE opus7zip.dll,enable`
</td></tr><tr><td>
</td><td>
</td><td>

**禁用**</td><td>

禁用指定 VFS 插件。

*示例：* `Prefs VFSPLUGINDISABLE opus7zip.dll,disable`
</td></tr><tr><td>
</td><td>
</td><td>

**切换**</td><td>

如果未指定“启用”或“禁用”，则切换为默认值，但如果您希望更明确，则可以指定“切换”。

注意，当 **VFSPLUGINDISABLE** 按钮为切换时，当插件被 *禁用* 时，按钮将显示处于活动状态（例如，选中或高亮显示）。与大多数命令一样，您可以在命令序列顶部的新行中添加 **@toggle:invert** 来反转此操作。

//<示例：//>

    @toggle:invert
    Prefs VFSPLUGINDISABLE="opus7zip.dll,toggle"
</td></tr><tr><td>
VFSPLUGINLIST</td><td>
/S</td><td>

*(无值)*</td><td>

显示已安装 VFS 插件的列表（充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。列表中的每个插件都有一个子菜单，其中包含 *关于*、*配置* 和 *启用/禁用* 命令。

*示例：* `Prefs VFSPLUGINLIST`
</td></tr><tr><td>
VFSPLUGINMANAGER</td><td>
/S</td><td>

*(无值)*</td><td>

在配置中显示 **[zip 及其他压缩包 / 压缩包和 VFS 插件](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_and_vfs_plugins.zh.md)** 页面（相当于 `Prefs PAGE=vfsplugins`）。

*示例：* `Prefs VFSPLUGINMANAGER`
</td></tr></tbody>
</table>

**查看器插件：**有关管理查看器插件，请参阅单独的 **[Show 命令](show.zh.md)**。