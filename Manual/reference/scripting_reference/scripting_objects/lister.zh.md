# Lister

**Lister** 对象代表一个打开的 [文件窗口](/Manual/basic_concepts/the_lister/README.zh.md) 窗口。可以使用 **[DOpus](dopus.zh.md).listers** 属性获取当前打开的文件窗口对象的集合，如果命令导致打开新的文件窗口，则可以使用 **[Results](results.zh.md)** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
activetab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，代表当前活动的（源）标签页。
</td></tr><tr><td>
bottom</td><td>

*int*</td><td>
文件窗口窗口下边缘坐标。
</td></tr><tr><td>
custom_title</td><td>

*string*</td><td>

返回文件窗口的自定义标题（如果有），由 **Set LISTERTITLE** 命令设置。这可能是一个空字符串。*title* 属性返回实际的窗口标题。
</td></tr><tr><td>
desktop</td><td>

*string*</td><td>
返回此文件窗口所在的虚拟桌面的 ID。
</td></tr><tr><td>
desttab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，代表当前的目标标签页（在双栏文件窗口中）。
</td></tr><tr><td>
dual</td><td>

*int*</td><td>

指示文件窗口是否处于 [双栏模式](/Manual/basic_concepts/the_lister/dual_display/README.zh.md)。可能的值为：

|     |                                 |
|-----|---------------------------------|
| 0   | 单显示模式             |
| 1   | 双栏，垂直布局   |
| 2   | 双栏，水平布局 |
</td></tr><tr><td>
dualsize</td><td>

*int*</td><td>

返回双栏的当前拆分百分比（例如 **50** 表示它们的大小相等）。
</td></tr><tr><td>
foreground</td><td>

*bool*</td><td>

如果此文件窗口当前是前台（活动）窗口，则返回 **True**。
</td></tr><tr><td>
lastactive</td><td>

*bool*</td><td>

如果此文件窗口当前是活动的文件窗口（前台窗口），或者是最最近活动的文件窗口，则返回 **True**。
</td></tr><tr><td>
layout</td><td>

*string*</td><td>

提供此文件窗口所来自的 [文件窗口布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md) 的名称（如果有）。
</td></tr><tr><td>
left</td><td>

*int*</td><td>
文件窗口窗口左边缘坐标。
</td></tr><tr><td>
metapane</td><td>

*int*</td><td>

指示 [元数据窗格](/Manual/basic_concepts/the_lister/metadata_pane.zh.md) 当前是否打开。可能的值为：

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
| 1   | 源      |
| 2   | 目标 |
| 4   | 锁定      |
</td></tr><tr><td>
style</td><td>

*string*</td><td>

返回最后应用于文件窗口的 [文件窗口样式](/Manual/basic_concepts/the_lister/styles.zh.md) 的名称，如果没有则返回空字符串。这只是最后加载的样式，并不意味着文件窗口仍然看起来相同；用户可能在样式应用后通过其它方法打开或关闭面板并进行其它更改。
</td></tr><tr><td>
tabs</td><td>

*collection:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象的集合，代表此文件窗口中的所有标签页。在双栏文件窗口中，这包括左侧和右侧文件列表中的标签页。
</td></tr><tr><td>
tabgroupleft</td><td>

*string*</td><td>

返回最后加载到文件窗口左侧的文件夹标签页组的名称，如果未加载任何组，则返回空字符串。

名称仅在加载文件夹标签页组时更改。如果用户自加载组后进行了更改，则当前标签页可能不再类似于命名标签页组。该名称在重新启动时保留，并贯穿默认文件窗口和保存的布局。
</td></tr><tr><td>
tabgroupright</td><td>

*string*</td><td>

与上面的 **tabgroupleft** 相似，但适用于文件窗口的右侧（如果有）。
</td></tr><tr><td>
tabsleft</td><td>

*collection:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象的集合，代表双栏文件窗口左侧/上侧的标签页。在单显示文件窗口中，这等效于文件窗口中的所有标签页。
</td></tr><tr><td>
tabsright</td><td>

*collection:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象的集合，代表双栏文件窗口右侧/下侧的标签页。在单显示文件窗口中，这将返回一个空集合。
</td></tr><tr><td>
title</td><td>

*string*</td><td>
返回文件窗口窗口的当前标题。
</td></tr><tr><td>
toolbars</td><td>

*collection:***[Toolbar](../../command_reference/internal_commands/toolbar.zh.md)**</td><td>

返回一个 **[Toolbar](../../command_reference/internal_commands/toolbar.zh.md)** 对象的集合，代表此文件窗口中当前打开的所有工具栏。

该集合每次脚本请求时都直接获取，而不是快照，因此您不需要调用 **Update** 即可反映更改。
</td></tr><tr><td>
top</td><td>

*int*</td><td>
文件窗口窗口上边缘坐标；
</td></tr><tr><td>
tree</td><td>

*int*</td><td>

指示 [文件夹树](/Manual/basic_concepts/the_lister/navigation/folder_tree.zh.md) 当前是否打开。可能的值为：

|     |                                                      |
|-----|------------------------------------------------------|
| 0   | 文件夹树未打开                              |
| 1   | 单个树打开，位于文件窗口的左侧     |
| 2   | 单个树打开，位于文件窗口的右侧    |
| 3   | 两个文件夹树打开（在双栏文件窗口中） |
</td></tr><tr><td>
utilpage</td><td>

*string*</td><td>

如果 [实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md) 当前打开，则返回一个字符串，指示当前选定的实用程序页面。可能的值为 **find**（表示查找面板的简单版本）、**findadvanced**、**sync**、**dupe**、**undo**、**filelog**、**ftplog**、**otherlog**、**email**。
</td></tr><tr><td>
utilpane</td><td>

*int*</td><td>

指示 [实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md) 当前是否打开。可能的值为：

|     |                           |
|-----|---------------------------|
| 0   | 实用程序面板未打开 |
| 1   | 实用程序面板打开     |
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.zh.md)**</td><td>

此 **[Vars](vars.zh.md)** 对象代表所有定义了 *文件窗口范围*（对此文件窗口具有范围）的变量。
</td></tr><tr><td>
viewpane</td><td>

*int*</td><td>

指示 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md) 当前是否打开。可能的值为：

|     |                                        |
|-----|----------------------------------------|
| 0   | 查看器窗格未打开                |
| 1   | 查看器窗格打开，垂直布局   |
| 2   | 查看器窗格打开，水平布局 |
</td></tr><tr><td>
viewpanefile</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回文件窗口查看器窗格当前显示的文件的路径。如果当前没有显示文件，则路径将为空字符串。

每次脚本请求时都会直接获取路径，而不是快照，因此您不需要调用 **Update** 即可反映更改。
</td></tr><tr><td>
windowstate</td><td>

*string*</td><td>

返回文件窗口窗口的当前可见性状态。可能的值为：

|            |                                  |
|------------|----------------------------------|
| **min**    |文件窗口已最小化          |
| **max**    |文件窗口已最大化          |
| **hidden** |文件窗口已隐藏             |
| **normal** |文件窗口以正常方式显示 |
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Dlg</td><td>

*无*</td><td>

*object:***[Dialog](dialog.zh.md)**</td><td>

创建一个新的 **[Dialog](dialog.zh.md)** 对象，允许您显示对话框和弹出菜单。对话框的 **window** 属性将自动分配给此文件窗口。
</td></tr><tr><td>
IsOnCurrentDesktop</td><td>

*无*</td><td>

*bool*</td><td>

如果文件窗口在当前虚拟桌面上，则返回 **True**。
</td></tr><tr><td>
MoveToDesktop</td><td>

\<string:desktop\></td><td>

*bool*</td><td>

将文件窗口窗口移动到指定的虚拟桌面。如果成功，则返回 **True**。
</td></tr><tr><td>
SetTaskbarGroup</td><td>

\<string:group\></td><td>

*bool*</td><td>

用于更改文件窗口窗口在任务栏上与其它 Opus 窗口的组合方式。指定一个组名称将窗口移动到另一个组，或者省略组参数将重置回默认组。如果一个或多个窗口移动到同一个组，它们将组合在一起，与默认组分开。

这仅在启用任务栏分组时有效。组名称限制为 103 个字符，如果更长，将被截断。组名称中的空格和点将自动转换为下划线。成功时返回 **True**。
</td></tr><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

脚本第一次访问特定 **Lister** 对象时，将获取文件窗口状态的快照。如果脚本随后对该文件窗口进行了更改（例如，它打开了新标签页或移动了窗口），则这些更改不会反映在对象中（除非另有说明）。要将对象与文件窗口重新同步，请调用 **Lister.Update** 方法。
</td></tr></tbody>
</table>