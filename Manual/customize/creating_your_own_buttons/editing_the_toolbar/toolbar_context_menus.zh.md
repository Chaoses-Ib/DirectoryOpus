# 工具栏上下文菜单

在自定义模式时，所有工具栏按钮都具有上下文菜单，可以通过右键单击访问该菜单。此上下文菜单上的命令会根据按钮类型而异。

对于“常规”按钮，上下文菜单如下所示：

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/button_context_menu_1.png) </td>
<td></td>
<td><strong>剪切</strong>：将按钮剪切到剪贴板 - 当粘贴到工具栏上的另一个位置时，按钮将被移动。<br />
<strong>复制</strong>：将按钮复制到剪贴板 - 您可以将副本粘贴到同一工具栏或其它工具栏。<br />
<strong>粘贴</strong>：从剪贴板粘贴按钮 - 将按钮插入到您右键单击的按钮左侧。<br />
<strong>删除</strong>：删除按钮。<br />
<strong>编辑</strong>：编辑按钮。<br />
<strong>三个按钮</strong>：将简单按钮变为多功能按钮（“三个按钮按钮”）。<br />
<strong>开始组</strong>：在此按钮的左侧插入分隔符。<br />
<strong>插入新项</strong>：在此按钮的左侧插入新按钮、下拉菜单或间隔符。<br />
</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>

对于*下拉菜单*，其上下文菜单看起来几乎相同。

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/button_context_menu_2.png) </td>
<td></td>
<td><strong>三个按钮</strong>选项不可用（不能将下拉菜单转换为多功能按钮），并且有一个新命令：<br /><br />
<strong>转换为菜单按钮</strong>：此命令将下拉菜单（其唯一目的是下拉其它按钮的菜单）转换为下拉菜单按钮。菜单按钮组合了一个常规按钮（您可以为其分配功能）和一个下拉菜单。按钮的主体部分运行指定命令，而显示箭头符号的右侧较小按钮则用于弹开菜单。<br />
![](/Manual/images/media/menu_button.png) <br />
有关更多详细信息，请参阅多功能按钮的<a href="drop-down_buttons_and_menus">下拉按钮和菜单</a>主题。</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>

同样地，*下拉菜单按钮*的上下文菜单非常相似，只多了一个命令。

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/button_context_menu_3.png) </td>
<td></td>
<td><strong>始终启用下拉</strong>：此选项使下拉部分菜单按钮始终可用，即使“按钮部分”被禁用也是如此。<br />
<strong>按住或右键单击以下拉</strong>：此选项删除可见的下拉箭头。可以通过右键单击按钮或左键单击并按住鼠标按钮直到菜单出现来访问下拉菜单。<br /><br />
默认文件列表工具栏中的<strong>后退</strong>按钮（![](/Manual/images/media/always_enable_menu_button.png)）使用了这两个选项。当您处于桌面级别时，<strong>后退</strong>按钮将被禁用（因为您无法从那里进一步后退）。如果没有启用<strong>始终启用下拉</strong>选项，您将无法访问连接到<strong>后退</strong>按钮的下拉菜单中的命令。<br />
</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>

*字段按钮*的上下文菜单如下所示：

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/field_context_menu.png) </td>
<td></td>
<td><strong>字段类型</strong>：让您更改字段按钮的类型。字段按钮只能通过从自定义对话框的命令标签页中拖放相应的项目（或复制现有的字段）来创建，但一旦按钮存在，您可以从上下文菜单中将其更改为任何可用的类型。<br />
<strong>全宽</strong>：将字段设置为<em>全宽</em>模式。在此模式下，它将在（Opus 不处于自定义模式时）扩展到占据工具栏中所有可用空间。如果字段不处于全宽模式，则可以将其调整为所需的任何大小。<br />
<strong>恢复焦点</strong>：如果启用此选项，则在字段中按<strong>Enter</strong>键将自动将焦点返回到文件列表。<br /><br />
有关字段按钮的详细信息，请参阅<a href="field_buttons">字段按钮</a>主题。<br />
</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>

最后，*工具栏本身*的上下文菜单（在右键单击工具栏的空白区域时显示）如下所示：

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/toolbar_context_menu.png) </td>
<td></td>
<td><strong>自定义</strong>：如果将<strong>自定义</strong>对话框隐藏在另一个窗口后面，则将其置于前面。<br />
<strong>恢复此工具栏的出厂设置</strong>：仅在<a href="/basic_concepts/the_lister/toolbars/the_default_toolbars">默认工具栏</a>上可用，这会将工具栏重置为其初始设置。您对该工具栏所做的任何更改都将丢失。<br />
<strong>新建</strong>：在工具栏中添加新按钮、菜单、菜单按钮或间隔符。新按钮显示在工具栏的末尾。<br />
<strong>粘贴</strong>：当您将按钮复制或剪切到剪贴板时，此命令让您将其粘贴到工具栏末尾。<br />
<strong>工具栏</strong>：此子菜单显示所有工具栏的列表，让您能够打开或关闭它们。此子菜单还包含<strong>恢复工具栏出厂设置</strong>命令 - 选择此命令将重置<strong>所有</strong><a href="/basic_concepts/the_lister/toolbars/the_default_toolbars">默认工具栏</a>为它们的初始设置。您对默认工具栏所做的任何更改都将丢失。您创建的任何工具栏都将被关闭，但除此之外不会受到影响。<br />
<strong>锁定工具栏</strong>：从工具栏边缘移除拖动控制点，防止您四处移动它们。<br />
<strong>关闭</strong>：关闭工具栏。<br />
</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>