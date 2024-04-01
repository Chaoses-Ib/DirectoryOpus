# Toolbar

**Toolbar** 内部命令可用于：

- 打开或关闭工具栏或工具栏组
- 打开或关闭浮动工具栏，控制其外观和屏幕上的位置
- 保存一个新组或修改默认工具栏组
- 将一个工具栏导入到您的配置中
- 重置您的工具栏为默认值

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
说明
</th></tr></thead><tbody><tr><td>
APPBAR</td><td>
/K</td><td>

**left**</td><td>

当打开一个浮动工具栏时，指定此参数，将工具栏对接到屏幕的左边缘。与 **POS** 结合使用，控制它对接到哪个显示器。

*示例：* `Toolbar my_tools STATE=float APPBAR=left TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**top**</td><td>

将工具栏对接到屏幕顶部。

*示例：* `Toolbar my_tools STATE=floatactive APPBAR=top`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

将工具栏对接到屏幕的右侧。

*示例：* `Toolbar my_tools FLOAT POS=1920,0 APPBAR=right`
</td></tr><tr><td>
</td><td>
</td><td>

**bottom**</td><td>

将工具栏对接到屏幕底部。

*示例：* `Toolbar my_tools STATE=float APPBAR=bottom`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

如果工具栏已经被对接，取消对接。

*示例：* `Toolbar my_tools FLOAT APPBAR=off POS=50,100`
</td></tr><tr><td>
AUTOCLOSE</td><td>
/S</td><td>

*(无值)*</td><td>

在打开一个浮动工具栏时添加此参数，在运行命令后，使工具栏自动关闭。这可以让您拥有一个工具栏，可以弹出（例如通过按键），运行命令并再次自动关闭，而且不必向工具栏上的所有按钮添加 `Toolbar NAME=*this CLOSE` 命令。

*示例：* `Toolbar my_tools STATE=float AUTOCLOSE`
</td></tr><tr><td>
CLOSE</td><td>
/O</td><td>

*(无值)*</td><td>

关闭用 **NAME** 参数指定的工具栏。请注意，**NAME** 是此命令的默认参数，**NAME** 关键字本身无需出现。该工具栏只会关闭在当前的文件窗口中，除非还指定了 **LOCAL=no** 以全局关闭它。

*示例：* `Toolbar Operations CLOSE`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

关闭当前文件窗口中的所有工具栏。

*示例：* `Toolbar CLOSE=all`
</td></tr><tr><td>
FLOAT</td><td>
/O</td><td>

*(无值)*</td><td>

将工具栏作为浮动工具栏打开。这相当于指定 **STATE=float**。使用各种参数可以更好地控制浮动工具栏。如果与 **UPDATE** 参数结合使用，可以对已打开的工具栏进行更改。

*示例：* `Toolbar my_tools FLOAT TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**default**</td><td>

使用默认外观打开浮动工具栏。如果没有指定（并且没有指定其它参数），Opus 将记住工具栏上次浮动时的设置。

*示例：* `Toolbar my_tools FLOAT=default`
</td></tr><tr><td>
</td><td>
</td><td>

**active**</td><td>

激活新打开的工具栏（相当于 **STATE=floatactive**）。

*示例：* `Toolbar my_tools FLOAT=active`
</td></tr><tr><td>
</td><td>
</td><td>

**vertical**</td><td>

垂直而不是水平地布局浮动工具栏。

*示例：* `Toolbar my_tools FLOAT=vertical`
</td></tr><tr><td>
</td><td>
</td><td>

\*\*locked \*\*</td><td>

锁定浮动工具栏，防止其调整大小或移动。

*示例：* `Toolbar my_tools FLOAT=vertical,locked POS=100,100`
</td></tr><tr><td>
</td><td>
</td><td>

**autohide**</td><td>

设置浮动工具栏在对接时自动隐藏。

*示例：* `Toolbar my_tools FLOAT=autohide APPBAR=bottom`
</td></tr><tr><td>
</td><td>
</td><td>

**roundededges**</td><td>

使用圆角显示工具栏。

*示例：* `Toolbar my_tools FLOAT=roundededges`
</td></tr><tr><td>
</td><td>
</td><td>

**grid**</td><td>

使浮动工具栏中的所有按钮大小相同。

*示例：* `Toolbar my_tools FLOAT=vertical,grid`
</td></tr><tr><td>
</td><td>
</td><td>

**frame**</td><td>

使用框架显示浮动工具栏。

*示例：* `Toolbar my_tools FLOAT=frame,roundededges`
</td></tr><tr><td>
</td><td>
</td><td>

**noframe**</td><td>

不带框架地显示浮动工具栏。

*示例：* `Toolbar my_tools FLOAT=noframe TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**transparent**</td><td>

使浮动工具栏透明。

*示例：* `Toolbar my_tools FLOAT=noframe,transparent`
</td></tr><tr><td>
</td><td>
</td><td>

**taskbar**</td><td>

使用系统任务栏主题显示浮动工具栏。

*示例：* `Toolbar my_tools FLOAT=taskbar,autohide`
</td></tr><tr><td>
</td><td>
</td><td>

**glass**</td><td>

使用玻璃显示浮动工具栏。

*示例：* `Toolbar my_tools FLOAT=glass`
</td></tr><tr><td>
</td><td>
</td><td>

**topopus**</td><td>

设置浮动工具栏出现在其它 Opus 窗口的顶部。

*示例：* `Toolbar my_tools FLOAT=topopus`
</td></tr><tr><td>
</td><td>
</td><td>

**toplevel**</td><td>

设置浮动工具栏出现在所有其它窗口的顶部。

*示例：* `Toolbar my_tools FLOAT=toplevel`
</td></tr><tr><td>
</td><td>
</td><td>

**hotkeys**</td><td>

在浮动工具栏中启用热键。

*示例：* `Toolbar my_tools FLOAT=hotkeys`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

当与生成项目列表的命令一起使用时（参见 [dynamic buttons](/Manual/Customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数在列表开头添加一个小的标题。当列表为空时，标题将被隐藏。标题只出现在在按钮自身级别上可能生成多个项目的命令中。

当 **HEADING** 单独使用时，而没有指定文本值，则主按钮的标签文本将用于标题。

*示例：* `Toolbar LIST=sets HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

如果您希望标题与按钮的标签不同，则可以指定标题文本。

*示例：* `Toolbar LIST HEADING="Toolbars"`
</td></tr><tr><td>
IMPORT</td><td>
/S</td><td>

*(无值)*</td><td>

将使用 **NAME** 参数指定的工具栏导入到您的 Opus 配置中。对于此命令，**NAME** 必须指定要导入的工具栏文件的完整路径。这在 **.dop**（工具栏）文件的上下文菜单中最为有用。

*示例：* `Toolbar NAME {f} IMPORT`
</td></tr><tr><td>
LINE</td><td>
/K</td><td>

*\<line\>*</td><td>

当打开一个工具栏时，指定该工具栏应出现在的工具栏行上。行号是相对于指定的工具栏状态指定的。例如，当 **STATE** 为 bottom 时，给定的行相对文件窗口底部的工具栏组。*\<line\>* 的计数从 0 开始。

*示例：* `Toolbar Operations LINE 1`
</td></tr><tr><td>
</td><td>
</td><td>

*\<line\>,\<position\>*</td><td>

指定新工具栏的行和位置。这可以让您在与现有工具栏相同的行上打开一个工具栏。*\<position\>* 被指定为从文件窗口窗口的左侧（或对于垂直工具栏来说是顶部）边缘开始的像素数。
<tr><td>
LIST</td><td>
/O</td><td>

*(无值)*</td><td>

显示所有工具栏的生成列表（充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。它允许您从下拉菜单中打开或关闭工具栏。

*示例:* `Toolbar LIST`
</td></tr><tr><td>
</td><td>
</td><td>

**sets**</td><td>

显示 [工具栏集](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.zh.md) 列表，并允许您在它们之间切换。

*示例:* `Toolbar LIST=sets`
</td></tr><tr><td>
</td><td>
</td><td>

**add**</td><td>

从生成列表中选择工具栏集后，它将以“添加”模式加载——这意味着其中包含的工具栏将被添加到任何当前打开的工具栏中。这将覆盖集内保存的选项状态。

*示例:* `Toolbar LIST=sets,add`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

从生成列表中选择工具栏集后，它将以“替换”模式加载——这意味着其中包含的工具栏将替换任何当前打开的工具栏。

*示例:* `Toolbar LIST=sets,replace`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

从生成列表中选择工具栏集后，它将关闭任何以前加载的集，但保持默认工具栏不受影响。再次选择集将关闭它。

*示例:* `Toolbar LIST=sets,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**usekeys**</td><td>

从生成列表中选择工具栏集后，Opus 将检查 **Shift** 和 **Ctrl** 键的状态以确定行为。按住 **Shift** 键将选择“添加”模式，按住 **Ctrl** 键将选择“替换”模式。

*示例:* `Toolbar LIST=sets,usekeys`
</td></tr><tr><td>
</td><td>
</td><td>

**nocontext**</td><td>

当 Opus 认为当前处于活动状态时，防止生成列表中的工具栏集显示为“已选中”。

*示例:* `Toolbar LIST=sets,add,nocontext`
</td></tr><tr><td>
LOADSET</td><td>
/O</td><td>

*(无值)*</td><td>

加载 NAME 参数指定的集。将使用集中指定的默认行为（“add”、“replace”或“toggle”），除非被覆盖。

*示例:* `Toolbar my_set LOADSET`
</td></tr><tr><td>
</td><td>
</td><td>

**add**</td><td>

将指定集中的工具栏添加到任何当前打开的工具栏中。

*示例:* `Toolbar my_set LOADSET=add`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

将任何当前打开的工具栏替换为指定集中的工具栏。

*示例:* `Toolbar my_set LOADSET=replace`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

关闭任何以前加载的集，但保持默认工具栏不受影响。如果指定的集已打开，它将被关闭（因此运行该命令两次会打开并关闭该集）。

*示例:* `Toolbar my_set LOADSET=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**usekeys**</td><td>

在加载集时使用 **Shift** 和 **Ctrl** 键的状态来确定行为。按住 **Shift** 键将选择“添加”模式，按住 **Ctrl** 键将选择“替换”模式。

*示例:* `Toolbar my_set LOADSET=usekeys`
</td></tr><tr><td>
LOCAL</td><td>
/O</td><td>

*(无值)*</td><td>

打开一个当前文件窗口的本地工具栏。请注意，由于这是默认行为，所以指定 **LOCAL** 或 **LOCAL=yes** 无效。

*示例:* `Toolbar Images LOCAL`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

在所有文件窗口中全局打开工具栏。

*示例:* `Toolbar Images LOCAL=no`
</td></tr><tr><td>
NAME</td><td>
</td><td>

*\<toolbar name\>*</td><td>

指定工具栏的名称——与其它参数结合使用以打开或关闭指定的工具栏。这是 **Toolbar** 命令的默认参数，因此无需使用 **NAME** 关键字，尽管这样做仍然是个好主意。如果未提供命令的其它参数，则将打开具名的工具栏。

*示例:* `Toolbar NAME="Images"`
</td></tr><tr><td>
</td><td>
</td><td>

**\*this**</td><td>

使命令适用于当前工具栏。当通过工具栏按钮使用时，Toolbar 命令将应用于包含该按钮的工具栏。

*示例:* `Toolbar NAME=*this CLOSE`
</td></tr><tr><td>
POS</td><td>
/K</td><td>

*\<x\>,\<y\>*</td><td>

打开浮动工具栏时，指定屏幕位置。该位置相对于主显示器左上角。它还可以用于控制停靠工具栏显示在哪个显示器上（通过将其与 **APPBAR** 参数结合使用）。

*示例:* `Toolbar Applications STATE=float POS 1200,80`
</td></tr><tr><td>
</td><td>
</td><td>

**mouse**</td><td>

浮动工具栏将以鼠标指针的当前位置为中心显示。

*示例:* `Toolbar LauncherBar STATE=float POS=mouse`
</td></tr><tr><td>
</td><td>
</td><td>

**mousel**</td><td>

浮动工具栏与鼠标指针的位置左对齐。

*示例:* `Toolbar Images STATE=float POS=mousel TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**mouser**</td><td>

浮动工具栏与鼠标指针右对齐。

*示例:* `Toolbar Applications STATE=float POS=mouser`
</td></tr><tr><td>
RESETDEFAULTS</td><td>
/K</td><td>

*(无值)*</td><td>

将工具栏重置为出厂默认设置。所有现有工具栏将关闭，默认工具栏将重置，然后仅打开这些工具栏。

如果您对默认工具栏进行了更改，则这些更改将丢失，但您的其它工具栏不会受到影响（除了在运行命令时这些工具栏如果打开，它们将被关闭之外）。

*示例:* `Toolbar RESETDEFAULTS`
</td></tr><tr><td>
</td><td>
</td><td>

**fdb**</td><td>

将 [地址栏](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.zh.md) 工具栏重置为其默认设置。将其与 **nolister** 结合使用以仅重置地址栏。

请注意，如果未提供 **stateonly** 或 **nolister** 参数，则表示 **fdb** 隐含（即 `Toolbar RESETDEFAULTS` 本身会重置地址栏工具栏和主要的文件窗口工具栏）。

*示例:* `Toolbar RESETDEFAULTS=nolister,fdb`
</td></tr><tr><td>
</td><td>
</td><td>

**nolister**</td><td>

默认情况下，所有文件窗口工具栏都会重置；将其与 **fdb** 和 **viewer** 结合使用以仅重置这些工具栏。

*示例:* `Toolbar RESETDEFAULTS=fdb,nolister,stateonly`
</td></tr><tr><td>
</td><td>
</td><td>

**stateonly**</td><td>

不修改工具栏本身——而是仅将当前工具栏集重置为默认设置。您自己创建的任何工具栏都将关闭，并显示默认工具栏集，但您对默认工具栏所做的任何修改都不会受到影响。

*示例:* `Toolbar RESETDEFAULTS=stateonly`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

在重置工具栏之前取消确认提示。

*示例:* `Toolbar RESETDEFAULTS=quiet`

<tr><td>
</td><td>
</td><td>

**viewer**</td><td>

重置 [图片查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 工具栏为其默认值。将其与 **nolister** 结合使用，仅重置查看器工具栏。

*示例:* `Toolbar RESETDEFAULTS=nolister,viewer`
</td></tr><tr><td>
SAVESET</td><td>
/O</td><td>

*(无值)*</td><td>

将当前工具栏保存为 [工具栏组](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.zh.md)。默认情况下，新组将设为“替换”模式。除非您使用 **NAME** 参数指定，否则 Opus 将提示输入组的名称。

*示例:* `Toolbar SAVESET`
</td></tr><tr><td>
</td><td>
</td><td>

**add**</td><td>

在“添加”模式中保存工具栏组。

*示例:* `Toolbar SAVESET=add`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在“切换”模式中保存工具栏组。

*示例:* `Toolbar SAVESET=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

覆盖现有的工具栏组时，取消显示确认提示。

*示例:* `Toolbar my_set SAVESET=toggle,quiet`
</td></tr><tr><td>
SETDEFAULT</td><td>
/O</td><td>

*(无值)*</td><td>

将当前文件窗口中的工具栏保存为默认工具栏组。

*示例:* `Toolbar SETDEFAULT`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

在保存组之前，取消显示确认提示。

*示例:* `Toolbar SETDEFAULT=quiet`
</td></tr><tr><td>
STATE</td><td>
/K</td><td>

**top**</td><td>

在文件窗口顶部打开指定的工具栏。这是此命令的默认行为。

*示例:* `Toolbar Applications STATE=top`
</td></tr><tr><td>
</td><td>
</td><td>

**bottom**</td><td>

在文件窗口底部打开工具栏。这些工具栏出现在窗口的最底部，位于所有其它文件窗口元素下方。

*示例:* `Toolbar Images STATE=bottom TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**fdbottom**</td><td>

在文件列表的底部打开工具栏。与 **bottom** 类似，但不会延伸至左侧最左边的文件夹树下方。

*示例:* `Toolbar Images STATE=fdbottom TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

在文件窗口左侧打开工具栏。这些工具栏垂直出现在窗口的最左侧边缘。

*示例:* `Toolbar Drives STATE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

在文件窗口右侧打开工具栏。这些工具栏垂直出现在窗口的最右侧边缘。

*示例:* `Toolbar Drives STATE=right LINE=1 TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**center**</td><td>

在文件窗口中心打开工具栏。这些工具栏出现在 [双栏](/Manual/basic_concepts/the_lister/dual_display/README.zh.md)文件窗口中的文件列表之间——根据文件列表的排列，它们将是水平方向或垂直方向。

*示例:* `Toolbar Drives STATE=center TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**viewpane**</td><td>

在文件列表和查看器窗格之间打开工具栏，当查看器窗格位于文件窗口右侧时。如果未打开查看器窗格，或者位于窗口底部，则此值的行为与 **right** 相同。

*示例:* `Toolbar Applications STATE=viewpane`
</td></tr><tr><td>
</td><td>
</td><td>

**tree**</td><td>

在左侧文件列表和文件夹树之间打开工具栏。

*示例:* `Toolbar Drives STATE=tree`
</td></tr><tr><td>
</td><td>
</td><td>

**float**</td><td>

浮动工具栏。您可以使用 **POS** 参数指定浮动工具栏的位置。

*示例:* `Toolbar Applications STATE=float TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**floatactive**</td><td>

浮动工具栏并使其处于活动状态。这可用于打开一个工具栏，并使其获得输入焦点，这样您就可以从键盘打开其下拉菜单。

*示例:* `Toolbar Tools STATE=floatactive POS=0,0`
</td></tr><tr><td>
</td><td>
</td><td>

**fdb**</td><td>

更改用于 [文件列表边框](/Manual/basic_concepts/the_lister/navigation/file_display_border.zh.md) 的工具栏。

*示例:* `Toolbar my_fdb STATE=fdb`
</td></tr><tr><td>
TOGGLE</td><td>
/S</td><td>

*(无值)*</td><td>

切换使用 **NAME** 参数指定的工具栏。如果工具栏当前未打开，则会将其打开，否则会将其关闭。

*示例:* `Toolbar Operations TOGGLE LINE=1`
</td></tr><tr><td>
UPDATE</td><td>
/S</td><td>

*(无值)*</td><td>

使用新的外观和位置值更新现有的浮动工具栏。如果工具栏当前未打开，则使用已定义的外观打开它。

*示例:* `Toolbar my_tools FLOAT=glass POS=50,50 UPDATE`
</td></tr></tbody>
</table>
```