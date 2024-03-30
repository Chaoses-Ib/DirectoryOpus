# Column

The **Column** object represents an information column displayed in a tab (e.g. name, size, attributes, etc). A collection of **Column** objects can be retrieved from the **[Format](format.md).columns** property.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>
Returns the name of the column.
</td></tr><tr><td>
autosize</td><td>

*bool*</td><td>

Returns **True** if the column width is set to *auto*.
</td></tr><tr><td>
collapse</td><td>

*bool*</td><td>

Returns **True** if the column width is set to *collapse*.
</td></tr><tr><td>
expand</td><td>

*bool*</td><td>

Returns **True** if the column width is set to *expand*.
</td></tr><tr><td>
fill</td><td>

*bool*</td><td>

Returns **True** if the column width is set to *fill*.
</td></tr><tr><td>
header</td><td>

*string*</td><td>
Returns the name of the column as displayed in the Lister column header.
</td></tr><tr><td>
label</td><td>

*string*</td><td>

Returns the name of the column as displayed in the *Columns* tab in the *Folder Options* dialog.
</td></tr><tr><td>
max</td><td>

*int* or *string*</td><td>

Returns the maximum width of the column in pixels, or the string "fill" if the maximum is set to *fill*.
</td></tr><tr><td>
min</td><td>

*int*</td><td>
Returns the minimum width of the column in pixels.
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Returns the name of the column.
</td></tr><tr><td>
reverse</td><td>

*bool*</td><td>

Returns **True** if the sort direction of the column is reversed.
</td></tr><tr><td>
sort</td><td>

*int*</td><td>
Returns the sort order of the column (e.g. 1 for the primary sort field, 2 for the secondary sort field, etc). Returns 0 if the display is not sorted by this column.
</td></tr><tr><td>
width</td><td>

*int*</td><td>
Returns the current display width of the column in pixels.
</td></tr></tbody>
</table>

