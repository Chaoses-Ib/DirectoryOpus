# Column

The **Column** object represents an information column displayed in a tab (e.g. name, size, attributes, etc). A collection of **Column** objects can be retrieved from the **[Format](format.md).columns** property.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns the name of the column. |
| autosize | *bool* | Returns **True** if the column width is set to *auto*. |
| collapse | *bool* | Returns **True** if the column width is set to *collapse*. |
| expand | *bool* | Returns **True** if the column width is set to *expand*. |
| fill | *bool* | Returns **True** if the column width is set to *fill*. |
| header | *string* | Returns the name of the column as displayed in the Lister column header. |
| label | *string* | Returns the name of the column as displayed in the *Columns* tab in the *Folder Options* dialog. |
| max | *int* or *string* | Returns the maximum width of the column in pixels, or the string "fill" if the maximum is set to *fill*. |
| min | *int* | Returns the minimum width of the column in pixels. |
| name | *string* | Returns the name of the column. |
| reverse | *bool* | Returns **True** if the sort direction of the column is reversed. |
| sort | *int* | Returns the sort order of the column (e.g. 1 for the primary sort field, 2 for the secondary sort field, etc). Returns 0 if the display is not sorted by this column. |
| width | *int* | Returns the current display width of the column in pixels. |

