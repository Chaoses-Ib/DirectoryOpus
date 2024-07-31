# Control

**Control** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 上的一个控件；它允许您读取和修改控件的值（和内容）。使用 **[Dialog](dialog.zh.md).Control** 方法获取 **Control** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
bg</td><td>

*string*</td><td>

设置或查询用于此控件背景（填充）的颜色。格式为 *\#RRGGBB*（十六进制）或 *RRR,GGG,BBB*（十进制）。目前仅支持 *静态文本* 和 *列表视图* 控件的此属性。
</td></tr><tr><td>
charcase</td><td>

*string*</td><td>

对于 *编辑* 控件，获取或设置控件的大小写设置。有效值为 **upper**、**lower** 和 **normal**。
</td></tr><tr><td>
columns</td><td>

*object:***[DialogListColumns](dialoglistcolumns.zh.md)**</td><td>

对于 *列表视图* 控件，返回一个 **[DialogListColumns](dialoglistcolumns.zh.md)** 对象，允许您查询或修改 *详细信息* 模式下的列。
</td></tr><tr><td>
count</td><td>

*int*</td><td>

返回控件中包含的项目数（例如，在 *组合框*、*列表框* 或 *列表视图* 中，返回列表中的项目数）。
</td></tr><tr><td>
cuetext</td><td>

*string*</td><td>
获取或设置单行编辑控件的提示文本。这是在编辑控件为空时显示的文本，用于帮助用户。
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

设置或查询控件的启用状态。如果控件已启用，则返回 **True**，如果已禁用，则返回 **False**。您可以设置此属性来更改状态。
</td></tr><tr><td>
fg</td><td>

*string*</td><td>

设置或查询用于此控件文本（前景）的颜色。格式为 *\#RRGGBB*（十六进制）或 *RRR,GGG,BBB*（十进制）。目前仅支持 *静态文本* 和 *列表视图* 控件的此属性。
</td></tr><tr><td>
focus</td><td>

*bool*</td><td>

设置或查询控件的输入焦点状态。如果控件当前具有输入焦点，则返回 **True**，如果它没有焦点，则返回 **False**。设置为 **True** 以使控件获得输入焦点。
</td></tr><tr><td>
image</td><td>

*string* 或  
*object:***[Image](image.zh.md)**</td><td>

对于设置为图像模式的按钮或静态控件，这会将图像分配给控件。您可以提供文件名（或内部图标名称 - 例如 `#about` 用于内部关于图标），或从 **[DOpus](dopus.zh.md).LoadImage** 或 **[Script](script.zh.md).LoadImage** 方法获取的 **[Image](image.zh.md)** 对象。
</td></tr><tr><td>
label</td><td>

*string* 或  
*object:***[Image](image.zh.md)**</td><td>

设置或查询控件的标签或标题。并非所有控件都有标签 - 这不会对没有标签的控件（如 *列表视图*）产生影响。

请注意，对于 *组合框* 控件，此属性仅对可编辑组合框有效 - 也就是说，您可以键入自己的文本。您可以使用此属性来设置或查询可编辑文本的当前值。

对于设置为“图像”模式的静态控件，您还可以提供从 **[DOpus](dopus.zh.md).LoadImage** 或 **[Script](script.zh.md).LoadImage** 方法获取的 **[Image](image.zh.md)** 对象。这与使用 `image` 属性相同。

对于 *标签页* 控件，您可以通过指定索引来设置或查询各个标签页的标签；例如，`Control.label(0)` 将引用第一个标签页的标签。
</td></tr><tr><td>
mode</td><td>

*string*</td><td>

对于 *列表视图* 控件，允许您更改或查询当前视图模式。有效值为 **icon**、**details**、**smallicon**、**list**。
</td></tr><tr><td>
readonly</td><td>

*bool*</td><td>

设置或查询 *编辑* 控件的 *只读* 状态。
</td></tr><tr><td>
redraw</td><td>

*bool*</td><td>

设置或查询控件的重绘状态。某些控件允许您关闭重绘，以便在进行多个更改时不会出现可见的闪烁（例如，在 *列表视图* 中添加大量项目）。设置为 **False** 以关闭重绘，或设置为 **True** 以在更改控件后重新打开重绘。
</td></tr><tr><td>
rotate</td><td>

*int*</td><td>

对于设置为“图像”模式的 *静态文本* 控件，您可以设置此属性以旋转显示的图像。提供的值是从图像初始方向旋转的度数。
</td></tr><tr><td>
style</td><td>

*string*</td><td>

设置或查询用于显示此控件标签的字体样式。字符串包含零个或多个字符；有效字符为 **b** 表示粗体，**i** 表示斜体。

目前仅支持 *静态文本* 控件的此属性。
</td></tr><tr><td>
textbg</td><td>

*string*</td><td>

设置或查询用于此控件文本背景（填充）的颜色。格式为 *\#RRGGBB*（十六进制）或 *RRR,GGG,BBB*（十进制）。

目前仅支持 *列表视图* 控件的此属性。
</td></tr><tr><td>
title</td><td>

*string* 或  
*object:***[Image](image.zh.md)**</td><td>

**label** 属性的替代名称。术语 **title** 用于对话框编辑器和 XML 资源中，也可以在这里用作方便的术语。
</td></tr><tr><td>
value</td><td>

*string* 或  
*bool* 或  
*int* 或  
*object:***[DialogListItem](dialoglistitem.zh.md)** 或  
*object:***[Vector](vector.zh.md)**</td><td>

设置或查询控件的值。此属性的含义取决于控件的类型：

- **编辑控件**: 返回或接受表示编辑控件当前内容的字符串。
- **复选框**: 对于简单的开/关复选框，返回或接受一个 *bool* - **True** 表示选中，**False** 表示未选中。对于三态复选框，返回或接受一个 *int* - **0** 表示未选中，**1** 表示选中，**2** 表示不确定状态。
- **单选按钮**: 返回或接受一个 *bool* - **True** 表示选中，**False** 表示未选中。
- **标签页**: 返回或接受一个 *int*，表示标签页控件中当前选中的页面。
- **列表框 / 组合框 / 列表视图**: 返回或接受一个 **[DialogListItem](dialoglistitem.zh.md)**，表示选中的项目。设置值时，它也接受一个 *int*，表示选定项目的 0 索引位置。
- **调色板控件**: 返回当前颜色值。如果调色板按钮的复选框已禁用，则颜色字符串前缀为 `!` 字符。您可以以这种方式设置颜色。您也可以将值设置为“enable”或“disable”来更改复选框状态，而不会影响颜色。

请注意，对于多选 *列表框* 或 *列表视图*，此值将返回一个 **[Vector](vector.zh.md)**，其中包含 [DialogListItem](dialoglistitem.zh.md) 对象，表示当前选中的所有项目。
</td></tr><tr><td>
visible</td><td>

*bool*</td><td>

设置或查询控件的可见状态。如果控件可见，则返回 **True**，如果隐藏，则返回 **False**。您可以设置此属性以隐藏或显示控件。
</td></tr><tr><td>
x</td><td>

*int*</td><td>
设置或查询控件的左（x）位置，以像素为单位。
</td></tr><tr><td>
y</td><td>

*int *</td><td>
设置或查询控件的顶部（y）位置，以像素为单位。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddGroup</td><td>

\<string:name\>  
\<int:id\>  
\[\<string:flags\>\]</td><td>

*int*</td><td>

向 *列表视图* 控件添加一个新组。您可以选择将添加到列表的项目放在组中。每个组必须具有唯一的 ID。

可选的标志为“c”（组可折叠）和“d”（组最初处于折叠状态）。例如，**AddGroup("Unimportant", 100, "cd")** 将添加一个名为 *Unimportant* 的组，该组最初是折叠的。
</td></tr><tr><td>
AddItem</td><td>

\<string:name\>  
\[\<int:value\>\]  
\[\<int:groupid\>\]

或

\<object:item\></td><td>

*int*</td><td>

向控件（*列表框*、*组合框* 或 *列表视图*）添加一个新项目。第一个参数是项目的名称，可选的第二个参数是与项目关联的数据值。

在向分组的 *列表视图* 添加项目时，可选的第三个参数提供要向其添加项目的组的 ID（在这种情况下必须提供第二个参数，如果不需要值，则可以将其设置为 0）。

该项目将添加到列表的末尾。

您还可以传递从另一个控件获取的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

返回值指示新项目的列表位置。

如果您要添加到列表视图控件并需要添加具有多列的项目，您可以执行以下操作（JScript）：

    var i = listview.AddItem("This is col 1");
    listview.GetItemAt(i).subitems(0) = "This is col 2";
    listview.GetItemAt(i).subitems(1) = "This is col 3";
</td></tr><tr><td>
AutoSize</td><td>

\[\<bool:height\>\]</td><td>

*bool*</td><td>

自动调整控件大小，如果控件类型支持自动调整大小。如果控件已自动调整大小，则返回 **True**。

如果可选的 *height* 参数设置为 true，则控件将垂直和水平自动调整大小。
</td></tr><tr><td>
DeselectItem</td><td>

\<int:position\>

或

\<object:item\></td><td>

*int*</td><td>

此方法主要用于多选 *列表框* 和 *列表视图* 控件。它允许您取消选择控件中的单个项目，同时保留其它项目被选中（或不受影响）。

您可以指定要选择的项目的索引（0 表示第一个项目，1 表示第二个项目，依此类推），或者指定从 **GetItemAt** 或 **GetItemByName** 方法获取的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

您还可以指定 **-1** 以取消选择列表框中的所有项目。
</td></tr><tr><td>
EnableGroupView</td><td>

\<bool:enable\></td><td>
none</td><td>

仅适用于 *列表视图* 控件。默认情况下，组视图处于关闭状态；在使用 **AddGroup** 方法添加组后，使用 **EnableGroupView** 打开组视图。
</td></tr><tr><td>
GetGroupById</td><td>

\<int:id\></td><td>

object:**[DialogListGroup](dialoglistgroup.zh.md)**</td><td>

返回一个 **[DialogListGroup](dialoglistgroup.zh.md)** 对象，表示您之前使用 **AddGroup** 方法添加到 *列表视图* 控件的具有指定 ID 的组。
</td></tr><tr><td>
GetItemAt</td><td>

\<int:position\></td><td>

object:**[DialogListItem](dialoglistitem.zh.md)**</td><td>

返回一个 **[DialogListItem](dialoglistitem.zh.md)** 对象，表示控件中指定索引位置的项目（*列表框*、*组合框* 或 *列表视图*）。项目 0 表示列表中的第一个项目，项目 1 表示第二个项目，依此类推。
</td></tr><tr><td>

GetItemByLabel  
GetItemByName</td><td>

\<string:name\></td><td>

object:**[DialogListItem](dialoglistitem.zh.md)**</td><td>

返回一个 **[DialogListItem](dialoglistitem.zh.md)** 对象，表示控件中具有指定名称的项目（*列表框、组合框或列表视图*）。此方法有两个名称（...*Label* 和 ...*Name*），出于历史原因，您可以互换使用任一方法名称）。
</td></tr><tr><td>
InsertItemAt</td><td>

\<int:position\>  
\<string:name\>  
\[\<int:value\>\]  
\[\<int:groupid\>\]

或

\<int:position\>  
\<object:item\></td><td>

*int*</td><td>

在控件（*列表框、组合框或列表视图*）中插入一个新项目。第一个参数是要插入项目的位置（0 表示列表开头，1 表示第二个位置，依此类推）。第二个参数是项目的名称，可选的第三个参数是与项目关联的数据值。

在向分组的 *列表视图* 添加项目时，可选的第四个参数提供要向其添加项目的组的 ID（在这种情况下必须提供第三个参数，如果不需要值，则可以将其设置为 0）。

除了 *name* 和 *value* 之外，您还可以传递从另一个控件获取的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

返回值指示新项目的列表位置。
</td></tr><tr><td>
MoveItem</td><td>

\<int:position\>  
or  
\<object:item\>  
\<int:newposition\></td><td>

*int*</td><td>

将现有项目移动到新位置（*列表框*、*组合框* 或 *列表视图*）。第一个参数是要移动的项目（您可以传递其索引或 **[DialogListItem](dialoglistitem.zh.md)** 对象），第二个参数是项目要移动到的新位置。

返回值指示已移动项目的列表位置。
</td></tr><tr><td>
RemoveGroup</td><td>

\<int:id\></td><td>
none</td><td>

从 *列表视图* 控件中删除指定的组。
</td></tr><tr><td>
RemoveItem</td><td>

\<int:position\>  
or  
\<object:item\></td><td>
none</td><td>

从控件（*列表框、组合框或列表视图*）中删除一个项目。您可以提供要删除项目的索引（0 表示第一个项目，1 表示第二个项目，依此类推），或者提供从 **GetItemAt** 或 **GetItemByName** 方法获取的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

您还可以指定 **-1** 以完全清除控件的内容，一次性删除所有项目。
</td></tr><tr><td>
SelectItem</td><td>

\<int:position\>  
or  
\<object:item\>  
or   
\<string:tab\></td><td>

*int*</td><td>

在控件中选择一个项目。对于 *列表框、组合框或列表视图*，您可以指定要选择的项目的索引（0 表示第一个项目，1 表示第二个项目，依此类推），或者提供从 **GetItemAt** 或 **GetItemByName** 方法获取的 **[DialogListItem](dialoglistitem.zh.md)** 对象。

对于多选 *列表框* 或 *列表视图*，您还可以指定 **-1** 以选择控件中的所有项目。

对于 *标签页* 控件，您可以通过指定要显示的页面名称（即子对话框的名称）来更改可见的页面。

返回值指示新的选中索引。
</td></tr><tr><td>
SelectRange</td><td>

\<int:start\>  
\<int:end\>

或

\<object:item1\>  
\<object:item2\></td><td>

object:**[Vector](vector.zh.md)**</td><td>

在 *编辑控件*（或 *组合框* 控件中的编辑字段）中选择文本。这两个参数表示所需选择的开始和结束位置。要选择整个内容，请将 **0** 用于开始，将 **-1** 用于结束。

返回值是一个 **[Vector](vector.zh.md)**，它有两个成员，提供选择的当前开始和结束位置。要查询范围而不更改它，只需在不带任何参数的情况下调用 **SelectRange** 方法即可。

在 *列表框* 或 *列表视图* 控件中，此方法会选择一系列项目。
</td></tr><tr><td>
SetFont</td><td>

\<int:id\></td><td>
none</td><td>

将控件使用的字体设置为指定的字体。*id* 参数必须来自对 **[Dialog](dialog.zh.md).CreateFont** 的先前调用。您可以使用 0 将字体重置为默认值。
</td></tr><tr><td>
SetItemWidth</td><td>

\<int:width\></td><td>
none</td><td>

设置设置为 **list** 或 **smallicon** 模式的列表视图控件中项目的宽度（以像素为单位）。指定 **-1** 以自动调整项目大小。
</td></tr><tr><td>
SetPos</td><td>

\<int:x\>  
\<int:y\></td><td>
none</td><td>
设置此控件的位置。x 和 y 坐标以像素为单位。
</td></tr><tr><td>
SetPosAndSize</td><td>

\<int:x\>  
\<int:y\>  
\<int:cx\>  
\<int:cy\></td><td>
none</td><td>
以单个操作设置控件的位置和大小。所有坐标均以像素为单位。
</td></tr><tr><td>
SetSize</td><td>

\<int:cx\>  
\<int:cy\></td><td>
none</td><td>
设置此控件的大小。cx（宽度）和 cy（高度）值以像素为单位。
</td></tr></tbody>
</table>