# Column Context Menus

Functions in the column header context menu can use the evaluator like in any other [toolbar or menu](functions/README.md), however in this evaluation context, the following variables are available which are specific to the column header:

<table>
<thead><tr><th>
Variable</th><th>
Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
frozenfields</td><td>

*int*</td><td>
The number of frozen columns.
</td></tr><tr><td>
group</td><td>

*int*</td><td>

ID of the column the file display is grouping by, `-1` if none. You can pass this ID to commands like `Set GROUPBY=x,toggle`.
</td></tr><tr><td>
groupkey</td><td>

*str*</td><td>
Keyword of the column the file display is grouping by.
</td></tr><tr><td>
groupname</td><td>

*str*</td><td>
Name of the column the file display is grouping by.
</td></tr><tr><td>
groupscheme</td><td>

*str*</td><td>
Name of the current grouping scheme (if any).
</td></tr><tr><td>
header</td><td>

*int*</td><td>

ID of the column that was right-clicked, `-1` if none. You can pass this ID to commands like `Set COLUMNSTOGGLE=x`.
</td></tr><tr><td>
headerindex</td><td>

*int*</td><td>
Position of the header item that was right-clicked.
</td></tr><tr><td>
headerinsert</td><td>

*int*</td><td>

Insertion point. Similar to *headerindex*, but +1 if the click was in the right-half of the item.
</td></tr><tr><td>
headeritem</td><td>

*int*</td><td>

Deprecated. The same as *headerinsert*.
</td></tr><tr><td>
headerkey</td><td>

*str*</td><td>
Keyword of the column that was right-clicked.
</td></tr><tr><td>
headername</td><td>

*str*</td><td>
Name of the column that was right-clicked.
</td></tr><tr><td>
path</td><td>

*path*</td><td>
Returns the path shown in the file display.
</td></tr></tbody>
</table>

