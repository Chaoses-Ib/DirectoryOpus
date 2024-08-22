# Clipboard

**Clipboard** 内部命令可用于：

- 将文件和文件夹从一个文件夹复制粘贴到另一个文件夹
- 将所选文件和文件夹的 **名称** 复制到剪贴板
- 将剪贴板中的图像或文本数据粘贴为磁盘上的文件
- 将剪贴板中的文件、图像或文本数据粘贴到压缩包中（新的或现有的）

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
描述
</th></tr></thead><tbody><tr><td>
ADD</td><td>
/S</td><td>
(无值)</td><td>

将其它文件添加到剪贴板中已有的文件，而不是替换它们。它与 **COPY** 或 **CUT** 结合使用。这样，您就可以将多个项目从不同的源文件夹放到剪贴板中，然后一次性将它们粘贴到目标文件夹中。

*示例:* `Clipboard COPY ADD`
</td></tr><tr><td>
AS</td><td>
/K</td><td>

*\<文件名\>*</td><td>

覆盖将图像或文本粘贴到磁盘时使用的默认文件名。

通常，当您粘贴剪贴板图像数据时，Opus 会创建一个名为 *Clipboard Image.png* 的文件（或其它后缀，具体取决于文件格式），当您粘贴文本数据时，Opus 会创建一个名为 *Clipboard Text.txt* 的文件。使用此参数更改文件名。

如果文件名中未指定扩展名，则会自动添加默认文件扩展名（例如，文本数据的 .txt）。

您可以指定完整路径，使命令始终保存到特定文件夹，而不是当前路径。

此参数也可用于将剪贴板内容粘贴为压缩包（例如，使用 **Clipboard PASTE=zip**）。在这种情况下，压缩包的文件名通常会根据剪贴板内容自动生成 - 此参数允许您覆盖它。

*示例:* `Clipboard PASTE AS PastedData`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

将图像或文本数据粘贴到文件时，此参数会导致 Opus 提示您输入要创建的文件的名称。对于文本，您还可以选择编码类型，对于图像数据，可以选择要使用的图像格式。

![](/Manual/images/media/paste_as.png)

此参数也可用于将剪贴板内容粘贴为压缩包（例如，使用 **Clipboard PASTE=7z**）。在这种情况下，系统将提示您输入新压缩包的名称以及任何特定于压缩包格式的参数。

**缩小图像以补偿系统 DPI** 选项会在您的系统 DPI 高于 100% 时将粘贴的图像缩小。

您还可以指定要在对话框中显示的默认文件名，如以下第二个示例所示。

*示例:* `Clipboard PASTE AS=ask`  
*示例:* `Clipboard PASTE AS=ask:{date|yyyy_MM}_`
</td></tr><tr><td>
COPY</td><td>
/S</td><td>

*(无值)*</td><td>

将所有选定的文件和文件夹复制到剪贴板。

*示例:* `Clipboard COPY`
</td></tr><tr><td>
COPYCOMMANDARGS</td><td>
/K</td><td>

*\<参数\>*</td><td>

与 **Clipboard PASTE** 一起使用时，这使您能够为 **Copy** 命令提供其它参数（如果粘贴命令最终运行的是 **Copy** 命令）。如果粘贴命令不使用 **Copy** 命令（例如，您的剪贴板上有位图数据，并且创建了一个图像文件），则此参数会被忽略。

*示例:* `Clipboard PASTE COPYCOMMANDARGS="FLATVIEWCOPY=autosingle,recreate"`
</td></tr><tr><td>
COPYIMAGE</td><td>
/S</td><td>

*(无值)*</td><td>

将选定的图像文件 **作为图像** 复制到剪贴板，以便粘贴到其它程序中。

*示例:* `Clipboard COPYIMAGE`
</td></tr><tr><td>
COPYINFOTIP</td><td>
/S</td><td>

*(无值)*</td><td>

将当前可见 *信息提示* 的文本内容复制到剪贴板。（信息提示是当您将鼠标悬停在文件或文件夹上时显示信息的“工具提示”。）

如果文件窗口没有可见的信息提示，则不会执行任何操作。此命令只有在分配给热键时才有意义，因为如果您移动鼠标单击工具栏按钮，信息提示将关闭。

*示例:* `Clipboard COPYINFOTIP`

默认情况下，您还可以使用 <kbd>Ctrl+Shift+Alt+C</kbd> 执行相同操作，而无需创建热键，但该命令允许您指定一个更易于输入的替代键。（<kbd>Ctrl+Shift+C</kbd> 也可能有效，但被默认工具栏覆盖，该工具栏将 <kbd>Ctrl+Shift+C</kbd> 分配给 *编辑 > 复制完整路径名*。）
</td></tr><tr><td>
COPYNAMES</td><td>
/O</td><td>

*(无值)*</td><td>

将所有选定文件和文件夹的名称复制到剪贴板（复制的是文件名本身，以文本格式，而不是实际文件）。

默认格式（不指定任何值）会将所有选定项目的完整路径和文件名复制到剪贴板，每个文件占一行。例如，

    C:\Windows\notepad.exe
    C:\Windows\regedit.exe

**COPYNAMES** 参数的各种值允许您修改文件名复制时的格式。某些值可以组合 - 请参阅下面给出的示例，了解您可以执行的操作。另请参阅 **REGEXP** 参数，它允许您使用正则表达式来控制格式。

*示例:* `Clipboard COPYNAMES`
</td></tr><tr><td>
</td><td>
</td><td>

**noexts**</td><td>

从复制到剪贴板的文件名中删除扩展名。例如，

    C:\Windows\notepad
    C:\Windows\regedit

*示例:* `Clipboard COPYNAMES=noexts`
</td></tr><tr><td>
</td><td>
</td><td>

**nopaths**</td><td>

仅将选定项目的名称复制到剪贴板 - 不复制路径。例如，

    notepad.exe
    regedit.exe

*示例:* `Clipboard COPYNAMES=nopaths`  
*示例:* `Clipboard COPYNAMES=nopaths,noexts`
</td></tr><tr><td>
</td><td>
</td><td>

**url**</td><td>

将选定项目的名称以 URL 格式复制到剪贴板。对于 FTP 站点上的文件，这将生成一个 **ftp://** 样式的路径，该路径应该会被其它 FTP 程序接受。对于本地文件，文件名将作为 **file://** 样式的链接复制（例如 //[file:///C:/Windows//](file:///C:/Windows//)）。例如，

    file:///C:/Windows/notepad.exe
    file:///C:/Windows/regedit.exe

*示例:* `Clipboard COPYNAMES=url`
</td></tr><tr><td>
</td><td>
</td><td>

**hash**</td><td>

将每个选定文件的文件名与其 **MD5** 校验和一起复制。例如，

    notepad.exe : f2c7bb8acc97f92e987a2d4087d021b1\\
    regedit.exe : 2e2c937846a0b8789e5e91739284d17a

*示例:* `Clipboard COPYNAMES=hash`
</td></tr><tr><td>
</td><td>
</td><td>

**hash2**</td><td>

以另一种格式复制选定文件的 **MD5** 校验和，与久负盛名的 *MD5Sum* 实用程序兼容。例如，

    f2c7bb8acc97f92e987a2d4087d021b1 *notepad.exe
    2e2c937846a0b8789e5e91739284d17a *regedit.exe

*示例:* `Clipboard COPYNAMES=hash2`
</td></tr><tr><td>
</td><td>
</td><td>

**hash3**</td><td>

复制选定文件的 **MD5** 校验和 **不带** 文件名。您可能只希望一次在单个文件上使用此格式。例如，

    f2c7bb8acc97f92e987a2d4087d021b1
    2e2c937846a0b8789e5e91739284d17a

*示例:* `Clipboard COPYNAMES=hash3`
</td></tr><tr><td>
</td><td>
</td><td>

**hash4**</td><td>

将每个选定文件的文件名与其 **SHA-1** 校验和一起复制。例如，

    notepad.exe : 7eb0139d2175739b3ccb0d1110067820be6abd29
    regedit.exe : f48138dc476e040b8a9925c7d2650b706178e863

*示例:* `Clipboard COPYNAMES=hash4`
</td></tr><tr><td>
</td><td>
</td><td>

**hash5**</td><td>

以另一种格式复制选定文件的 **SHA-1** 校验和。例如，

    7eb0139d2175739b3ccb0d1110067820be6abd29 *notepad.exe
    f48138dc476e040b8a9925c7d2650b706178e863 *regedit.exe

*示例:* `Clipboard COPYNAMES=hash5`
</td></tr><tr><td>
</td><td>
</td><td>

**hash6**</td><td>

复制选定文件的 **SHA-1** 校验和 **不带** 文件名。您可能只希望一次在单个文件上使用此格式。例如，

    7eb0139d2175739b3ccb0d1110067820be6abd29
    f48138dc476e040b8a9925c7d2650b706178e863

*示例:* `Clipboard COPYNAMES=hash6`
</td></tr><tr><td>
</td><td>
</td><td>

**hashcache**</td><td>

将 **hashcache** 关键字添加到其中一个 **hash** 选项中，以使 Opus 使用校验和缓存；如果文件以前已计算过其校验和并且似乎没有更改，则将使用缓存的值。

*示例:* `Clipboard COPYNAMES=hash2,hashcache`
</td></tr><tr><td>
</td><td>
</td><td>

**unc**</td><td>

当指定了 **unc** 值，并且正在复制其名称的文件位于映射的网络驱动器上时，该函数会将它们的映射路径解析为 UNC 路径，并将该路径复制到剪贴板。例如，如果 **Z:** 是一个映射的网络驱动器，**Clipboard COPYNAMES** 将返回：

    Z:\Windows\notepad.exe
    Z:\Windows\regedit.exe

而 **Clipboard COPYNAMES=unc** 可能会返回：

    \\win7vm\c\Windows\notepad.exe
    \\win7vm\c\Windows\regedit.exe

如果当前文件夹不在映射的网络驱动器上，则 unc 参数不会有任何影响。

*示例:* `Clipboard COPYNAMES=unc`
</td></tr><tr><td>
</td><td>
</td><td>

**short**</td><td>

复制选定路径的短（8.3）版本，而不是长版本。例如，

    C:\PROGRA~1\GPSOFT~1\DIRECT~1\dopus.exe
    C:\PROGRA~1\GPSOFT~1\DIRECT~1\dopuslib.dll

*示例:* `Clipboard COPYNAMES=short,nopaths`

并非所有驱动器都启用了短路径。在未启用短路径的驱动器上，将复制正常的长路径。
</td></tr><tr><td>
</td><td>
</td><td>

**single**</td><td>

当选择多个文件时，这会将所有名称复制到单行上（以空格分隔），而不是每个项目一行。如果任何项目名称包含空格，则它们将用引号括起来。例如，

    dopus.exe dopuslib.dll "Opus 13 What's New.pdf"

*示例:* `Clipboard COPYNAMES=nopaths,single`
</td></tr><tr><td>
</td><td>
</td><td>

**paths**</td><td>

仅复制选定项目的路径，不带文件名（与 **nopaths** 相反）。例如，

    C:\Program Files\GPSoftware\Directory Opus

*示例:* `Clipboard COPYNAMES=paths`

为了向后兼容，也识别 **path**，并且执行相同操作。
</td></tr><tr><td>
</td><td>
</td><td>

**capsemantics**</td><td>

使函数的行为类似于 Windows *复制为路径* 上下文菜单命令（每行一个文件路径，并且行始终用引号括起来）。

*示例:* `Clipboard COPYNAMES=capsemantics`
</td></tr><tr><td>
</td><td>
</td><td>

**quote**</td><td>

强制将复制到剪贴板的文件名和路径用双引号括起来，即使它们不包含空格（因此通常不需要引号）。

*示例:* `Clipboard COPYNAMES=quote`
</td></tr><tr><td>
</td><td>
</td><td>

**wsl**</td><td>

以 WSL（适用于 Linux 的 Windows 子系统）格式复制文件路径。例如，**C:\Temp** 将转换为 **/mnt/c/Temp**。

*示例:* `Clipboard COPYNAMES=wsl`
</td></tr><tr><td>
COPYQUEUE</td><td>
/O</td><td>

*(无值)*</td><td>

与 **PASTE** 参数一起使用，以启用 [复制队列](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/README.zh.md) 粘贴文件。不指定任何值，如果需要，会自动将副本排队。这可以覆盖 **[复制文件](/Manual/preferences/preferences_categories/file_operations/copying_files/README.zh.md)** 配置页面上的 **自动管理文件复制队列** 选项。

*示例:* `Clipboard PASTE COPYQUEUE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<队列名称\>*</td><td>

当您指定队列名称作为此参数的值时，它将在粘贴文件时启用手动复制队列。也就是说，如果指定了名称，则文件粘贴将始终排队到指定的队列 - 如果没有为参数指定名称，则粘贴仅在需要时才排队。

*示例:* `Clipboard PASTE COPYQUEUE=MyQueue`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

用于禁用复制队列 - 无论是在配置中启用，还是通过 **shift** 关键字启用。

*示例:* `Clipboard PASTE COPYQUEUE=none`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

允许您为 **COPYQUEUE** 参数指定两个备用参数。如果未按住 **Shift** 键，则使用在 **shift** 关键字之前指定的值 - 如果按住 **Shift** 键，则使用其后的值。例如，您可以配置一个粘贴按钮，以便在按住 <kbd>Shift</kbd> 键时将文件排队到特定队列，而在其它情况下禁用队列。

*示例:* `Clipboard PASTE COPYQUEUE=none,shift,MyQueue`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

指定 **quiet** 关键字以抑制通常指示复制操作已排队的提示。（Opus 13.9.1 及更高版本：您也可以在配置中关闭 *在作业排队时显示确认*。）

*示例:* `Clipboard PASTE COPYQUEUE=MyQueue,quiet`
</td></tr><tr><td>
</td><td>
</td><td>

**noisy**</td><td>

（Opus 13.9.1 及更高版本。）指定 **noisy** 关键字始终显示提示，指示复制操作已排队，即使配置中 *在作业排队时显示确认* 已关闭。

*示例:* `Clipboard PASTE COPYQUEUE=MyQueue,noisy`
</td></tr><tr><td>
CUT</td><td>
/S</td><td>

*(无值)*</td><td>

将所有选定的文件和文件夹剪切到剪贴板（文件不会立即发生任何变化，但当您将它们粘贴到其它地方时，它们会被移动而不是复制）。

*示例:* `Clipboard CUT`
</td></tr><tr><td>
CUTNOCOPYQUEUEWHENSAME</td><td>
/S</td><td>

*(无值)*</td><td>

与 **Clipboard PASTE** 一起使用，此功能在剪贴板上的文件被剪切（即移动）以及源和目标位于同一个驱动器分区上时，会禁用使用复制队列。

*示例:* `Clipboard PASTE CUTNOCOPYQUEUEWHENSAME`
</td></tr><tr><td>
EXPANDNEWLINES</td><td>
/S</td><td>

*(无值)*</td><td>

与 **Clipboard SET** 一起使用，允许您使用 **\n** 将新行插入字符串中，以便您可以设置包含多行的剪贴板字符串。您也可以使用 **\\** 插入一个字面上的反斜杠。

*示例:* `Clipboard EXPANDNEWLINES SET Hello\nWorld`

使用 **EXPANDNEWLINES** 在剪贴板字符串中插入路径时，应使用 **[escbackslash](../external_control_codes/codes_for_passing_paths.zh.md)** 来防止路径中的反斜杠被误解。

*示例（全部在一行上）：*  
**Clipboard EXPANDNEWLINES SET {sourcepath\|escbackslash}\n{destpath\|escbackslash}**
</td></tr><tr><td>
FILE</td><td>
/K/M</td><td>

*\<文件名\>, ...*</td><td>

指定要操作的文件。如果未指定，则该命令将对所有当前选定的文件进行操作。

*示例:* `Clipboard COPY FILE "C:\moo.zip" "C:\cow.zip"`
</td></tr><tr><td>
NEWLINEIFADDING</td><td>
/S</td><td>

*(无值)*</td><td>

与 **Clipboard ADD SET** 一起使用，在现有的剪贴板数据和要添加的字符串之间添加一个新行。如果剪贴板当前为空或包含非文本数据，则不会添加新行。

*示例:* `Clipboard ADD NEWLINEIFADDING SET This is a new line.`
</td></tr><tr><td>
NOFROMFOCUS</td><td>
/S</td><td>

*(无值)*</td><td>

**Clipboard** 命令的默认行为是根据源文件列表或文件夹树哪个具有输入焦点来对它们进行操作。这使您可以在树中使用相同的命令复制文件夹，以及在文件列表中复制文件。指定此参数以强制命令始终对源文件列表进行操作并忽略文件夹树。

*示例:* `Clipboard COPY NOFROMFOCUS`
</td></tr><tr><td>
PASTE</td><td>
/O</td><td>

*(无值)*</td><td>

将先前复制到剪贴板的任何文件和文件夹粘贴到当前文件窗口中。

如果文件是通过“剪切”操作放置在剪贴板上的，则它们将被移动，否则它们将被复制到新位置。

也可以将剪贴板中的图像和文本数据粘贴到当前文件夹中的新文件中。粘贴图像和文本数据时，**AS** 参数可以更改创建的文件的名称和路径。

*示例:* `Clipboard PASTE`
</td></tr><tr><td>
</td><td>
</td><td>

**enc:***\<编码\>*</td><td>

在将文本从剪贴板粘贴到文件时，指定编码类型。默认行为是如果剪贴板文本是 Unicode，则粘贴为 UTF-16，否则粘贴为 ANSI。

支持的编码类型为 **oem**、**ansi**、**utf8**、**utf8nobom**、**utf16**、**utf16nobom**。

*示例:* `Clipboard PASTE=enc:utf8`
</td></tr><tr><td>
</td><td>
</td><td>

**jpg**</td><td>

强制将剪贴板上的图像数据以 JPEG 格式粘贴（覆盖配置的默认设置）。您还可以选择指定 JPEG 图像质量，其值为 1 到 100。

*示例:* `Clipboard PASTE=jpg:85`
</td></tr><tr><td>
</td><td>
</td><td>

**png**</td><td>

以 PNG 格式粘贴图像数据。您还可以选择指定 PNG 压缩级别，其值为 1 到 6。

*示例:* `Clipboard PASTE=png:4`
</td></tr><tr><td>
</td><td>
</td><td>

**gif**</td><td>

以 GIF 格式粘贴图像数据。

*示例:* `Clipboard PASTE=gif`
</td></tr><tr><td>
</td><td>
</td><td>

**bmp**</td><td>

以 BMP 格式粘贴图像数据。

*示例:* `Clipboard PASTE=bmp`
</td></tr><tr><td>
</td><td>
</td><td>

**zip**</td><td>

将剪贴板内容（文件、图像或文本数据）粘贴为新的 ZIP 压缩包。压缩包的文件名将根据剪贴板内容自动生成 - 您可以使用 **AS** 参数覆盖此文件名。
</td></tr><tr><td>
</td><td>
</td><td>

**7z**</td><td>
将剪贴板内容粘贴为新的 7Zip 压缩包。
</td></tr><tr><td>
</td><td>
</td><td>

*\<压缩包后缀\>*</td><td>
将剪贴板内容粘贴为指定类型的新压缩包（您可以指定 Opus 支持创建的任何压缩包后缀）。
</td></tr><tr><td>
PASTELINK</td><td>
/O</td><td>

*(无值)*</td><td>

将先前复制到剪贴板的任何文件和文件夹的快捷方式粘贴到当前文件窗口中。例如，如果您对 *C:\Windows* 文件夹使用 **Clipboard COPY** 命令，导航到另一个文件夹，并运行 **Clipboard PASTELINK** 命令，它将粘贴一个名为 *Windows - Shortcut.lnk* 的快捷方式。

*示例:* `Clipboard PASTELINK`
</td></tr><tr><td>
</td><td>
</td><td>

**junction**</td><td>

创建指向剪贴板中任何文件夹的联结。联结仅在 NTFS 卷上受支持，并且您不能创建指向文件（仅文件夹）的联结。

*示例:* `Clipboard PASTELINK=junction`
</td></tr><tr><td>
</td><td>
</td><td>

**hardlink**</td><td>

创建指向剪贴板中任何文件的硬链接。硬链接仅在 NTFS 卷上受支持，并且您不能创建指向文件夹（仅指向文件）的硬链接。

*示例:* `Clipboard PASTELINK=hardlink`
</td></tr><tr><td>
</td><td>
</td><td>

**softlink**</td><td>

创建指向剪贴板中任何文件或文件夹的软链接。请注意，链接目标被存储为绝对路径。软链接支持文件和文件夹，但仅在 Vista 及更高版本上受支持（同样，仅在 NTFS 卷上）。创建软链接需要管理员访问权限，因此如果需要，Opus 会在您运行此命令时显示 UAC 提示。

*示例:* `Clipboard PASTELINK=softlink`
</td></tr><tr><td>
</td><td>
</td><td>

**relsoftlink**</td><td>

创建指向剪贴板中任何文件或文件夹的软链接，如果可能，则存储相对目标路径。如果目标不能相对于链接来表达，则将创建常规的绝对链接。

*示例:* `Clipboard PASTELINK=relsoftlink`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

自动确定要创建的最合适的链接类型。在 Vista 及更高版本上，这将是一个软链接 - 在 Windows XP 上，将是联结或硬链接，具体取决于项目类型。如果剪贴板上存在非文件系统对象（例如，您试图创建指向 *控制面板* 等虚拟文件夹的链接）或目标驱动器未格式化为 NTFS，则它将创建一个快捷方式。

*示例:* `Clipboard PASTELINK=auto`
</td></tr><tr><td>
</td><td>
</td><td>

**autonosoft**</td><td>

与 **auto** 相同，但它不会尝试创建软链接。换句话说：它将根据项目的类型创建联结或硬链接。如果剪贴板上存在非文件系统对象（例如，您试图创建指向 *控制面板* 等虚拟文件夹的链接）或目标驱动器未格式化为 NTFS，则它将创建一个快捷方式。

*示例:* `Clipboard PASTELINK=autonosoft`
</td></tr><tr><td>
PREFERIMAGE</td><td>
/S</td><td>

*(无值)*</td><td>

将剪贴板中的数据粘贴到新文件时，图像数据通常优先于文本数据。Opus 在某些情况下会对此规则做出例外。

例如，如果您使用 Microsoft Excel 将一些单元格复制到剪贴板，Excel 会将单元格中的文本和它们的屏幕截图都放到剪贴板中。将数据从 Excel 粘贴时，人们通常想要文本，而不是屏幕截图。因此，当 Opus 检测到粘贴的数据来自 Excel 时，它会优先考虑文本而不是图像，这与它对来自其它程序的数据的行为相反。

如果指定了 **PREFERIMAGE** 参数，则无论数据来自何处，图像数据都将 *始终* 优先于文本数据。这使您能够粘贴来自 Excel 的图像数据，如果这是您想要的。（如果剪贴板上只有文本数据，您仍然会得到一个文本文件。）

*示例:* `Clipboard PASTE PREFERIMAGE`
</td></tr><tr><td>
PREFERTEXT</td><td>
/S</td><td>

*(无值)*</td><td>

将剪贴板中的数据粘贴到新文件时，图像数据通常优先于文本数据。（对此规则有例外；请参阅上面的 **PREFERIMAGE** 参数。）

通常，如果另一个程序将文本和图像数据都放到剪贴板中，然后您在 Opus 中粘贴以将数据保存到新文件中，文本数据将被忽略，您将获得一个图像文件（BMP、JPG、GIF 或 PNG）。

例如，一个绘图程序可能会将照片和照片的描述都放到剪贴板中，而粘贴到 Opus 中通常会创建一个包含照片的图像文件，而不是包含描述的文本文件。

**PREFERTEXT** 参数优先考虑文本而不是图像，因此在这种情况下您会得到一个文本文件。（如果剪贴板上只有图像数据，您仍然会得到一个图像文件。）

*示例:* `Clipboard PASTE PREFERTEXT`
</td></tr><tr><td>
REGEXP</td><td>
/K/M</td><td>

*\<搜索\> \<替换\> ...*</td><td>

与 **COPYNAMES** 一起使用，允许您对文件名进行 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md) 操作，这些文件名被放入剪贴板 - 这实际上允许您确定自己的剪贴板格式。

为此参数指定的值是一个或多个字符串对 - 每个对中的第一个是要搜索的模式，第二个是替换字符串。例如，要剥离所有文件名复制到剪贴板时的后缀，搜索字符串将是 **(.\*)\\(.\*)**，替换字符串将是 **\1**。

*示例:* `Clipboard COPYNAMES=nopaths REGEXP "(.*)\\(.*)" "\1"`
</td></tr><tr><td>
SCREENSHOT</td><td>
/O</td><td>

*(无值)*</td><td>

拍摄活动文件窗口的屏幕截图并将其复制到剪贴板。等效于按下 <kbd>Alt+PrtScr</kbd>。

*示例:* `Clipboard SCREENSHOT`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

拍摄桌面的屏幕截图并将其复制到剪贴板。等效于按下 <kbd>PrtScr</kbd>。

*示例:* `Clipboard SCREENSHOT=all`
</td></tr><tr><td>
</td><td>
</td><td>

**format**</td><td>

当指定了 **save** 参数时，此参数允许您指定要保存屏幕截图的文件格式。支持的格式为 **jpg**、**png**、**gif** 和 **bmp**。

*示例:* `Clipboard SCREENSHOT=save,format:jpg`
</td></tr><tr><td>
</td><td>
</td><td>

**name**</td><td>

当指定了 **save** 参数时，此参数允许您配置要保存屏幕截图的名称。如果未指定，则使用默认名称。您可以使用 **%date%** 代码在名称中插入当前日期。请记住，如果您的目标名称包含空格，则将 SCREENSHOT 参数的值用引号括起来。

*示例:* `Clipboard SCREENSHOT=save,name:My_Opus_%date\\`  
*示例:* `Clipboard SCREENSHOT "save,name:Opus Screenshot"`
</td></tr><tr><td>
</td><td>
</td><td>

**quality**</td><td>

当指定了 save 参数并且屏幕截图被保存为 jpeg 图像时，此参数允许您指定压缩图像的质量（值为 1 到 100）。

*示例:* `Clipboard SCREENSHOT=save,format:jpg,quality:85`

如果屏幕截图被保存为 PNG 图像，则可以使用此参数来控制压缩级别（值为 1 到 6）。

*示例:* `Clipboard SCREENSHOT=save,format:png,quality:4`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

在拍摄屏幕截图后不会显示确认消息。

*示例:* `Clipboard SCREENSHOT=all,quiet`
</td></tr><tr><td>
</td><td>
</td><td>

**save**</td><td>

屏幕截图将自动保存到桌面（以及复制到剪贴板）。使用 **format** 和 **quality** 参数来控制文件类型。您可以使用 **name** 参数配置名称。

*示例:* `Clipboard SCREENSHOT=save`
</td></tr><tr><td>
</td><td>
</td><td>

**secure**</td><td>

在拍摄屏幕截图时，文件窗口中的文件名将被模糊，以遮盖可能敏感的信息。

*示例:* `Clipboard SCREENSHOT=all,secure`
</td></tr><tr><td>
</td><td>
</td><td>

**time**</td><td>

在拍摄屏幕截图之前显示一个倒计时计时器。

*示例:* `Clipboard SCREENSHOT=secure,time:10`
</td></tr><tr><td>
SET</td><td>
/K/R</td><td>
用户定义</td><td>

将提供的文本复制到剪贴板。

*示例:* `Clipboard SET {sourcepath}`
</td></tr><tr><td>
USESEL</td><td>
/S</td><td>

*(无值)*</td><td>

修改 **PASTE** 和 **PASTESHORTCUT** 函数的行为。通常，文件会粘贴到当前源文件夹中。如果您指定了 **USESEL** 参数，并且当前在源文件列表中选择了子文件夹，则文件将粘贴到该子文件夹中。这在用作上下文菜单命令时最有用（这样您就可以右键单击文件夹并将剪贴板内容粘贴到其中）。

这也适用于 Opus 可以写入的压缩包 - 例如，如果您将以下命令添加到 *Archives* [文件类型组](/Manual/file_types/file_type_groups.zh.md) 的上下文菜单中，那么您就可以右键单击现有的压缩包文件并将剪贴板内容直接粘贴到其中。

*示例:* `Clipboard PASTE USESEL`
</td></tr></tbody>
</table>