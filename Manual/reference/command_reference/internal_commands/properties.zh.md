# Properties

**属性**内部命令可用于：

- 显示文件和文件夹的系统*属性*对话框
- 显示当前文件夹的**[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)**对话框
- 显示当前连接的 FTP 站点的 FTP [站点属性](/Manual/ftp/site_properties.zh.md) 对话框
- 显示您[常用文件夹格式](/Manual/basic_concepts/folder_options/folder_formats.zh.md) 的下拉菜单
- 为所选文件和文件夹分配[标签](/Manual/file_operations/labels.zh.md)
- 设置选定的图像文件为系统壁纸图像

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

显示所选文件和文件夹的系统*属性*对话框。

*示例:* `Properties`
</td></tr><tr><td>
ADDLABEL</td><td>
/O</td><td>

*(无值)*</td><td>

结合使用 **SETLABEL** 参数时，它允许您添加一个或多个标签，而不清除现有标签。

*示例:* `Properties SETLABEL=Green ADDLABEL`

可与 **SETLABELTOGGLE** 结合使用以切换单个标签。

*示例:* `Properties SETLABEL=Bold ADDLABEL SETLABELTOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**shift  
ctrl  
alt**</td><td>

如果指定了关键字，标签仅在函数运行时按住指定键才会添加 - 否则将忽略 **ADDLABEL** 参数，它们将像往常一样替换现有标签。

*示例:* `Properties SETLABEL red ADDLABEL=ctrl`
</td></tr><tr><td>
FILE</td><td>
</td><td>

*\<filename\>*</td><td>

指定文件名而不是使用所选文件。路径的最后成分支持通配符。这是 **Properties** 命令的默认参数，因此您不需要指定 **FILE** 关键字。如果文件名包含空格，请确保用引号引起来。

*示例:* `Properties "C:\Windows\System32\notepad.exe"`
</td></tr><tr><td>
FOLDERFORMAT</td><td>
/S</td><td>

*(无值)*</td><td>

显示当前文件夹的**文件夹格式**对话框。

*示例:* `Properties FOLDERFORMAT`
</td></tr><tr><td>
FTPSITE</td><td>
/S</td><td>

*(无值)*</td><td>

显示当前连接的 FTP 站点的 FTP [站点属性](/Manual/ftp/site_properties.zh.md) 对话框。如果您当前未查看 FTP 目录，则此命令不起作用。

*示例:* `Properties FTPSITE`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

当与生成项目列表的命令一起使用时（请参阅[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数在列表的开头添加一个小标题。当列表为空时，标题将被隐藏。标题仅适用于可能在与按钮本身同一级别的命令生成多个项目的情况。

当 **HEADING** 单独使用时，而不指定文本值时，主按钮的标签文本将用作标题。

*示例:* `Properties SETLABEL HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

如果希望标题文本与按钮标签不同，则可以指定标题文本。

*示例:* `Properties SETLABEL HEADING="Labels"`
</td></tr><tr><td>
LABELCATEGORY</td><td>
/K</td><td>

*\<category\>*</td><td>

当用于生成标签列表的命令（例如 `Properties SETLABEL` 或 `Properties SETLABEL !menu`）时，此参数允许您按类别过滤生成列表。它接受一个或多个逗号分隔的通配符字符串，这些字符串允许您匹配要包含的类别的名称。

使用 `Properties SETLABEL !reset` 命令重置标签时，还将使用指定的类别 - 如果同时使用了 **LABELCATEGORY**，则只会清除指定类别中的标签。它在默认的 **Properties** 下拉菜单中使用，提供了清除状态图标而不影响其他标签的命令。

您可以使用模式 **~**\* （意思是“任何东西都不是”）来匹配未分类的标签。

对两个预定义的类别（*状态*和*颜色*）有特殊处理；可以通过使用带有 **raw:** 前缀的英文名称引用它们，并且可以在任何语言中使用。

*示例:* `Properties SETLABEL !menu LABELCATEGORY raw:~(Status)`
</td></tr><tr><td>
LISTER</td><td>
/S</td><td>

*(无值)*</td><td>

显示源文件列表中当前显示的文件夹的系统*属性*对话框。

*示例:* `Properties LISTER`
</td></tr><tr><td>
NOFROMFOCUS</td><td>
/S</td><td>

*(无值)*</td><td>

**Properties** 命令的默认行为是对源文件列表或文件夹树进行操作，具体取决于哪个具有输入焦点。这使您可以使用相同的命令访问树中的文件夹以及文件列表中的文件和文件夹的*属性*对话框。指定此参数以强制命令始终在源文件列表器上运行并忽略文件夹树。

*示例:* `Properties NOFROMFOCUS`
</td></tr><tr><td>
POSITION</td><td>
/K</td><td>

*\<x,y\>*</td><td>

以屏幕坐标为单位指定属性对话框的位置。如果未指定位置，对话框将在默认位置打开。

*示例:* `Properties POSITION=0,0`
</td></tr><tr><td>
</td><td>
</td><td>

**rel**</td><td>

表示坐标相对于启动属性函数的文件窗口。

*示例:* `Properties POSITION=32,32,rel`
</td></tr><tr><td>
</td><td>
</td><td>

**center**</td><td>

在启动属性对话框的文件窗口上方居中放置属性对话框。

*示例:* `Properties POSITION=center`
</td></tr><tr><td>
SETLABEL</td><td>
/O</td><td>

*(无值)*</td><td>

显示已配置的 [标签](/Manual/file_operations/labels.zh.md) 的已生成列表（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。从此列表中选择标签会将其应用到所有选定的文件和文件夹。

此命令支持 [嵌入函数](/Manual/customize/creating_your_own_buttons/embedded_functions.zh.md)用于生成动态按钮。

*示例:* `Properties SETLABEL`
</td></tr><tr><td>
</td><td>
</td><td>

*\<label\>\[,\<label\>,...\]*</td><td>

将指定的标签或标签应用到所有选定的文件和文件夹。多个标签名称必须用逗号分隔。标签名称中的逗号和反斜杠必须用反斜杠转义。

您可以将此与 **ADDLABEL** 参数结合使用，将标签添加到现有标签，而不是替换它们。您可以进一步将其与 **SETLABELTOGGLE** 结合使用以打开和关闭标签。

关键字 **stoponmatch** 可用于将“停止匹配”标志添加到文件，这会阻止任何通配符或标签过滤器应用于该文件。

*示例:* `Properties SETLABEL=Green,Blue`
</td></tr><tr><td>
</td><td>
</td><td>

**!menu**</td><td>

将生成的标签列表放在菜单中。

*示例:* `Properties SETLABEL !menu`
</td></tr><tr><td>
**!submenu**</td><td>

为每个标签类别生成子菜单。

*示例:* `Properties SETLABEL !submenu`
</td></tr><tr><td>
</td><td>
</td><td>

**!submenu2**</td><td>

为每个标签类别生成子菜单，并将没有类别的标签放在*未分类*组中。

*示例:* `Properties SETLABEL !menu,!submenu2`
</td></tr><tr><td>
</td><td>
</td><td>

**!nogroup**</td><td>

标签默认按类别分组；指定 **!nogroup** 以忽略类别并生成一个标签平面列表，仅按名称排序，其中不同类别的标签会混合。

*示例:* `Properties SETLABEL !menu,!nogroup`
</td></tr><tr><td>
</td><td>
</td><td>

**!noreset**</td><td>

在自动生成的标签列表后，通常会添加一个*重置*选项。您可以通过指定 **!noreset** 来阻止这样做。

*示例:* `Properties SETLABEL !noreset`
</td></tr><tr><td>
</td><td>
</td><td>

**!nostoponmatch**</td><td>

在自动生成的标签列表后，如果在[标签/选项](/Manual/preferences/preferences_categories/labels/options.zh.md)配置页面上选择了 **将通配符和过滤器标签应用于明确标记的文件**，则通常会添加一个*停止匹配*选项。您可以通过指定 **!nostoponmatch** 来阻止其添加。

*示例:* `Properties ADDLABEL SETLABELTOGGLE SETLABEL !nostoponmatch,!noreset LABELCATEGORY raw:Status`

上面的示例会直接在工具栏上提供顶级按钮，以切换每个状态标签，而无需额外的按钮弄乱工具栏。
</td></tr><tr><td>
</td><td>
</td><td>

**!compact**</td><td>

使得自动生成的标签列表窄而紧凑，其中每个标签的按钮仅包含一个图标或“Aa”标签以显示其效果。不显示完整标签名称，但可以通过悬停在每个按钮上来显示。适用于在顶级工具栏上列出标签时不想占用太多空间的情况。

*示例:* `Properties SETLABEL=!compact`
</td></tr><tr><td>
</td><td>
</td><td>

**!reset**</td><td>

从所有选定项中移除标签。您可以将此与 **LABELCATEGORY** 参数结合使用，以仅移除特定类别的标签。

*示例:* `Properties SETLABEL=!reset`

请注意，**!reset** 不会影响自动生成的标签列表；除非指定了 **!noreset**，否则会在这些列表中添加一个*重置*选项。而 **!reset** 会创建一个按钮，用于移除选定文件上的所有标签。
</td></tr><tr><td>
SETLABELINFS</td><td>
/K</td><td>

**yes**</td><td>

结合 **SETLABEL** 参数指定以覆盖 [标签/选项](/Manual/preferences/preferences_categories/labels/options.zh.md)配置页面上的 **在文件系统中启用标签存储** 选项的状态。即使该选项处于禁用状态，标签也会存储在文件系统中。

*示例:* `Properties SETLABEL=Green SETLABELINFS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

标签将存储在 Opus 配置中。

*示例:* `Properties SETLABEL=Blue SETLABELINFS=no`
</td></tr><tr><td>
SETLABELREMOVE</td><td>
/O</td><td>

*(无值)*</td><td>

结合 **SETLABEL** 参数指定以移除标签。如果目标文件或文件夹已具有指定的标签，则将移除该标签。否则不会发生任何事情。

（仅影响明确应用于各个文件夹和文件的标签。通过通配符和过滤器获取的标签可以被更明确的标签覆盖，但无法在各个项上切换。）

*示例:* `Properties SETLABEL=Bold SETLABELREMOVE`
</td></tr><tr><td>
</td><td>
</td><td>

**shift  
ctrl  
alt**</td><td>

如果指定，**SETLABELREMOVE** 参数仅在函数运行时按住指定键时才会应用。

*示例:* `Properties SETLABEL=Bold SETLABELREMOVE=alt`
</td></tr><tr><td>
SETLABELTOGGLE</td><td>
/O</td><td>

*(无值)*</td><td>

结合 **SETLABEL** 参数指定以切换标签。如果目标文件或文件夹已具有指定的标签，则将清除整个标签。

（仅影响明确应用于各个文件夹和文件的标签。通过通配符和过滤器获取的标签可以被更明确的标签覆盖，但无法在各个项上切换。）

*示例:* `Properties SETLABEL=Bold SETLABELTOGGLE`

与 **ADDLABEL** 结合使用以仅切换一个标签，同时保留文件的任何其他标签。

*示例:* `Properties SETLABEL=Red SETLABELTOGGLE ADDLABEL`
</td></tr><tr><td>
</td><td>
</td><td>

**shift  
ctrl  
alt**</td><td>

如果指定，**SETLABELTOGGLE** 参数仅在函数运行时按住指定键时才会应用。如果没有按住该键，则标签仅会开启 - 它不会再次关闭。

*示例:* `Properties SETLABEL=Bold SETLABELTOGGLE=shift`
</td></tr><tr><td>
SETWALLPAPER</td><td>
/O</td><td>

*(无值)*</td><td>

将选定的图像文件设置为系统壁纸。Opus 将复制选定的图像文件（并在必要时转换其格式）- 您可以使用配置中 **[其他/高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面上的 **setwallpaper_file** 选项来更改该副本的存储位置。

*示例:* `Properties SETWALLPAPER`
</td></tr><tr><td>
</td><td>
</td><td>

**center**</td><td>

壁纸模式将设置为在屏幕上居中图像。

*示例:* `Properties SETWALLPAPER=center`
</td></tr><tr><td>
</td><td>
</td><td>

**tile**</td><td>

图像将在屏幕上平铺。

*示例:* `Properties SETWALLPAPER=tile`
</td></tr><tr><td>
</td><td>
</td><td>

**stretch**</td><td>

图像将被拉伸（或缩小）以完全填充屏幕。

*示例:* `Properties SETWALLPAPER stretch`
</td></tr><tr><td>
</td><td>
</td><td>

**fit**</td><td>

必要时，图像将被裁剪以填充屏幕。图像的宽高比将得到保留。这仅在 Windows 7 及更高版本上可用。

*示例:* `Properties SETWALLPAPER=fit`
</td></tr><tr><td>
</td><td>
</td><td>

**fill**</td><td>

图像将被拉伸或缩小以填充屏幕，但宽高比将得到保留 - 所以图像的侧面或顶部和底部可能会显示黑条。这仅在 Windows 7 及更高版本上可用。

*示例:* `Properties SETWALLPAPER fill`
</td></tr><tr><td>
</td><td>
</td><td>

**span**</td><td>

图像将在多个显示器的桌面上跨越。这仅在 Windows 8 及更高版本上可用。

*示例:* `Properties SETWALLPAPER span`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

显示各种壁纸模式的下拉菜单（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。从该菜单中选择模式将使用该模式将选定的图像文件设置为壁纸。当将其添加到 **图像** [文件类型组](/Manual/file_types/file_type_groups.zh.md) 的上下文菜单中时，这非常有用。

*示例:* `Properties SETWALLPAPER=menu`
</tr><tr><td>
SINGLE</td><td>
/S</td><td>

*(无值)*</td><td>

当选择了多个文件或文件夹时，修改 **属性** 命令的行为。默认情况下，将为所有选中的项显示一个合并的*属性*对话框，但如果指定了 **SINGLE**，则会为每个项显示一个单独的*属性*对话框。

*示例:* `Properties SINGLE`
</td></tr></tbody>
</table>