# Show

**查看**内部命令可用于：

- 在 [独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中显示所选图像文件
- 显示当前文件夹内容的幻灯片
- 查看和操作已安装的查看器插件（可以扩展 Opus 图像处理能力的第三方库）
- 动态调整当前文件列表中显示的缩略图大小
- 执行独立图像查看器的内部命令（允许你配置查看器工具栏和热键）

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

打开 [独立图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 以显示所选文件。

*示例：* `查看`
</td></tr><tr><td>
自动文件列表</td><td>
/S</td><td>

*(无值)*</td><td>

用于在查看器的“上一个/下一个”列表中自动填充从启动命令的文件夹标签页中可见的其它文件。

单独使用 **自动文件列表**，而不使用 **列出同级**，可以创建具有类似于通过双击文件启动查看器的行为的命令。具体来说，它使该命令遵守配置中 **[独立查看器](/Manual/preferences/preferences_categories/viewer/standalone_viewer/README.zh.md)** 页面上的 **生成上一个/下一个列表（双击后打开时）** 选项，即使不是由双击触发时。如果关闭此选项，则单独使用 **自动文件列表** 可能没有任何效果。

如果你将 **自动文件列表** 和 **列出同级** 结合使用，则该命令将始终填充“上一个/下一个”列表，即使关闭配置选项，除非选择了多个文件。（如果选择两个或更多文件，然后对它们运行该命令，那么只有这些文件会出现在“上一个/下一个”列表中。）

由 **自动文件列表** 生成的“上一个/下一个”列表（当配置选项打开或与 **列出同级** 结合使用时）通常与由 **列出同级** 单独生成的文件相同。当文件夹标签页中显示的内容与磁盘上的真实文件夹不对应时，两者会有所不同。如果应用了文件夹标签页的过滤器，或显示了类似于查找结果或扁平视图这样的内容，那么 **自动文件列表** 会为你提供一个与该过滤或多目录视图相对应列表；另一方面，**列出同级**（单独使用）会让你获得与你开始的文件位于同一个目录中的文件列表，这些文件可能是根本没有在文件夹标签页中显示的文件。

*示例：* `查看 自动文件列表 列出同级`
</td></tr><tr><td>
文件</td><td>
</td><td>

*\<文件\>*</td><td>

指定要显示的文件或文件夹。如果指定文件夹，则它下面的所有文件将排队到查看器的“上一个/下一个”列表中。如果你没有在命令行中提供文件或文件夹，则将使用从启动命令的文件夹标签页中选择的所有文件（如果适用）。记得如果路径中包含空格，用引号将它们括起来。

由于 **文件** 是默认参数，因此你无需显式使用其名称。以下两个示例执行相同操作：

*示例：* `查看 "C:\图片\父母.jpg"`  
*示例：* `查看 文件="C:\图片\父母.jpg"`

**文件** 参数还可与 **查看窗格命令=打开** 一起用于在列表框的查看器窗格中打开特定文件。

*示例：* `查看 "C:\猫\最好猫.jpg" 查看窗格命令=打开`
</td></tr><tr><td>
全屏</td><td>
/S</td><td>

*(无值)*</td><td>

在全屏模式下打开图像查看器。

*示例：* `查看 全屏`
</td></tr><tr><td>
标题</td><td>
/O</td><td>

*(无值)*</td><td>

当与生成项目列表的命令一起使用时（请参阅 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**标题** 参数在列表的开头添加一个小标题。列表为空时，标题将被隐藏。标题仅适用于在按钮本身的同一级别上可能生成多个项目的命令。

当 **标题** 单独使用时，不指定文本值，则使用主按钮的标签文本作为标题。

*示例：* `查看 缩略图大小=列表 标题`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题文本\>*</td><td>

如果你希望标题文本与按钮的标签不同，可以指定它。

*示例：* `查看 缩略图大小=列表 标题="缩略图大小"`
</td></tr><tr><td>
列表框链接</td><td>
/O</td><td>

*(无值)*</td><td>

打开的查看器将链接到运行该命令的列表框。查看器会跟踪列表框的文件选择，类似于分离的预览窗格。当在列表框中单击文件时，它将被加载到查看器中。

*示例：* `查看 列表框链接`

如果配置或其它参数指定重新使用现有查看器，则仅当它也使用 **列表框链接** 参数打开并来自同一列表框时，才会重新使用一个查看器。类似地，不带 **列表框链接** 打开查看器的请求不会重新使用已打开的查看器。

此参数用于在打开新查看器时在列表框工具栏（等）上使用。如果你希望链接或取消链接已经打开的查看器，请参阅下面的 **查看器命令=列表框链接**。
</td></tr><tr><td>
</td><td>
</td><td>

**关闭**</td><td>

关闭当前链接到运行该命令的列表框的所有独立查看器。

*示例：* `查看 列表框链接=关闭`
</td></tr><tr><td>
</td><td>
</td><td>

**切换**</td><td>

如果列表框还没有，则打开一个新的链接查看器；否则，关闭列表框的所有链接查看器。

*示例：* `查看 列表框链接=切换`
</td></tr><tr><td>
列出同级</td><td>
/S</td><td>

*(无值)*</td><td>

当 **列出同级** 单独使用，而不使用 **自动文件列表** 时，它会自动使用与指定的文件（或单个选定文件）相同的目录中的其它文件的查看器填充“上一个/下一个”列表。

如果既没有指定 **列出同级** 也没有指定 **自动文件列表**，或者该命令针对多个选定文件运行，则只有指定或选定的文件才会包含在查看器的“上一个/下一个”列表中。

请参阅 **自动文件列表** 的说明，了解在指定两者时会发生什么，以及两者之间的差异。

*示例：* `查看 全屏 列出同级`
</td></tr><tr><td>
加载所有缩略图</td><td>
/S</td><td>

*(无值)*</td><td>

触发为源文件夹中的所有文件（包括当前不可见的文件）生成缩略图图像。

*示例：* `查看 加载所有缩略图`
</td></tr><tr><td>
插件</td><td>
/K</td><td>

*\<插件名称\>*</td><td>

强制使用指定的插件来显示文件。如果没有此插件，Opus 会自动确定要使用的最佳插件（或者，对于可以内部处理的格式，不会使用插件）。

*\<插件名称\>* 可以是插件 DLL 的名称（包括 **.dll** 扩展名）或插件的“漂亮名称”。请注意，此命令不能强制插件查看它无法处理的文件。
</td></tr>
此论证还与 **PLUGINDISABLE** 结合使用，以启用或禁用指定的插件。

*示例：* `Show PLUGIN "Animated GIF"`
</td></tr><tr><td>
PLUGINABOUT</td><td>
/K</td><td>

*\<插件名称\>*</td><td>

显示指定插件的 **关于** 对话框。 *\<插件名称\>* 可以是插件 DLL（包括 **.dll** 扩展名）的名称或插件的“可读名称”。

*示例：* `Show PLUGINABOUT text.dll`
</td></tr><tr><td>
PLUGINCONFIG</td><td>
/K</td><td>

*\<插件名称\>*</td><td>

显示指定插件的配置对话框（如果存在）。

*示例：* `Show PLUGINCONFIG dcrawrap.dll`
</td></tr><tr><td>
PLUGINDISABLE</td><td>
/O</td><td>

*(无值)*</td><td>

在指定插件的启用状态之间切换。如果插件当前已启用，则会禁用，反之亦然。必须使用 **PLUGIN** 论证指定插件。

*示例：* `Show PLUGINDISABLE PLUGIN gifanim.dll`
</td></tr><tr><td>
</td><td>
</td><td>

**enable**</td><td>

启用使用 **PLUGIN** 论证指定的插件。

*示例：* `Show PLUGINDISABLE=enable PLUGIN text.dll`
</td></tr><tr><td>
</td><td>
</td><td>

**disable**</td><td>

禁用使用 **PLUGIN** 论证指定的插件。

*示例：* `Show PLUGIN audiotags.dll PLUGINDISABLE disable`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

不需要指定“toggle”，因为如果未指定“enable”或“disable”，它就是默认值，但是如果你想更明确，可以指定。

*示例：* `Show PLUGIN="audiotags.dll" PLUGINDISABLE=toggle`

请注意，当 **PLUGINDISABLE** 按钮为切换按钮时，当插件*禁用*时，按钮将显示为活动状态（例如，选中或突出显示）。与大多数命令一样，你可以在命令序列的顶部新行上添加 **@toggle:invert** 来反转此命令。

//<示例://>

    @toggle:invert
    Show PLUGIN="wma.dll" PLUGINDISABLE=toggle
</td></tr><tr><td>
PLUGINLIST</td><td>
/S</td><td>

*(无值)*</td><td>

显示已安装查看器插件的动态列表（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。生成的列表为每个查看器插件包含一个子菜单，其中包含可用于启用/禁用、配置以及显示有关插件的信息的命令。

*示例：* `Show PLUGINLIST`
</td></tr><tr><td>
PLUGINMANAGER</td><td>
/S</td><td>

*(无值)*</td><td>

在配置中显示 **[查看器/查看器插件](/Manual/preferences/preferences_categories/viewer/viewer_plugins.zh.md)** 页面，其中你可以查看并管理已安装的查看器插件。

*示例：* `Show PLUGINMANAGER`
</td></tr><tr><td>
POS</td><td>
/K</td><td>

*\<x\>,\<y\>*</td><td>

替代独立查看器的默认定位，并在指定坐标处打开其窗口。例如，可以始终在特定显示器上显示查看器。

*示例：* `Show POS 1920,0`
</td></tr><tr><td>
SIZE</td><td>
/K</td><td>

*\<宽度\>,\<高度\>*</td><td>

替代独立查看器的默认大小。

*示例：* `Show POS 1920,0 SIZE 960,1080`
</td></tr><tr><td>
SLIDESHOW</td><td>
/S</td><td>

*(无值)*</td><td>

启动图像幻灯片。如果当前在源文件列表中选中任何文件，则幻灯片中仅显示这些图像 - 否则，将显示当前文件夹中的所有图像文件。与 **LISTSIBLINGS** 论证一起使用，无论当前选定的文件数量多少，始终包括文件夹中的所有文件。

你可以在配置中 **[幻灯片](/Manual/preferences/preferences_categories/viewer/standalone_viewer/slideshow.zh.md)** 页面上调整幻灯片速度，并选择顺序应为线性还是随机。

*示例：* `Show SLIDESHOW LISTSIBLINGS FULLSCREEN`
</td></tr><tr><td>
THUMBNAILSIZE</td><td>
/K</td><td>

*\<大小\>*</td><td>

将活动文件窗口中缩略图的大小设置为指定像素大小。这将替代配置中 **[文件列表模式/缩略图](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.zh.md)** 页面中设置的全局缩略图大小。

*示例：* `Show THUMBNAILSIZE 192`
</td></tr><tr><td>
</td><td>
</td><td>

*\<宽度\>,\<高度\>*</td><td>

分别设置缩略图的宽度和高度。这让你可以根据需要设置非方形缩略图大小。

*示例：* `Show THUMBNAILSIZE 92,64`
</td></tr><tr><td>
</td><td>
</td><td>

*\<更改\>*</td><td>

通过指定增量值调整活动文件窗口中缩略图的大小。你必须指定前导 **+** 或 **-** 以使其成为相对大小更改。

*示例：* `Show THUMBNAILSIZE +32`
</td></tr><tr><td>
</td><td>
</td><td>

*\<更改 w\>,\<更改 h\>*</td><td>

通过指定增量调整缩略图的宽度和高度。

*示例：* `Show THUMBNAILSIZE +16,+24`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

仅将大小更改应用于 [双栏](/Manual/basic_concepts/the_lister/dual_display/README.zh.md)文件窗口中的左侧（或顶部的）文件列表。

*示例：* `Show THUMBNAILSIZE left,128`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

仅将大小更改应用于右侧（或底部的）文件列表。

*示例：* `Show THUMBNAILSIZE +64,right`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

仅将大小更改应用于源文件列表。

*示例：* `Show THUMBNAILSIZE source,64,80`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

仅将大小更改应用于目标文件列表。

*示例：* `Show THUMBNAILSIZE dest,256`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

将大小更改应用于双栏文件窗口中所有可见的文件列表，但仅限于活动的文件夹标签。

*示例：* `Show THUMBNAILSIZE both,+32`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

将大小更改应用于文件窗口中的所有文件列表，包括双栏文件窗口的两侧和所有文件夹标签。这是默认行为。

*示例：* `Show THUMBNAILSIZE all,+32`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

将缩略图大小重置为配置中设置的值。

*示例：* `Show THUMBNAILSIZE all,reset`
</td></tr><tr><td>
</td><td>
</td><td>

**list**</td><td>

生成 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)，这些按钮提供了多种缩略图大小选项，根据你的系统 DPI 设置进行智能选择。

*示例：* `Show THUMBNAILSIZE=list`
</td></tr><tr><td>
USEEXISTING</td><td>
/O</td><td>

*(无值)*</td><td>

强制重新使用现有的查看器窗口 - 如果当前有一个现有的查看器已打开，则绝不会打开一个新窗口。这将替代配置中 **[独立查看器](/Manual/preferences/preferences_categories/viewer/standalone_viewer/README.zh.md)** 页面上的 **重复使用现有查看器窗口** 选项。

*示例：* `Show USEEXISTING`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

阻止重新使用现有的查看器窗口 - 始终会打开一个新窗口。
*示例：* `Show USEEXISTING=no`
</td></tr><tr><td>
</td><td>
</td><td>

**avoid**</td><td>

避免切换到另一个虚拟桌面——只会在同一桌面上重复使用窗口。这将覆盖 **避免切换桌面** 选项。

*示例：* `Show USEEXISTING=yes,avoid`
</td></tr><tr><td>
</td><td>
</td><td>

**noavoid**</td><td>

不避免切换到另一个虚拟桌面。

*示例：* `Show USEEXISTING=yes,noavoid`
</td></tr><tr><td>
VIEWERCMD</td><td>
/K</td><td>

*\<命令\>*</td><td>

仅用于[独立查看器](/Manual/additional_functionality/viewing_images/README.zh.md)中，此命令构成了默认查看器工具栏、上下文菜单和热键的基础。这些命令还可以用于在查看器上下文中运行的脚本。
</td></tr><tr><td>
</td><td>
</td><td>

**alpha**</td><td>

切换启用或禁用 *隐藏 Alpha 通道* 选项。

*示例：* `Show VIEWERCMD=alpha`
</td></tr><tr><td>
</td><td>
</td><td>

**backcol**</td><td>

覆盖或重置查看器的 *背景颜色*。这仅会影响支持它的查看器和插件，并且对于检查使用透明度叠加在各种背景颜色上的图像很有用。更改是临时的（不会保存到配置中），并且只会影响运行该命令的查看器。

如果没有指定颜色，背景就会重置为配置中的颜色。

*示例：* `Show VIEWERCMD=backcol`

否则，应使用 ##RRGGBB 十六进制或 RRR,GGG,BBB 十进制格式指定颜色：

*示例：* `Show VIEWERCMD=backcol,#FFFFFF`  
*示例：* `Show VIEWERCMD=backcol,127,127,127`

如果您需要一个在每次按下时切换颜色覆盖的按钮或热键，请编辑默认查看器工具栏中的 **视图/背景颜色** 菜单中的项目，以了解有关该操作如何执行的详细信息。
</td></tr><tr><td>
</td><td>
</td><td>

**close**</td><td>

关闭独立查看器窗口。

*示例：* `Show VIEWERCMD=close`
</td></tr><tr><td>
</td><td>
</td><td>

**cmdbar**</td><td>

在查看器窗口底部显示一个 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 风格的命令栏，该命令栏可让您键入一个临时命令，以便在查看器上下文中运行。

*示例：* `Show VIEWERCMD=cmdbar`
</td></tr><tr><td>
</td><td>
</td><td>

**copy**</td><td>

将图像的当前所选区域复制到剪贴板。

*示例：* `Show VIEWERCMD=copy`
</td></tr><tr><td>
</td><td>
</td><td>

**copyto**</td><td>

提示输入一个新文件名，以便将当前查看的文件复制到该文件名中。

*示例：* `Show VIEWERCMD=copyto`
</td></tr><tr><td>
</td><td>
</td><td>

**crop**</td><td>

将图像裁剪为当前所选区域。除非另存图像，否则不会修改磁盘上的文件。

*示例：* `Show VIEWERCMD=crop`
</td></tr><tr><td>
</td><td>
</td><td>

**cut**</td><td>

将当前查看的文件剪切到剪贴板。如果您随后在列表中执行粘贴操作，查看的文件将被移动。

*示例：* `Show VIEWERCMD=cut`
</td></tr><tr><td>
</td><td>
</td><td>

**delete**</td><td>

删除当前查看的文件（在默认情况下提示确认后）。

*示例：* `Show VIEWERCMD=delete`

使用此命令和实际的 [Delete 命令](delete.zh.md) 之间的主要区别在于，在删除当前文件后，查看器将移动到下一个文件。

可以指定以下其它选项：

- **close** 在删除图像后自动关闭查看器
- **noadvance** 在删除图像后停止查看器移动到下一个图像

您还可以指定以下一个或多个 [Delete 命令参数](delete.zh.md)：**shift**、**force**、**quiet**、**norecycle**、**recycle** 或 **secure**（或 **secure=*n*** 表示 *n* 次通过）。

任何其它选项或 Delete 命令参数都必须包含在逗号分隔列表中，且不含任何额外的空格：

*示例：* `Show VIEWERCMD=delete,quiet,secure=2`

如果没有给出其它参数，则会隐含 **shift** 参数，以维持旧的默认行为。如果您只想禁用 shift 参数，请使用 **noshift**：

*示例：* `Show VIEWERCMD=delete,noshift`
</td></tr><tr><td>
</td><td>
</td><td>

**dragsel**</td><td>

可让您从 **OnViewerEvent** 脚本事件触发某些鼠标操作。例如，当触发脚本事件以告诉您用户单击了鼠标左键时，您可以根据鼠标在窗口上的单击位置触发滚动或展开模式。

默认行为是滚动；使用“select”关键字可触发选择模式，使用“expand”可触发展开/滚动模式。

默认情况下，该命令假定使用鼠标左键触发事件——对鼠标右键使用“rclick”关键字，对鼠标中键使用“mclick”关键字。

您还可以通过在命令行中传递“pos:x,y”来提供单击坐标——如果未提供，则假定为当前鼠标位置。

*示例：* `Show VIEWERCMD=dragsel,expand,mclick,pos:100,100`
</td></tr><tr><td>
</td><td>
</td><td>

**first**</td><td>

返回查看列表中的第一个文件。

*示例：* `Show VIEWERCMD=first`
</td></tr><tr><td>
</td><td>
</td><td>

**flip**</td><td>

翻转当前查看的图像。除非另存图像，否则不会修改磁盘上的文件。与 **horiz** 一起使用可水平翻转，或与 **vert** 一起使用可垂直翻转。

*示例：* `Show VIEWERCMD=flip,horiz`
</td></tr><tr><td>
</td><td>
</td><td>

**frame**</td><td>

启用或禁用独立查看器的 *图片框架* 选项。这仅会影响支持它的查看器和插件（大多数图像类型，但不包括 Office 或 PDF 文档等内容）。该更改影响所有已打开的查看器窗口，并被保存到配置中。

默认情况下会切换框架。

*示例：* `Show VIEWERCMD=frame`

您还可以指定“on”或“off”以明确启用或禁用框架。

*示例：* `Show VIEWERCMD=frame,on`
</td></tr><tr><td>
</td><td>
</td><td>

**fullscreen**</td><td>

启用或禁用全屏模式。默认情况下，它将切换设置，但您也可以明确启用或禁用它。

*示例：* `Show VIEWERCMD=fullscreen`  
*示例：* `Show VIEWERCMD=fullscreen,on`  
*示例：* `Show VIEWERCMD=fullscreen,off`
</td></tr><tr><td>
</td><td>
</td><td>

**gamma**</td><td>

调整图像显示的 gamma 值。调整值可以是以下值之一：

|                   |                                   |
|-------------------|-----------------------------------|
| **+***\<值\>*  | 将 gamma 值增加 *\<值\>*     |
| **-***\<值\>*  | 将 gamma 值减少 *\<值\>*     |
| *\<值\>*       | 将绝对 gamma 值设置为值       |
| **0-***\<值\>* | 设置绝对负 gamma 值 |
| **reset**         | 将 gamma 值重置为默认值      |

*示例：* `Show VIEWERCMD=gamma,+1`  
*示例：* `Show VIEWERCMD=gamma,reset`
</td></tr><tr><td>
</td><td>
</td><td>

**goto**</td><td>

转到列表中的指定文件。必须与指示图像的值一起使用，其中 **0** 是第一张图像，**1** 是第二张等等。此命令还可用于通过指定以 **+** 或 **-** 为前缀的数字，向前或向后跳转特定数量的文件。
*示例:* `Show VIEWERCMD=goto,0`  
*示例:* `Show VIEWERCMD=goto,+10`
</td></tr><tr><td>
</td><td>
</td><td>

**help**</td><td>

显示图像查看器的帮助信息。

*示例:* `Show VIEWERCMD=help`
</td></tr><tr><td>
</td><td>
</td><td>

**hex**</td><td>

在十六进制模式和非十六进制模式之间切换显示。

*示例:* `Show VIEWERCMD=hex`
</td></tr><tr><td>
</td><td>
</td><td>

**info**</td><td>

打开或关闭图像信息叠加显示。

*示例:* `Show VIEWERCMD=info`
</td></tr><tr><td>
</td><td>
</td><td>

**last**</td><td>

转到列表中的最后一个文件。

*示例:* `Show VIEWERCMD=last`
</td></tr><tr><td>
</td><td>
</td><td>

**listerlink**</td><td>

将查看器与打开它的文件窗口关联或解除关联。当文件窗口和查看器关联时，选择文件窗口中的文件将在查看器中显示，使独立的查看器成为脱离的预览窗格。

如果将 **listerlink** 单独指定，它将切换关联（假设文件窗口仍然存在）。还可以指定 **toggle** 以更加明确，或者指定 **on** 或 **off** 在不切换的情况下打开或关闭关联。

*示例:* `Show VIEWERCMD=listerlink`  
*示例:* `Show VIEWERCMD=listerlink,off`

此项用于通过查看器工具栏（等）运行，以更改现有查看器的关联状态。还提供了一个单独的 **LISTERLINK** 参数（如上），该参数可用于从文件窗口中打开新的查看器，并在它们一打开就将它们关联起来。
</td></tr><tr><td>
</td><td>
</td><td>

**mark**</td><td>

此关键字用于控制图像标记。它具有许多不同的功能，通过将它与以下关键字组合使用来访问这些功能：

|                                     |                                                                                                                                                                                                                       |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <nobr>*(无子关键字)*</nobr> | 切换当前图像的标记状态（与 **toggle** 关键字相同）。                                                                                                                                                  |
| **browse**                          | 浏览标记的图片（在新标签页中打开标记的图片集合）。                                                                                                                                           |
| **clear**                           | 清除所有标记。                                                                                                                                                                                                      |
| **exchange**                        | 将当前图像与先前标记的图像交换（取消对前一个图像的标记，并在此处标记当前图像）。                                                                                                |
| **first**                           | 跳转到第一个标记的图像。                                                                                                                                                                                       |
| **last**                            | 跳转到最后一个标记的图像。                                                                                                                                                                                        |
| **next**                            | 跳转到下一个标记的图像。                                                                                                                                                                                        |
| **nohighlight**                     | 在其描述的条件为真时，防止按钮高亮（例如，当图像被标记时，停止 **mark,toggle** 按钮的高亮）。与 **on**、**off**、**toggle** 和 **view** 一起使用。 |
| **off**                             | 取消标记当前图像。                                                                                                                                                                                            |
| **on**                              | 标记当前图像。                                                                                                                                                                                              |
| **prev**                            | 跳转到前面一个标记的图像。                                                                                                                                                                                  |
| **return**                          | 从跳转返回到您之前正在查看的图像（例如，在 **mark,first** 之后跳转到第一个标记的图像，**mark,return** 将您放回之前的位置）。                                         |
| **toggle**                          | 切换当前图像的标记状态。                                                                                                                                                                                   |
| **view**                            | 打开或关闭标记的窗格。                                                                                                                                                                                    |

*示例:* `Show VIEWERCMD=mark,toggle,nohighlight`  
*示例:* `Show VIEWERCMD=mark,view`
</td></tr><tr><td>
</td><td>
</td><td>

**markfirst**</td><td>

将其与 **next** 和 **prev** 结合使用，以便在移动到下一个（或上一个）图像之前标记前一个图像。

*示例:* `Show VIEWERCMD=next,markfirst`
</td></tr><tr><td>
</td><td>
</td><td>

**meta**</td><td>

打开或关闭嵌入式元数据面板，并控制其宽度。与以下关键字组合使用：

|             |                                                                                                                                                                                                                     |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *\<宽度\>* | 以像素为单位指定元数据面板的宽度。                                                                                                                                                                  |
| **grow**    | 打开元数据面板时，查看器窗口会尽可能地增长以容纳该面板。关闭面板时，只要窗口没有手动调整大小，它就会恢复其原始宽度。                                           |
| **nofocus** | 防止元数据编辑器在打开时获得输入焦点。                                                                                                                                                |
|**关闭**|关闭元数据面板。|
|**打开**|打开元数据面板。|
|**切换**|打开并关闭元数据面板。|

*示例：`Show VIEWERCMD=meta,toggle,grow,400`*
</td></tr><tr><td>
</td><td>
</td><td>

**最窄宽度**</td><td>

将当前查看器窗口的宽度保存为新的最窄宽度。当新的查看器打开时，它们不会自动调整为小于此宽度的尺寸。

*示例：`Show VIEWERCMD=minwidth`*
</td></tr><tr><td>
</td><td>
</td><td>

**下一个显示器**</td><td>

假设是多显示器系统，将查看器移至下一个显示器。在全屏查看器中使用时最有用。

*示例：`Show VIEWERCMD=monitornext`*
</td></tr><tr><td>
</td><td>
</td><td>

**上一个显示器**</td><td>

将查看器移至上一个显示器。

*示例：`Show VIEWERCMD=monitorprev`*
</td></tr><tr><td>
</td><td>
</td><td>

**移动至**</td><td>

提示输入新文件名以移动当前正在查看的文件。

*示例：`Show VIEWERCMD=moveto`*
</td></tr><tr><td>
</td><td>
</td><td>

**下一个**</td><td>

转到并查看列表中的下一个文件。你可以将其与**标记第一个**结合在一起以首先标记当前图像。

*示例：`Show VIEWERCMD=next`*
</td></tr><tr><td>
</td><td>
</td><td>

**下一列表**</td><td>

生成图像列表中后续文件的列表（充当[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md) - 设计用于附加到*下一步*按钮上的下拉菜单）。

*示例：`Show VIEWERCMD=nextlist`*
</td></tr><tr><td>
</td><td>
</td><td>

**非全屏**</td><td>

当查看器不在全屏模式下时隐藏此按钮。可以将其与任何其它关键字结合使用。

*示例：`Show VIEWERCMD=delete,notfullscreen`*
</td></tr><tr><td>
</td><td>
</td><td>

**独占全屏**</td><td>

除非查看器处于全屏模式下，否则隐藏此按钮。可以将其与任何其它关键字结合使用。

*示例：`Show VIEWERCMD=close,onlyfullscreen`*
</td></tr><tr><td>
</td><td>
</td><td>

**打开**</td><td>

打开并查看新文件。默认情况下，这会提示要打开的文件，但可以在命令行中提供文件名（例如，来自脚本）。

*示例：`Show VIEWERCMD=open`*
*示例：`Show VIEWERCMD="open,c:\my pictures\image.jpg"`*
</td></tr><tr><td>
</td><td>
</td><td>

**关于插件**</td><td>

显示当前查看器插件的*关于*对话框。

*示例：`Show VIEWERCMD=pluginabout`*
</td></tr><tr><td>
</td><td>
</td><td>

**插件配置**</td><td>

显示当前查看器插件的配置对话框（如果提供）。

*示例：`Show VIEWERCMD=plugincfg`*
</td></tr><tr><td>
</td><td>
</td><td>

**插件命令**</td><td>

触发当前查看器插件提供的命令（如果提供）。命令指定为一个数字，其中**0**表示第一个命令，**1**表示第二个，依此类推。

*示例：`Show VIEWERCMD=plugincmd,0`*
</td></tr><tr><td>
</td><td>
</td><td>

**插件命令列表**</td><td>

生成当前查看器插件提供的命令列表（如果提供）。这充当[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)。

*示例：`Show VIEWERCMD=plugincmds`*
</td></tr><tr><td>
</td><td>
</td><td>

**上一个**</td><td>

转到并查看列表中的上一个文件。你可以将其与**标记第一个**结合在一起以首先标记当前图像。

*示例：`Show VIEWERCMD=prev,markfirst`*
</td></tr><tr><td>
</td><td>
</td><td>

**上一个列表**</td><td>

生成图像列表中之前文件的列表（充当[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md) - 设计用于附加到*上一步*按钮上的下拉菜单）。

*示例：`Show VIEWERCMD=prevlist`*
</td></tr><tr><td>
</td><td>
</td><td>

**打印**</td><td>

打印当前正在查看的文件。

*示例：`Show VIEWERCMD=print`*
</td></tr><tr><td>
</td><td>
</td><td>

**刷新**</td><td>

刷新当前正在查看的文件。文件将从磁盘重新加载。

*示例：`Show VIEWERCMD=refresh`*
</td></tr><tr><td>
</td><td>
</td><td>

**重新选择**</td><td>

重新选择之前的选择。这使你可以轻松地将多个图像裁剪到同一个区域（即选择一个区域，裁剪并保存此图像，移动到下一个图像，重新选择之前的区域，裁剪并保存，...）。

*示例：`Show VIEWERCMD=reselect`*
</td></tr><tr><td>
</td><td>
</td><td>

**还原**</td><td>

撤消之前的裁剪操作。

*示例：`Show VIEWERCMD=restore`*
</td></tr><tr><td>
</td><td>
</td><td>

**旋转**</td><td>

旋转当前图像的显示。磁盘上的文件不会修改，除非你保存图像。旋转量可以按以下方式指定：

|                  |                                              |
|------------------|----------------------------------------------|
| **+***\<值\>* | 顺时针旋转*\<值\>*度      |
| **-***\<值\>* | 逆时针旋转*\<值\>*度 |
| *\<值\>*      | 将旋转设置为绝对值            |
| **重置**        | 重置旋转                           |

*示例：`Show VIEWERCMD=rotate,+90`*
</td></tr><tr><td>
</td><td>
</td><td>

**保存**</td><td>

保存你对当前图像所做的任何更改。与**静默**选项一起使用以静默替换现有文件。如果图像不是 Opus 能够保存的格式之一（当前为 PNG、JPG、BMP 和 GIF），则此命令不可用 - 在这种情况下，你可以使用 **另存为**将图像保存为其中一种格式。

*示例：`Show VIEWERCMD=save,quiet`*
</td></tr><tr><td>
</td><td>
</td><td>

**另存为**</td><td>

提示输入新文件名以保存图像。*另存图片*对话框还允许你选择要保存的图像格式。你还可以选择在命令行中提供要保存的文件名（例如，来自脚本）。

*示例：`Show VIEWERCMD=saveas`*
*示例：`Show VIEWERCMD="saveas,c:\my pictures\image.png"`*
</td></tr><tr><td>
</td><td>
</td><td>

**滚动**</td><td>

滚动当前图像。你必须指定**水平**或**竖直**以指示你想要滚动的维度，结合另一个关键字以指示滚动多远。关键词如下：

|              |                                                                              |
|--------------|------------------------------------------------------------------------------|
| **底部**   | 滚动到底部（垂直）或最右侧（水平）。                   |
| **向下**     | 向下（垂直）或向右（水平）滚动。                                |
| **horiz**    | 水平滚动。                                                         |
| **pagedown** | 向下滚动一页（垂直）或向右滚动一页（水平）。                  |
| **pageup**   | 向上滚动一页（垂直）或向左滚动一页（水平）。                     |
| **top**      | 滚动到顶部（垂直）或最左端（水平）。                       |
| **up**       | 向上滚动（垂直）或向左滚动（水平）。                                   |
| **vert**     | 垂直滚动。                                                           |
| **center**   | 滚动到中心。可以与 **horiz** 或 **vert** 组合使用。 |

*示例:* `Show VIEWERCMD=scroll,vert,pagedown`
</td></tr><tr><td>
</td><td>
</td><td>

**selaspect**</td><td>

修复选择区域的纵横比。您可以指定纵横比（16:9、3/2 等），或 **reset** 以取消该限制。

*示例:* `Show VIEWERCMD=selaspect,16:9`  
*示例:* `Show VIEWERCMD=selaspect,reset`
</td></tr><tr><td>
</td><td>
</td><td>

**selectall**</td><td>

选择整个图像。

*示例:* `Show VIEWERCMD=selectall`
</td></tr><tr><td>
</td><td>
</td><td>

**selectfile**</td><td>

从启动查看器的文件夹标签页中选择当前显示的文件。

*示例:* `Show VIEWERCMD=selectfile`
</td></tr><tr><td>
</td><td>
</td><td>

**shortcutbar**</td><td>

打开或关闭快捷方式栏的显示。

*示例:* `Show VIEWERCMD=shortcutbar`
</td></tr><tr><td>
</td><td>
</td><td>

\*\*slideshow \*\*</td><td>

打开或关闭幻灯片模式。

*示例:* `Show VIEWERCMD=slideshow`

您还可以明确地打开它或关闭它，无论其当前状态如何：

*示例:* `Show VIEWERCMD=slideshow,on`  
*示例:* `Show VIEWERCMD=slideshow,off`
</td></tr><tr><td>
</td><td>
</td><td>

**statusbar**</td><td>

打开或关闭状态栏。

*示例:* `Show VIEWERCMD=statusbar`
</td></tr><tr><td>
</td><td>
</td><td>

**toolbar**</td><td>

打开或关闭工具栏的显示。

*示例:* `Show VIEWERCMD=toolbar`
</td></tr><tr><td>
</td><td>
</td><td>

**wallpaper**</td><td>

将当前显示的图像设置为 Windows 桌面壁纸。默认情况下，壁纸将设置为 *居中* 模式，但您可以提供其它关键字来指定模式：

|             |                                                                                                                                                  |
|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| **center**  | 图像将以纯色填充环绕的形式置于桌面的中心（这是默认设置）。                                          |
| **fill**    | 扩展或缩小图像以填满桌面（为了保持纵横比，顶部和底部或两侧可能会留有黑条）。    |
| **fit**     | 扩展或缩小图像以填满桌面（为了保持纵横比，可能会裁剪图像的顶部和底部或两侧）。 |
| **span**    | 将图像跨越多个显示器。                                                                                              |
| **stretch** | 拉伸图像以适应显示器，忽略其纵横比。                                                                       |
| **tile**    | 以瓷砖方式多次水平和垂直排列小图像以适应显示器。                                                       |

*示例:* `Show VIEWERCMD=wallpaper,span`
</td></tr><tr><td>
</td><td>
</td><td>

**zoom**</td><td>

调整当前图像显示的缩放级别。您必须提供其它关键字来指示所需的缩放级别：

|                  |                                                                                                                                  |
|------------------|----------------------------------------------------------------------------------------------------------------------------------|
| **+**            | 放大。                                                                                                                         |
| **-**            | 缩小。                                                                                                                        |
| **+***\<value\>* | 放大指定量（百分比）。                                                                                         |
| **-***\<value\>* | 缩小指定量（百分比）。                                                                                        |
| *\<value\>*      | 缩放到原始大小的绝对百分比。                                                                             |
| **fit**          | 将缩放模式设置为“适合页面” - 如果图像太大而无法一次全部容纳，则会将图像缩小以适合页面。                  |
| **grow**         | 将缩放模式设置为“增长到页面” - 如果图像较大，则会将其缩小以适应；如果图像较小，则会将其扩展以填满页面。 |
| **tile**         | 将缩放模式设置为“平铺” - 以瓷砖方式多次水平和垂直排列小图像以填满页面。               |
| **reset**        | 重置缩放级别。                                                                                                            |

*示例:* `Show VIEWERCMD=zoom,+`
</td></tr><tr><td>
VIEWPANECMD</td><td>
/K</td><td>

\<*command*\></td><td>

向文件窗口的查看器窗格发送命令。

大多数可用命令对应于查看器窗格工具栏和上下文菜单中的按钮，并且存在，以便您可以创建热键来执行相同操作。
</td></tr><tr><td>
</td><td>
</td><td>

**backcol**</td><td>

更改查看器窗格的背景颜色，覆盖配置中指定的颜色。

这仅影响支持它的图像查看器和插件，并且可用于针对各种背景颜色检查使用透明度的图像。

如果没有指定颜色，则将背景重置为配置中的颜色：

*示例:* `Show VIEWPANECMD=backcol`

否则，应以 #RRGGBB 十六进制或 RRR,GGG,BBB 十进制格式指定颜色：

*示例:* `Show VIEWPANECMD=backcol,#FFFFFF`
</td></tr><tr><td>
</td><td>
</td><td>

**clear**</td><td>

卸载任何现有文件并清除查看器窗格。

*示例:* `Show VIEWPANECMD=clear`
</td></tr><tr><td>
</td><td>
</td><td>

**frame**</td><td>

打开或关闭图片帧（如果当前查看器支持）。

*示例:* `Show VIEWPANECMD=frame`
</td></tr><tr><td>
</td><td>
</td><td>

**prev**</td><td>

转到预览文件。

*示例:* `Show VIEWPANECMD=prev`
</td></tr><tr><td>
</td><td>
</td><td>

**next**</td><td>

转到下一个文件。

*示例:* `Show VIEWPANECMD=next`
</td></tr><tr><td>
</td><td>
</td><td>

**open**</td><td>

在查看器窗格中打开特定文件。

*示例:* `Show VIEWPANECMD="open,C:\My Image.png"`

在使用 **open** 时，您可能希望首先运行 **Set VIEWPANELOCK=On** 以防止在文件列表中选择其它文件时查看器窗格加载其它文件。
您还可以使用 **FILE** 参数指定要打开的文件：

*示例：* `Show FILE="C:\Cats\Best Cat.jpg" VIEWPANECMD=open`

最后，`Show VIEWPANECMD=open` 自身可以用于只是打开查看器窗格，尽管 **Set VIEWPANE=On** 或 **Set VIEWPANE=Toggle** 是执行此操作的更标准的方式。

</td></tr><tr><td>
</td><td>
</td><td>

**rotateleft**</td><td>

将图像逆时针旋转 90 度。

*示例：* `Show VIEWPANECMD=rotateleft`
</td></tr><tr><td>
</td><td>
</td><td>

**rotateright**</td><td>

将图像顺时针旋转 90 度。

*示例：* `Show VIEWPANECMD=rotateright`
</td></tr><tr><td>
</td><td>
</td><td>

**zoomfit**</td><td>

如果需要，缩小图像以适应可用空间。

*示例：* `Show VIEWPANECMD=zoomfit`
</td></tr><tr><td>
</td><td>
</td><td>

**zoomgrow**</td><td>

放大或缩小图像以匹配可用空间。

*示例：* `Show VIEWPANECMD=zoomgrow`
</td></tr><tr><td>
</td><td>
</td><td>

**zoomin**</td><td>

将缩放量增加一步。

*示例：* `Show VIEWPANECMD=zoomin`
</td></tr><tr><td>
</td><td>
</td><td>

**zoomout**</td><td>

将缩放量减少一步。

*示例：* `Show VIEWPANECMD=zoomout`
</td></tr><tr><td>
</td><td>
</td><td>

**zoomreset**</td><td>

以 100% 的缩放显示图像。

*示例：* `Show VIEWPANECMD=zoomreset`
</td></tr></tbody>
</table>