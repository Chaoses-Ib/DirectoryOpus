# Clipboard
**剪贴板**内部命令可用于：

- 从一个文件夹复制和粘贴文件和文件夹到另一个文件夹
- 复制所选文件和文件夹的**名称**到剪贴板
- 将图像或文本数据从剪贴板粘贴为磁盘上的文件
- 从剪贴板将文件、图片或文本数据粘贴到压缩包中（新建或现有）

**命令参数：** 

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
说明
</th></tr></thead><tbody><tr><td>
ADD</td><td>
/S</td><td>
（无值）</td><td>

将其他文件添加到剪贴板上已经存在的文件，而不是替换它们。它与 **COPY** 或 **CUT** 结合使用。这允许您从不同源文件夹向剪贴板放置多个项目，然后一次性粘贴到期望的目标文件夹中。

*示例:* `Clipboard COPY ADD`
</td></tr><tr><td>
AS</td><td>
/K</td><td>

*\<filename\>*</td><td>

覆盖将图像或文本粘贴到磁盘时使用的默认文件名。

在正常情况下，当您粘贴剪贴板图像数据时，Opus 会创建一个名为 *Clipboard Image.png* 的文件（或其他后缀，具体取决于文件格式），当您粘贴文本数据时，Opus 会创建一个名为 *Clipboard Text.txt* 的文件。使用此参数更改文件名。

如果文件名中未指定扩展名，会自动添加默认文件扩展名（例如文本数据的 .txt）。

您可以指定一个完整路径，使该命令始终保存到特定文件夹，而不是当前路径。

在将剪贴板内容作为压缩包粘贴时（例如使用 **Clipboard PASTE=zip**）也可以使用此参数。在这种情况下，压缩包的文件名通常会根据剪贴板内容自动生成 - 此参数允许您覆盖它。

*示例:* `Clipboard PASTE AS PastedData`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

将图片或文本数据粘贴到文件时，此参数会提示您输入所创建文件的文件名。针对文本时，您还可以选择编码类型，针对图片数据时，可以选择要使用的图片格式。

![](/Manual/images/media/paste_as.png)在将剪贴板内容粘贴为压缩包（例如使用 **Clipboard PASTE=7z**）时，此参数也可以使用。在这种情况下，您将被提示输入新压缩包的名称和任何压缩包特定格式的参数。

如果系统 DPI 高于 100%，**缩小图像以补偿系统 DPI** 选项将缩小粘贴的图像。

您还可以指定要在对话框中显示的默认文件名，如下面的第二个示例所示。

*示例:* `Clipboard PASTE AS=ask`  
*示例:* `Clipboard PASTE AS=ask:{date\|yyyy_MM}\_`
</td></tr><tr><td>
COPY</td><td>
/S</td><td>

*(无值)*</td><td>

将所有选中的文件和文件夹复制到剪贴板。

*示例:* `Clipboard COPY`
</td></tr><tr><td>
COPYCOMMANDARGS</td><td>
/K</td><td>

*\<arguments\>*</td><td>

配合 **Clipboard PASTE** 使用时，允许您为 **Copy** 命令提供其他参数（如果粘贴命令最终运行了 **Copy** 命令）。如果粘贴命令不使用 **Copy** 命令（例如，剪贴板上存在位图数据，且创建了一个图像文件），则将忽略该参数。

*示例:* `Clipboard PASTE COPYCOMMANDARGS="FLATVIEWCOPY=autosingle,recreate"`
</td></tr><tr><td>
COPYIMAGE</td><td>
/S</td><td>

*(无值)*</td><td>

将选中的图像文件复制到剪贴板**作为图像**，以便粘贴到其他程序中。

*示例:* `Clipboard COPYIMAGE`
</td></tr><tr><td>
COPYINFOTIP</td><td>
/S</td><td>

*(无值)*</td><td>

复制当前可见*信息提示*中的文本内容到剪贴板。（信息提示是在您将鼠标悬停在文件或文件夹上时显示信息的“工具提示”。）

如果列表中没有可见的信息提示，则不执行任何操作。此命令仅在分配给热键时才有意义，因为如果您移动鼠标单击工具栏按钮，信息提示将关闭。

*示例:* `Clipboard COPYINFOTIP`

默认情况下，您还可以使用 <kbd>Ctrl+Shift+Alt+C</kbd> 进行相同操作，而无需创建热键，但该命令允许您为其提供另一种键，其输入方式更简单。（<kbd>Ctrl+Shift+C</kbd> 也可以，但会被默认的工具栏覆盖，默认的工具栏将 <kbd>Ctrl+Shift+C</kbd> 分配给 *编辑 \> 复制完整路径*。）
</td></tr><tr><td>
COPYNAMES</td><td>
/O</td><td>

*(无值)*</td><td>

将所有选中的文件和文件夹的名称复制到剪贴板（实际复制的是文件名本身，采用文本格式，而不是实际文件）。

默认格式（未指定值）会将所有所选项目的完整路径和文件名复制到剪贴板，每一行一个文件。例如，

    C:\Windows\notepad.exe
    C:\Windows\regedit.exe

**COPYNAMES** 参数的不同值允许您修改复制文件名的格式。某些值可以组合 - 请参阅下面提供的示例以获取有关您可以做什么的想法。另请参阅 **REGEXP** 参数，该参数允许您使用正则表达式自行控制格式。

*示例:* `Clipboard COPYNAMES`
</td></tr><tr><td>
</td><td>
</td><td>

**noexts**</td><td>

移除复制到剪贴板中的文件名的扩展名。例如，

    C:\Windows\notepad
    C:\Windows\regedit

*示例:* `Clipboard COPYNAMES=noexts`
</td></tr><tr><td>
</td><td>
</td><td>

**nopaths**</td><td>

仅将选中项目的名称复制到剪贴板 - 不会复制路径。例如，

    notepad.exe
    regedit.exe

*示例:* `Clipboard COPYNAMES=nopaths`  
*示例:* `Clipboard COPYNAMES=nopaths,noexts`
</td></tr><tr><td>
</td><td>
</td><td>

**url**</td><td>

将选中项目的名称以 URL 格式复制到剪贴板。对于 FTP 站点上的文件，这将产生其他 FTP 程序应该接受的 **ftp://** 样式的路径。对于本地文件，文件名将复制为 **file://** 样式的链接（例如 //[file:///C:/Windows//](file:///C:/Windows//)）。例如，

    file:///C:/Windows/notepad.exe
    file:///C:/Windows/regedit.exe

*示例:* `Clipboard COPYNAMES=url`
</td></tr><tr><td>
</td><td>
</td><td>

**hash**</td><td>

复制每个所选文件的文件名及其 **MD5** 校验和。例如，

    notepad.exe : f2c7bb8acc97f92e987a2d4087d021b1\\
    regedit.exe : 2e2c937846a0b8789e5e91739284d17a

*示例:* `Clipboard COPYNAMES=hash`
</td></tr><tr><td>
</td><td>
</td><td>

**hash2**</td><td>

以备用格式复制选中文件的 **MD5** 校验和，该格式兼容老牌 *MD5Sum* 实用工具。例如，

    f2c7bb8acc97f92e987a2d4087d021b1 *notepad.exe
    2e2c937846a0b8789e5e91739284d17a *regedit.exe

*示例:* `Clipboard COPYNAMES=hash2`
</td></tr><tr><td>
</td><td>
</td><td>

**hash3**</td><td>

复制选中文件（**不带** 文件名）的 **MD5** 校验和。您可能只想一次在单个文件上使用此格式。例如，

    f2c7bb8acc97f92e987a2d4087d021b1
    2e2c937846a0b8789e5e91739284d17a

*示例:* `Clipboard COPYNAMES=hash3`
</td></tr><tr><td>
</td><td>
</td><td>

**hash4**</td><td>

复制每个所选文件的文件名以及其**SHA-1** 校验和。例如，
    notepad.exe : 7eb0139d2175739b3ccb0d1110067820be6abd29
    regedit.exe : f48138dc476e040b8a9925c7d2650b706178e863

*示例：* `Clipboard COPYNAMES=hash4`
</td></tr><tr><td>
</td><td>
</td><td>

**hash5**</td><td>

以另一种格式复制已选文件的 **SHA-1** 校验和。例如：

    7eb0139d2175739b3ccb0d1110067820be6abd29 *notepad.exe
    f48138dc476e040b8a9925c7d2650b706178e863 *regedit.exe

*示例：* `Clipboard COPYNAMES=hash5`
</td></tr><tr><td>
</td><td>
</td><td>

**hash6**</td><td>

**不带** 文件名的 **SHA-1** 校验和复制已选文件。可能只想一次在一个文件上使用这种格式。 For example,

    7eb0139d2175739b3ccb0d1110067820be6abd29
    f48138dc476e040b8a9925c7d2650b706178e863

*示例：* `Clipboard COPYNAMES=hash6`
</td></tr><tr><td>
</td><td>
</td><td>

**hashcache**</td><td>

为任一 **hash** 选项添加 **hashcache** 关键字，使 Opus 使用校验和缓存；如果文件已经计算出它的校验和并且看起来没有更改，则将使用缓存值。

*示例：* `Clipboard COPYNAMES=hash2,hashcache`
</td></tr><tr><td>
</td><td>
</td><td>

**unc**</td><td>

当指定 **unc** 值，且要复制其名称的文件位于映射网络驱动器上时，该函数将解析其映射路径到 UNC 路径并将其复制到剪贴板中。例如，如果 **Z:** 是一个映射网络驱动器，则 **Clipboard COPYNAMES** 返回：

    Z:\Windows\notepad.exe
    Z:\Windows\regedit.exe

而 **Clipboard COPYNAMES=unc** 可能返回：

    \\win7vm\c\Windows\notepad.exe
    \\win7vm\c\Windows\regedit.exe

如果当前文件夹不在映射网络驱动器上，则 unc 参数无效。

*示例：* `Clipboard COPYNAMES=unc`
</td></tr><tr><td>
</td><td>
</td><td>

**short**</td><td>

复制所选路径的短（8.3）版本，而不是长版本。例如：

    C:\PROGRA~1\GPSOFT~1\DIRECT~1\dopus.exe
    C:\PROGRA~1\GPSOFT~1\DIRECT~1\dopuslib.dll

*示例：* `Clipboard COPYNAMES=short,nopaths`

并非所有驱动器都启用了短路径。在没有启用短路径的驱动器上，将复制普通长路径。
</td></tr><tr><td>
</td><td>
</td><td>

**single**</td><td>

当选择多个文件时，这将在单行上复制所有名称（由空格分隔），而不是每行一个项目。如果任何项目名称包含一个空格，它们将被引号包围。例如：

    dopus.exe dopuslib.dll "Opus 13 What's New.pdf"

*示例：* `Clipboard COPYNAMES=nopaths,single`
</td></tr><tr><td>
</td><td>
</td><td>

**paths**</td><td>

仅复制所选项目路径，不包括文件名（与 **nopaths** 相反）。例如：

    C:\Program Files\GPSoftware\Directory Opus

*示例：* `Clipboard COPYNAMES=paths`

为了向后兼容，**path** 也被识别且执行相同操作。
</td></tr><tr><td>
</td><td>
</td><td>

**capsemantics**</td><td>

使函数的行为与 Windows *复制为路径* 上下文菜单命令类似（每行一个文件路径，并且行始终被引用）。

*示例：* `Clipboard COPYNAMES=capsemantics`
</td></tr><tr><td>
</td><td>
</td><td>

**quote**</td><td>

强制将复制到剪贴板的文件名和路径用双引号括起来，即使它们不包含空格（因此通常不需要引号）。

*示例：* `Clipboard COPYNAMES=quote`
</td></tr><tr><td>
</td><td>
</td><td>

**wsl**</td><td>

以 WSL（适用于 Linux 的 Windows 子系统）格式复制文件路径。例如，**C:\Temp** 将转换为 **/mnt/c/Temp**。

*示例：* `Clipboard COPYNAMES=wsl`
</td></tr><tr><td>
COPYQUEUE</td><td>
/O</td><td>

*(no value)*</td><td>

与 **PASTE** 参数结合使用，启用 [复制队列](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/README.zh.md) 的文件粘贴。如果没有指定值，则需要时会自动对复制进行排队。这可以覆盖 **[复制文件](/Manual/preferences/preferences_categories/file_operations/copying_files/README.zh.md)** 配置页面上的 **自动管理文件复制队列** 选项。

*示例：* `Clipboard PASTE COPYQUEUE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<queue name\>*</td><td>

当为该参数指定队列名称作为值时，在粘贴文件时会启用人工复制队列。也就是说，指定名称后，文件粘贴将始终排队到指定的队列 - 如果未指定参数名称，只有需要时才会将粘贴排队。

*示例：* `Clipboard PASTE COPYQUEUE=MyQueue`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

用于禁用复制队列 - 无论是在配置中启用，还是通过关键字 **shift** 启用。

*示例：* `Clipboard PASTE COPYQUEUE=none`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

允许为 **COPYQUEUE** 参数指定两个备用参数。如果未按住 **Shift** 键，则使用 **shift** 关键字之前指定的值 - 如果按住，则使用它之后指定的值。例如，可以将一个粘贴按钮配置为在按住 <kbd>Shift</kbd> 键时将文件排队到特定队列，否则禁用排队。

*示例：* `Clipboard PASTE COPYQUEUE=none,shift,MyQueue`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

指定 **quiet** 关键字以禁止提示通常指示已排队复制操作。

*示例：* `Clipboard PASTE COPYQUEUE=MyQueue,quiet`
</td></tr><tr><td>
CUT</td><td>
/S</td><td>

*(no value)*</td><td>

将所有选定的文件和文件夹剪切到剪贴板（目前不会对文件产生任何影响，但是当你将它们粘贴到其他位置时，它们会被移动而不是复制）。

*示例：* `Clipboard CUT`
</td></tr><tr><td>
CUTNOCOPYQUEUEWHENSAME</td><td>
/S</td><td>

*(no value)*</td><td>

与 **Clipboard PASTE** 一起使用，禁用在剪贴板上的文件被剪切（即移动）时使用复制队列以及源和目标位于同一驱动器分区上。

*示例：* `Clipboard PASTE CUTNOCOPYQUEUEWHENSAME`
</td></tr><tr><td>
EXPANDNEWLINES</td><td>
/S</td><td>

*(no value)*</td><td>

与 **Clipboard SET** 一起使用，允许使用 **\n** 在字符串中插入新行，以便可以设置由多行组成的剪贴板字符串。还可以使用 **\\** 插入反斜杠。

*示例：* `Clipboard EXPANDNEWLINES SET Hello\nWorld`

当使用 **EXPANDNEWLINES** 在剪贴板字符串中插入路径时，应该使用 **[escbackslash](../external_control_codes/codes_for_passing_paths.zh.md)** 来防止错误地解释路径中的反斜杠。

*示例（全部在一行中）：*  
**Clipboard EXPANDNEWLINES SET {sourcepath\|escbackslash}\n{destpath\|escbackslash}**
</td></tr><tr><td>
FILE</td><td>
/K/M</td><td>

*\<filename\>, ...*</td><td>

指定要操作的文件。如果没有指定，该命令将对当前选定的所有文件进行操作。

*示例：* `Clipboard COPY FILE "C:\moo.zip" "C:\cow.zip"`
NEWLINEIFADDING</td><td>
/S</td><td>

*(无值)*</td><td>

与 **Clipboard ADD SET** 一起使用，可在现有的剪贴板数据和要添加的字符串之间添加一个新行。如果剪贴板当前为空或有非文本数据，则不会添加新行。

*示例:* `Clipboard ADD NEWLINEIFADDING SET 这是一行新文本.`
</td></tr><tr><td>
NOFROMFOCUS</td><td>
/S</td><td>

*(无值)*</td><td>

**Clipboard** 命令的默认行为是对源文件列表或文件夹树进行操作，具体取决于哪个有输入焦点。这使您可以使用相同的命令来复制树中的文件夹以及文件列表中的文件。指定此参数可强制命令始终对源文件列表进行操作，并忽略文件夹树。

*示例:* `Clipboard COPY NOFROMFOCUS`
</td></tr><tr><td>
PASTE</td><td>
/O</td><td>

*(无值)*</td><td>

将以前复制到剪贴板的文件和文件夹粘贴到当前的文件窗口中。

如果通过“剪切”操作将文件放在剪贴板上，则将移动它们，否则将复制到新位置。

还可以将图像和文本数据从剪贴板粘贴到当前文件夹中的新文件中。粘贴图像和文本数据时，**AS** 参数可以更改所创建文件的文件名和路径。

*示例:* `Clipboard PASTE`
</td></tr><tr><td>
</td><td>
</td><td>

**enc:***\<编码\>*</td><td>

从剪贴板向文件粘贴文本时，指定编码类型。默认行为是如果剪贴板文本是 Unicode，则粘贴为 UTF-16，否则为 ANSI。

受支持的编码类型有 **oem**、**ansi**、**utf8**、**utf8nobom**、**utf16**、**utf16nobom**。

*示例:* `Clipboard PASTE=enc:utf8`
</td></tr><tr><td>
</td><td>
</td><td>

**jpg**</td><td>

强制将剪贴板上的图像数据粘贴为 JPEG 格式（覆盖配置默认设置）。您还可以指定 JPEG 图像质量。

*示例:* `Clipboard PASTE=jpg:85`
</td></tr><tr><td>
</td><td>
</td><td>

**png**</td><td>

将图像数据粘贴为 PNG 格式。

*示例:* `Clipboard PASTE=png`
</td></tr><tr><td>
</td><td>
</td><td>

**gif**</td><td>

将图像数据粘贴为 GIF 格式。

*示例:* `Clipboard PASTE=gif`
</td></tr><tr><td>
</td><td>
</td><td>

**bmp**</td><td>

将图像数据粘贴为 BMP 格式。

*示例:* `Clipboard PASTE=bmp`
</td></tr><tr><td>
</td><td>
</td><td>

**zip**</td><td>

将剪贴板内容（文件、图像或文本数据）粘贴为新的 ZIP 档案。档案的文件名将根据剪贴板内容自动生成 - 您可以使用 **AS** 参数覆盖它。
</td></tr><tr><td>
</td><td>
</td><td>

**7z**</td><td>
将剪贴板内容粘贴为一个新的 7 Zip 档案。
</td></tr><tr><td>
</td><td>
</td><td>

*\<档案后缀\>*</td><td>
将剪贴板内容粘贴为指定类型的新压缩包（您可以指定 Opus 支持创建的任何档案后缀）。
</td></tr><tr><td>
PASTELINK</td><td>
/O</td><td>

*(无值)*</td><td>

将以前复制到剪贴板的任何文件和文件夹的快捷方式粘贴到当前文件窗口中。例如，如果您对 *C:\Windows* 文件夹使用 **Clipboard COPY** 命令，导航到另一个文件夹，并运行 **Clipboard PASTELINK** 命令，它将粘贴一个名为 *Windows - Shortcut.lnk* 的快捷方式。

*示例:* `Clipboard PASTELINK`
</td></tr><tr><td>
</td><td>
</td><td>

**junction**</td><td>

创建到剪贴板上任何文件夹的连接。连接仅在 NTFS 卷上受支持，并且您不能创建到文件的连接 - 只能连接到文件夹。

*示例:* `Clipboard PASTELINK=junction`
</td></tr><tr><td>
</td><td>
</td><td>

**hardlink**</td><td>

创建到剪贴板上任何文件的硬链接。硬链接仅在 NTFS 卷上受支持，并且您不能创建到文件夹的硬链接 - 只能连接到文件。

*示例:* `Clipboard PASTELINK=hardlink`
</td></tr><tr><td>
</td><td>
</td><td>

**softlink**</td><td>

创建到剪贴板上任何文件或文件夹的软链接。请注意，链接目标存储为绝对路径。软链接同时支持文件和文件夹，但仅在 Vista 及更高版本上支持（而且，仅在 NTFS 卷上支持）。创建软链接需要管理员访问权限，因此在您运行此命令时，Opus 会在必要时显示 UAC 提示。

*示例:* `Clipboard PASTELINK=softlink`
</td></tr><tr><td>
</td><td>
</td><td>

**relsoftlink**</td><td>

创建到剪贴板上任何文件或文件夹的软链接，如果可能，存储相对目标路径。如果无法相对于链接来表示目标，则将创建规则的绝对链接。

*示例:* `Clipboard PASTELINK=relsoftlink`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

自动确定要创建的最合适的链接类型。在 Vista 及更高版本上，这将是软链接 - 在 Windows XP 中，将根据项类型创建连接或硬链接。如果剪贴板上是非文件系统对象（例如您尝试链接到像“控制面板”这样的虚拟文件夹），或者目标驱动器没有使用 NTFS 格式化，那么它将创建快捷方式。

*示例:* `Clipboard PASTELINK=auto`
</td></tr><tr><td>
</td><td>
</td><td>

**autonosoft**</td><td>

与 **auto** 相同，不同之处在于它不会尝试创建软链接。换句话说：它将根据项类型创建连接或硬链接。如果剪贴板上是非文件系统对象（例如您尝试链接到像“控制面板”这样的虚拟文件夹），或者目标驱动器没有使用 NTFS 格式化，那么它将创建快捷方式。

*示例:* `Clipboard PASTELINK=autonosoft`
</td></tr><tr><td>
PREFERIMAGE</td><td>
/S</td><td>

*(无值)*</td><td>

将剪贴板中的数据粘贴到新文件时，通常图像数据优先于文本数据。Opus 在某些情况下对这一规则进行例外处理。

例如，如果您使用 Microsoft Excel 并将某些单元格复制到剪贴板，Excel 会将单元格中的文本和它们的屏幕截图放入剪贴板中。从 Excel 粘贴数据时，人们通常需要文本，而不是屏幕截图。因此，当 Opus 检测到粘贴的数据来自 Excel 时，它会使文本优先于图像，这与它对来自其他程序的数据的行为相反。

如果指定 **PREFERIMAGE** 参数，则无论数据来自何处，图像数据将*始终*优先于文本数据。这样您就可以粘贴 Excel 中的图像数据（如果这是您想要的）。（如果剪贴板中只有文本数据，您仍将得到一个文本文件。）

*示例:* `Clipboard PASTE PREFERIMAGE`
</td></tr><tr><td>
PREFERTEXT</td><td>
/S</td><td>

*(无值)*</td><td>

将剪贴板中的数据粘贴到新文件时，通常图像数据优先于文本数据。（此规则有例外情况；请参阅上面的 **PREFERIMAGE** 参数。）

通常，如果另一个程序将文本和图像数据同时放入剪贴板中，然后您在 Opus 中粘贴以将数据保存到新文件中，则文本数据将被忽略，您将获得一个图像文件（BMP、JPG、GIF 或 PNG）。

例如，绘图程序可能会将照片和照片描述同时放入剪贴板中，而粘贴到 Opus 中通常会创建包含照片的图像文件，而不是包含描述的文本文件。
**PREFERTEXT** 参数优先考虑文本而不是图像，因此在这种情况下你将获得一个文本文件。（如果剪贴板中仅有图像数据，你仍然会获得一个图像文件。）

*示例：* `Clipboard PASTE PREFERTEXT`
</td></tr><tr><td>
REGEXP</td><td>
/K/M</td><td>

*\<搜索\> \<替换\> ...*</td><td>

结合 **COPYNAMES** 让你可以在将文件名放置到剪贴板时对它们执行 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md) 操作，这实际上让你能够决定你自己的剪贴板格式。

为此参数指定的值是一对或多对字符串 - 每一对中第一个是搜索模式，每一对中第二个是替换字符串。例如，要删除所有文件名在复制到剪贴板时的后缀，则搜索字符串应为 **(.\*)\\(.\*)**，替换字符串应为 **\1**。

*示例：* `Clipboard COPYNAMES=nopaths REGEXP "(.\*)\\(.\*)" "\1"`
</td></tr><tr><td>
SCREENSHOT</td><td>
/O</td><td>

*(无值)*</td><td>

截取活动文件窗口的屏幕截图并将其复制到剪贴板。等同于按下 <kbd>Alt+PrtScr</kbd>。

*示例：* `Clipboard SCREENSHOT`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

截取桌面的屏幕截图并将它复制到剪贴板。等同于按下 <kbd>PrtScr</kbd>。

*示例：* `Clipboard SCREENSHOT=all`
</td></tr><tr><td>
</td><td>
</td><td>

**format**</td><td>

当指定 **save** 参数时，这让你可以指定保存屏幕截图的文件格式。支持的格式有 **jpg**、**png**、**gif** 和 **bmp**。

*示例：* `Clipboard SCREENSHOT=save,format:jpg`
</td></tr><tr><td>
</td><td>
</td><td>

**name**</td><td>

当指定 **save** 参数时，这让你可以配置保存屏幕截图的名称。如果没有指定，将使用默认名称。你可以使用 **%date%** 代码在名称中插入当前日期。如果期望的名称中有空格，请记住用引号将 SCREENSHOT 参数的值括起来。

*示例：* `Clipboard SCREENSHOT=save,name:My_Opus\_%date\\`  
*示例：* `Clipboard SCREENSHOT "save,name:Opus Screenshot"`
</td></tr><tr><td>
</td><td>
</td><td>

**quality**</td><td>

当指定 save 参数并将屏幕截图保存为 jpeg 图像时，这让你可以指定压缩图像的质量。

*示例：* `Clipboard SCREENSHOT=save,format:jpg,quality:85`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

在截取屏幕截图后，不会显示确认消息。

*示例：* `Clipboard SCREENSHOT=all,quiet`
</td></tr><tr><td>
</td><td>
</td><td>

**save**</td><td>

屏幕截图将自动保存到桌面（以及复制到剪贴板）。使用 **format** 和 **quality** 参数来控制文件类型。你可以使用 **name** 参数配置名称。

*示例：* `Clipboard SCREENSHOT=save`
</td></tr><tr><td>
</td><td>
</td><td>

**secure**</td><td>

在截取屏幕截图时，将对文件窗口中的文件名进行模糊处理，以隐藏可能包含敏感信息的内容。

*示例：* `Clipboard SCREENSHOT=all,secure`
</td></tr><tr><td>
</td><td>
</td><td>

**time**</td><td>

在截取屏幕截图之前，显示一个倒数计时器。

*示例：* `Clipboard SCREENSHOT=secure,time:10`
</td></tr><tr><td>
SET</td><td>
/K/R</td><td>
用户定义</td><td>

将所提供的文本复制到剪贴板。

*示例：* `Clipboard SET {sourcepath}`
</td></tr><tr><td>
USESEL</td><td>
/S</td><td>

*(无值)*</td><td>

修改 **PASTE** 和 **PASTESHORTCUT** 函数的行为。通常情况下，文件被粘贴到当前源文件夹。如果你指定 **USESEL** 参数，并且当前在源文件列表中选择了子文件夹，则文件将被粘贴到该子文件夹中。这在用作上下文菜单命令时最有用（这样你就可以右键单击文件夹，然后将剪贴板内容粘贴到其中）。

这也适用于 Opus 可以写入的压缩包 - 例如，如果你将以下命令添加到 *压缩包* [文件类型组](/Manual/file_types/file_type_groups.zh.md) 的上下文菜单，那么你可以右键单击现有的压缩包文件，并将剪贴板内容直接粘贴到其中。

*示例：* `Clipboard PASTE USESEL`
</td></tr></tbody>
</table>