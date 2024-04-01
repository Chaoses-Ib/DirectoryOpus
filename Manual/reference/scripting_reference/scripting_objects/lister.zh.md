**文件窗口**对象表示一个开放的[文件窗口](/Manual/basic_concepts/the_lister/README.zh.md)窗口。可以在[DOpus](dopus.zh.md).**listers**属性中提供当前打开的文件窗口对象集合，如果命令导致打开一个新的文件窗口，则**[Results](results.zh.md)**对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
activetab</td><td>

*对象:***[Tab](tab.zh.md)**</td><td>

返回一个**[Tab](tab.zh.md)**对象，表示当前活动（源）标签页。
</td></tr><tr><td>
bottom</td><td>

*int*</td><td>
文件窗口窗口底部边缘坐标。
</td></tr><tr><td>
custom_title</td><td>

*string*</td><td>

返回文件窗口的自定义标题（如果有），由**Set LISTERTITLE**命令设置。这可能是一个空字符串。*title*属性返回实际的窗口标题。
</td></tr><tr><td>
desktop</td><td>

*string*</td><td>
返回此文件窗口所在的虚拟桌面的ID。
</td></tr><tr><td>
desttab</td><td>

*对象:***[Tab](tab.zh.md)**</td><td>

返回一个**[Tab](tab.zh.md)**对象，表示当前目标标签页（在双栏器文件窗口中）。
</td></tr><tr><td>
dual</td><td>

*int*</td><td>

指示文件窗口是否处于[双栏器模式](/Manual/basic_concepts/the_lister/dual_display/README.zh.md)。可能的值为：

|     |                                 |
|-----|---------------------------------|
| 0   | 单显示模式             |
| 1   | 双栏，垂直布局   |
| 2   | 双栏，水平布局 |
</td></tr><tr><td>
dualsize</td><td>

*int*</td><td>

返回双栏器的当前拆分百分比（例如**50**表示它们的尺寸相同）。
</td></tr><tr><td>
foreground</td><td>

*bool*</td><td>

如果此文件窗口当前是前台（活动）窗口，则返回**True**。
</td></tr><tr><td>
lastactive</td><td>

*bool*</td><td>

如果此文件窗口当前是活动的文件窗口（前台窗口），或最近的活动文件窗口，则返回**True**。
</td></tr><tr><td>
layout</td><td>

*string*</td><td>

提供此文件窗口引用的[文件窗口布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md)的名称（如果有）。
</td></tr><tr><td>
left</td><td>

*int*</td><td>
文件窗口窗口左边缘坐标。
</td></tr><tr><td>
metapane</td><td>

*int*</td><td>

指示[元数据窗格](/Manual/basic_concepts/the_lister/metadata_pane.zh.md)当前是否打开。可能的值为：

|     |                                          |
|-----|------------------------------------------|
| 0   | 元数据窗格未打开                |
| 1   | 元数据窗格打开，垂直布局   |
| 2   | 元数据窗格打开，水平布局 |
</td></tr><tr><td>
right</td><td>

*int*</td><td>
文件窗口窗口右边缘坐标。
</td></tr><tr><td>
state</td><td>

*string*</td><td>

返回单显示模式文件窗口的状态：

|     |             |
|-----|-------------|
| 0   | 关闭         |
| 1   | 来源      |
| 2   | 目标      |
| 4   | 已锁定      |
</td></tr><tr><td>
style</td><td>

*string*</td><td>

返回最后应用于文件窗口的[文件窗口样式](/Manual/basic_concepts/the_lister/styles.zh.md)的名称，或者如果不存在，则返回一个空字符串。这只是加载的最后一个样式，并不意味着文件窗口仍然看起来相同；从应用样式以来，用户可能已经通过其它方法打开或关闭面板并进行其它更改。
</td></tr><tr><td>
tabs</td><td>

*集合:***[Tab](tab.zh.md)**</td><td>

返回一个**[Tab](tab.zh.md)**对象集合，表示此文件窗口中的所有标签页。在双栏器文件窗口中，这包括左右文件列表中的标签页。
</td></tr><tr><td>
tabgroupleft</td><td>

*string*</td><td>

返回最后加载到文件窗口左侧的文件夹标签页组的名称，或者如果没有加载任何组，则返回一个空字符串。

只有在加载了一个文件夹标签页组时才更改名称。如果用户自加载组以来进行了更改，则当前标签页可能不再类似于命名的标签页组。该名称在默认文件窗口和保存的布局中跨重启持续存在。
</td></tr><tr><td>
tabgroupright</td><td>

*string*</td><td>

与上面的**tabgroupleft**类似，但用于文件窗口的右侧（如果有）。
</td></tr><tr><td>
tabsleft</td><td>

*集合:***[Tab](tab.zh.md)**</td><td>

返回一个**[Tab](tab.zh.md)**对象集合，表示双栏器文件窗口的左侧/顶部的标签页。在单显示器文件窗口中，这等同于文件窗口中的所有标签页。
</td></tr><tr><td>
tabsright</td><td>

*集合:***[Tab](tab.zh.md)**</td><td>

返回一个**[Tab](tab.zh.md)**对象集合，表示双栏器文件窗口的右侧/底部的标签页。在单显示器文件窗口中，这将返回一个空集合。
</td></tr><tr><td>
title</td><td>

*string*</td><td>
返回文件窗口窗口的当前标题。
</td></tr><tr><td>
toolbars</td><td>

*集合:***[Toolbar](../../command_reference/internal_commands/toolbar.zh.md)**</td><td>

返回一个**[Toolbar](../../command_reference/internal_commands/toolbar.zh.md)**对象的集合，表示此文件窗口中当前打开的所有工具栏。

每次脚本请求该集合时都会直接获取该集合，并且不是快照，因此您不需要调用**Update**来反映更改。
</td></tr><tr><td>
top</td><td>

*int*</td><td>
文件窗口窗口顶边缘坐标；
</td></tr><tr><td>
tree</td><td>

*int*</td><td>

指示[文件夹树](/Manual/basic_concepts/the_lister/navigation/folder_tree.zh.md)是否打开。可能的值为：

|     |                                                      |
|-----|------------------------------------------------------|
| 0   | 文件夹树未打开                              |
| 1   | 单个树打开，在文件窗口的左侧     |
| 2   | 单个树打开，在文件窗口的右侧    |
| 3   | 打开了两个文件夹树（在双栏器文件窗口中） |
</td></tr><tr><td>
utilpage</td><td>

*string*</td><td>

如果[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)当前打开，则返回一个字符串，指出当前选定的实用程序页面。可能的值包括 **find**（表示查找面板的简单版本）、**findadvanced**、**sync**、**dupe**、**undo**、**filelog**、**ftplog**、**otherlog**、**email**。
</td></tr><tr><td>
utilpane</td><td>

*int*</td><td>

指示[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)是否打开。可能的值为：

|     |                           |
|-----|---------------------------|
| 0   | 实用程序面板未打开 |
| 1   | 实用程序面板打开     |
</td></tr><tr><td>
vars</td><td>

*对象:***[Vars](vars.zh.md)**</td><td>

此**[Vars](vars.zh.md)**对象表示所有已定义的具有*文件窗口范围*的变量（作用域为此文件窗口）。
</td></tr><tr><td>
viewpane</td><td>

*int*</td><td>

指示[查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md)是否打开。可能的值为：
|     |                                        |
|-----|----------------------------------------|
| 0   | 查看器面板没有打开                |
| 1   | 查看器面板打开，垂直布局   |
| 2   | 查看器面板打开，水平布局 |
</td></tr><tr><td>
viewpanefile</td><td>

*对象:***[路径](path.zh.md)**</td><td>

返回文件窗口查看器面板当前显示的文件的路径。如果当前没有显示文件，路径将为空字符串。

每次脚本要求获取路径时，都直接获取路径，而不是获取快照，因此无需调用 **Update** 即可反映更改。
</td></tr><tr><td>
windowstate</td><td>

*字符串*</td><td>

返回文件窗口窗口的当前可见性状态。可能的值有：

|            |                                  |
|------------|----------------------------------|
| **最小**    |文件窗口已最小化          |
| **最大**    |文件窗口已最大化          |
| **隐藏** |文件窗口已隐藏             |
| **正常** |文件窗口正常显示 |
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Dlg</td><td>

*无*</td><td>

*对象:***[对话框](dialog.zh.md)**</td><td>

创建一个新的 **[对话框](dialog.zh.md)** 对象，可用来显示对话框和弹出菜单。对话框的 **窗口** 属性将自动分配给此文件窗口。
</td></tr><tr><td>
IsOnCurrentDesktop</td><td>

*无*</td><td>

*布尔值*</td><td>

如果文件窗口在当前虚拟桌面上，则返回 **True**。
</td></tr><tr><td>
MoveToDesktop</td><td>

\<字符串:电脑桌\></td><td>

*布尔值*</td><td>

将文件窗口窗口移动到指定的虚拟桌面。如果成功，则返回 **True**。
</td></tr><tr><td>
SetTaskbarGroup</td><td>

\<字符串:组\></td><td>

*布尔值*</td><td>

用于更改文件窗口窗口在任务栏上与其它 Opus 窗口分组的方式。指定组名称以将窗口移动到替代组，或省略 group 参数以重置回默认组。如果将一个或多个窗口移动到同一组，则它们将被组合在一起，并与其它默认组分开。

这仅在启用任务栏分组时才起作用。组名限制为 103 个字符，并且如果较长，将被截断。组名中的空格和点会自动转换为下划线。成功时返回 **True**。
</td></tr><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

当脚本首次访问某个特定的 **文件窗口** 对象时，会对文件窗口状态进行快照。如果脚本随后对该文件窗口进行更改（例如，它打开一个新标签页或移动窗口），这些更改将不会反映在对象中（除非另有说明）。若要将对象与文件窗口重新同步，请调用 **文件窗口.Update** 方法。
</td></tr></tbody>
</table>