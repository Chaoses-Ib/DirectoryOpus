# 控件

**Control** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 上的控件；它允许您阅读和修改控件的值（和内容）。使用 **[Dialog](dialog.zh.md).Control** 方法来获取 **Control** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
bg</td><td>

*string*</td><td>

设置或查询该控件背景（填充）使用的颜色。此格式为 *\#RRGGBB*（十六进制）或 *RRR,GGG,BBB*（十进制）。目前，只有 *静态文本* 和 *列表视图* 控件支持此属性。
</td></tr><tr><td>
charcase</td><td>

*string*</td><td>

对于 *编辑* 控件，获取或设置控件的案例设置。值包括 **upper**、**lower** 和 **normal**。
</td></tr><tr><td>
columns</td><td>

*object:***[DialogListColumns](dialoglistcolumns.zh.md)**</td><td>

对于 *列表视图* 控件，返回一个 **[DialogListColumns](dialoglistcolumns.zh.md)** 对象，该对象允许您查询或修改 *详细信息* 模式下的列。
</td></tr><tr><td>
count</td><td>

*int*</td><td>

返回控件中包含的项目数（例如，在 *组合框*、*列表框* 或 *列表视图* 中，返回列表中的项目数）。
</td></tr><tr><td>
cuetext</td><td>

*string*</td><td>
获取或设置单行编辑控件的提示文本。这是控件为空时显示的文本，旨在帮助用户。
</td></tr><tr><td>
cx</td><td>

*int*</td><td>
设置或查询控件的宽度，以像素为单位。
</td></tr><tr><td>
cy</td><td>

*int*</td><td>
设置或查询控件的高度，以像素为单位。
</td></tr><tr><td>
enabled</td><td>

*bool*</td><td>

设置或查询控件的启用状态。如果控件已启用，则返回 **True**；如果已禁用，则返回 **False**。您可以设置此属性来更改状态。
</td></tr><tr><td>
fg</td><td>

*string*</td><td>

设置或查询该控件文本（前景）使用的颜色。此格式为 *\#RRGGBB*（十六进制）或 *RRR,GGG,BBB*（十进制）。目前，只有 *静态文本* 和 *列表视图* 控件支持此属性。
</td></tr><tr><td>
focus</td><td>

*bool*</td><td>

设置或查询控件的输入焦点状态。如果控件当前具有输入焦点，则返回 **True**；否则，返回 **False**。设置为 **True** 以给予控件输入焦点。
</td></tr><tr><td>
label</td><td>

*string* 或  
*object:***[Image](image.zh.md)**</td><td>

设置或查询控件的标签或标题。并非所有控件都有标签 - 这对没有标签的控件（如 *列表视图*）不起作用。

请注意，对于 *组合框* 控件，此属性仅对可编辑组合框有效 - 也就是说，可以输入您自己的文本的控件。您可以使用此属性来设置或查询可编辑文本的当前值。

对于设置为“图像”模式的静态控件，还可以提供一个 **[Image](image.zh.md)** 对象，该对象是从 **[DOpus](dopus.zh.md).LoadImage** 或 **[Script](script.zh.md).LoadImage** 方法获取的。

对于 *标签页* 控件，您可以通过指定索引来设置或查询各个标签页的标签；例如，`Control.label(0)` 将引用第一个标签页的标签。
</td></tr><tr><td>
mode</td><td>

*string*</td><td>

对于 *列表视图* 控件，允许您更改或查询当前的视图模式。有效值包括 **icon**、**details**、**smallicon**、**list**。
</td></tr><tr><td>
readonly</td><td>

*bool*</td><td>

设置或查询 *编辑* 控件的 *只读* 状态。
</td></tr><tr><td>
redraw</td><td>

*bool*</td><td>

设置或查询控件的重绘状态。某些控件允许您关闭重绘，以便进行多次更改而不会出现明显的闪烁（例如，向 *列表视图* 中添加大量项目）。请设置为 **False** 以关闭重绘，或设置为 **True** 以在更改控件后重新打开重绘。
</td></tr><tr><td>
rotate</td><td>

*int*</td><td>

对于设置为“图像”模式的 *静态文本* 控件，您可以设置此属性来旋转显示的图像。提供的值是图像初始方向的度数。
</td></tr><tr><td>
style</td><td>

*string*</td><td>

设置或查询用于显示此控件标签的字体样式。该字符串由零个或多个字符组成；有效字符包括 **b**（粗体）和 **i**（斜体）。

目前，只有 *静态文本* 控件支持此属性。
</td></tr><tr><td>
textbg</td><td>

*string*</td><td>

设置或查询此控件文本背景（填充）使用的颜色。此格式为 *\#RRGGBB*（十六进制）或 *RRR,GGG,BBB*（十进制）。

目前，只有 *列表视图* 控件支持此属性。
</td></tr><tr><td>
title</td><td>

*string* 或  
*object:***[Image](image.zh.md)**</td><td>

**label** 属性的备用名称。术语 **title** 用于对话框编辑器和 XML 资源中，也可以在这里用作便捷名称。
</td></tr><tr><td>
value</td><td>

*string* 或  
*bool* 或  
*int 或*  
*object:***[DialogListItem](dialoglistitem.zh.md)** 或  
*object:***[Vector](vector.zh.md)**</td><td>

设置或查询控件的值。此属性的含义取决于控件的类型：

- **编辑控件**：返回或接受一个字符串，表示编辑控件的当前内容。
- **复选框**：对于简单的开/关复选框，返回或接受一个 *bool* - 选中时为 **True**，未选中时为 **False**。对于三态复选框，返回或接受一个 *int* - 未选中时为 **0**，选中时为 **1**，不确定状态时为 **2**。
- **单选按钮**：返回或接受一个 *bool* - 选中时为 **True**，未选中时为 **False**。
- **标签页**：返回或接受一个 *int*，表示标签页控件中当前选定的页面。
- **列表框/组合框/列表视图**：返回或接受一个 **[DialogListItem](dialoglistitem.zh.md)**，表示所选项目。当设置值时，它还接受一个 *int*，表示所选项目的以 0 为基数的索引。

请注意，对于多选 *列表框* 或 *列表视图*，此值将返回一个 **[Vector](vector.zh.md)** of [DialogListItem](dialoglistitem.zh.md) 对象，表示所有当前选定的项。
</td></tr><tr><td>
visible</td><td>

*bool*</td><td>

设置或查询控件的可见状态。如果控件可见，则返回 **True**；如果隐藏，则返回 **False**。您可以设置此属性来隐藏或显示控件。
</td></tr><tr><td>
x</td><td>

*int*</td><td>
设置或查询控件的左侧 (x) 位置，以像素为单位。
</td></tr><tr><td>
y</td><td>

*int *</td><td>
设置或查询控件的顶部 (y) 位置，以像素为单位。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
AddGroup</td><td>

\<string:name\>  
\<int:id\>  
\[\<string:flags\>\]</td><td>

*int*</td><td>

向 *列表视图* 控件添加一个新组。添加到列表中的项目可以有选择地分组。每个组必须有唯一的 ID。

可选标志为“c”（组可折叠）和“d”（组在折叠后展开）。例如，**AddGroup("Unimportant", 100, "cd")** 将添加一个名为 *Unimportant* 的组，该组最初为折叠状态。
</td></tr>
</td></tr><tr><td>
AddItem</td><td>

\<string:name\>  
\[\<int:value\>\]  
\[\<int:groupid\>\]

或者

\<object:item\></td><td>

*int*</td><td>

将一个新项目添加到控件（*列表框*、*组合框*或*列表视图*）中。第一个参数是项目的名称，第二个参数（可选）是要与项目关联的数据值。

当添加到已分组的*列表视图*中时，第三个参数（可选）提供要向其中添加项目的组的 ID（在这种情况下，必须提供第二个参数，如果没有需要的值，则可以将其设置为 0）。

*项目*被添加到列表的结尾。

您还可以传递从另一个控件获得的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

返回值指示列表中新项目的位置。

如果您正要添加到一个列表视图控件中，并且需要添加一个具有多列的项目，则可以像这样操作（JScript）：

    var i = listview.AddItem("这是第 1 列");
    listview.GetItemAt(i).subitems(0) = "这是第 2 列";
    listview.GetItemAt(i).subitems(1) = "这是第 3 列";
</td></tr><tr><td>
AutoSize</td><td>

\[\<bool:height\>\]</td><td>

*bool*</td><td>

自动调整控件大小（如果控件类型支持自动调整大小）。如果自动调整了控件大小，则返回 **True**。

如果将可选 *height* 参数设置为 true，则垂直以及水平自动调整控件大小。
</td></tr><tr><td>
DeselectItem</td><td>

\<int:position\>

或

\<object:item\></td><td>

*int*</td><td>

此方法主要用于多选*列表框*和*列表视图*控件。它允许您取消选择控件中单个项目的同时，让其它项目保持选中（或不受影响）。

您可以指定要选择的项目的索引（0 表示第一个项目，1 表示第二个项目，以此类推）或从 **GetItemAt** 或 **GetItemByName** 方法获取的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

您还可以指定 **-1** 以取消选择列表框中的所有项目。
</td></tr><tr><td>
EnableGroupView</td><td>

\<bool:enable\></td><td>
无</td><td>

仅适用于*列表视图*控件。默认情况下，组视图已关闭；在使用 **AddGroup** 方法添加组后，使用 **EnableGroupView** 启用组视图。
</td></tr><tr><td>
GetGroupById</td><td>

\<int:id\></td><td>

object:**[DialogListGroup](dialoglistgroup.zh.md)**</td><td>

返回一个 **[DialogListGroup](dialoglistgroup.zh.md)** 对象，该对象表示您先前使用 **AddGroup** 方法添加到*列表视图*控件的具有指定 ID 的组。
</td></tr><tr><td>
GetItemAt</td><td>

\<int:position\></td><td>

object:**[DialogListItem](dialoglistitem.zh.md)**</td><td>

返回一个 **[DialogListItem](dialoglistitem.zh.md)** 对象，其表示控件中包含的项目，该项目位于指定的索引（*列表框*、*组合框*或*列表视图*）的位置。项目 0 代表列表中的第一个项目，项目 1 代表第二个项目，以此类推。
</td></tr><tr><td>

GetItemByLabel  
GetItemByName</td><td>

\<string:name\></td><td>

object:**[DialogListItem](dialoglistitem.zh.md)**</td><td>

返回一个 **[DialogListItem](dialoglistitem.zh.md)** 对象，其表示控件中包含的项目，其名称为指定名称（*列表框、组合框或列表视图*）。由于历史原因，此方法有两个名称（...*Label* 和 ...*Name*），您可以互换使用这两个方法名称）。
</td></tr><tr><td>
InsertItemAt</td><td>

\<int:position\>  
\<string:name\>  
\[\<int:value\>\]  
\[\<int:groupid\>\]

或者

\<int:position\>  
\<object:item\></td><td>

*int*</td><td>

在控件（*列表框、组合框或列表视图*）中插入一个新项目。第一个参数是要插入项目的的位置（0 表示列表的开头，1 表示第二个位置，以此类推）。第二个参数是项目的名称，第三个参数（可选）是要与项目关联的数据值。

当添加到已分组的*列表视图*中时，第四个参数（可选）提供要向其中添加项目的组的 ID（在这种情况下，必须提供第三个参数，如果没有需要的值，则可以将其设置为 0）。

除了 *name* 和 *value*，您还可以传递从另一个控件获得的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

返回值指示列表中新项目的位置。
</td></tr><tr><td>
MoveItem</td><td>

\<int:position\>  
或  
\<object:item\>  
\<int:newposition\></td><td>

*int*</td><td>

将一个现有项目移动到新的位置（*列表框*、*组合框*或*列表视图*）。第一个参数是要移动的项目（您可以传递其索引或者 **[DialogListItem](dialoglistitem.zh.md)** 对象），第二个参数是要将项目移动到的新位置。

返回值指示已移动项目的列表中的位置。
</td></tr><tr><td>
RemoveGroup</td><td>

\<int:id\></td><td>
无</td><td>

从*列表视图*控件中删除指定的组。
</td></tr><tr><td>
RemoveItem</td><td>

\<int:position\>  
或  
\<object:item\></td><td>
无</td><td>

从控件（*列表框、组合框或列表视图*）中删除一个项目。您可以提供要删除项目的索引（0 表示第一个项目，1 表示第二个项目，以此类推）或从 **GetItemAt** 或 **GetItemByName** 方法获取的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

您还可以指定 **-1** 以彻底清除控件中的内容，一次删除所有项目。
</td></tr><tr><td>
SelectItem</td><td>

\<int:position\>  
或  
\<object:item\>  
或   
\<string:tab\></td><td>

*int*</td><td>

选择控件中的一个项目。对于*列表框、组合框或列表视图*，您可以指定要选择的项目的索引（0 表示第一个项目，1 表示第二个项目，以此类推）或从 **GetItemAt** 或 **GetItemByName** 方法获取的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

对于多选*列表框*或*列表视图*，您还可以指定 **-1** 以选择控件中的所有项目。

对于*标签页控件*，您可以通过指定要显示的页面的名称（即子对话框的名称）来更改哪个页面可见。

返回值表示新的选定索引。
</td></tr><tr><td>
SelectRange</td><td>

\<int:start\>  
\<int:end\>

或

\<object:item1\>  
\<object:item2\></td><td>

object:**[Vector](vector.zh.md)**</td><td>

选择*编辑控件*（或*组合框*控件中编辑字段）中的文本。这两个参数表示所需选择范围的开始位置和结束位置。要选择全部内容，请对开始位置使用 **0**，对结束位置使用 **-1**。

返回值是一个**[Vector](vector.zh.md)**，其具有两个成员，提供选择的当前开始位置和结束位置。要查询范围，而不更改它，只要无参数调用 **SelectRange** 方法，即可进行查询。

在*列表框*或*列表视图*控件中，此方法选择一个项目范围。
</td></tr><tr><td>
SetFont</td><td>

\<int:id\></td><td>
无</td><td>

将控件使用的字体设置为指定的字体。*id* 参数必须来自 **[Dialog](dialog.zh.md).CreateFont** 的前一次调用。您可以使用 0 将字体重置为其默认值。
</td></tr><tr><td>
SetItemWidth</td><td>

\<int:width\></td><td>
无</td><td>

设置设置为 **list** 或 **smallicon** 模式的列表视图控件中项目的像素宽度。指定 **-1** 以自动调整项目的尺寸。
</tr ></tr><tr><td>
SetPos</td><td>

\<int:x\>  
\<int:y\></td><td>
none</td><td>
设置此控件的位置。X 和 Y 坐标以像素为单位。
</td></tr><tr><td>
SetPosAndSize</td><td>

\<int:x\>  
\<int:y\>  
\<int:cx\>  
\<int:cy\></td><td>
none</td><td>
通过一次操作设置控件的位置和大小。所有坐标都以像素为单位。
</td></tr><tr><td>
SetSize</td><td>

\<int:cx\>  
\<int:cy\></td><td>
none</td><td>
设置此控件的大小。cx（宽度）和 cy（高度）值以像素为单位。
</td></tr></tbody>
</table>