# Columns

![](/Manual/images/media/13/folder_format_columns.png)

The **Columns** tab of the Folder Options dialog lets you configure which information fields (columns) are displayed for the folder when the file display is in Details or Power mode. The selection of columns also has an impact on other display modes like Thumbnails - even if the columns aren't displayed, you can only sort by columns that have been enabled.

The available columns are grouped into a number of categories - you can use the filter field at the bottom of the column list to quickly find a column by name.

##### Adding and removing columns

The fields that aren't currently enabled appear in the list on the left, and the enabled fields are shown in the list on the right. To move a field from one list to another you can double-click it, drag and drop it, or use the left and right arrow buttons between the two lists.

In the list on the right, you can change the order the columns will appear in the file display by drag and drop or using the up and down arrow buttons. You can also re-order columns in the file display itself by dragging the column headers around.

##### Auto-sizing columns

You can tell Opus to auto-size all columns, or specify the widths of individual columns.

Turn on the **Auto-size all columns in Details and Power modes** option at the bottom of the tab to auto-size all columns.

When auto-size is on, the field list on the right will show *Auto* grayed out for each field, to indicate that option is in effect. Editing an individual column's width will automatically turn off the **Auto-size all columns** option.

##### Controlling column width

The **Width** column in the fields list lets you specify the width for individual columns. 

Click the **Width** field of one of the displayed columns to change its width. You can type in a fixed pixel width, or click the drop-down button to select various automatic sizing options:

![](/Manual/images/media/13/folder_format_width.png)

- **Auto**: Automatically size this column. This has the same effect as the *Automatically size all columns* option at the bottom of the dialog, but lets you apply it on a per-column basis.

- **Expand**: Automatically sizes the column the same as **Auto**. The difference is the widths of **Expand** columns are ignored in the calculation of **Fill** columns (see below), and columns set to **Expand** will go off the right hand side of the file display rather than making **Collapse** columns start to collapse.

- **Collapse**: Automatically sizes the column, but its width is able to collapse (down to zero width if necessary) to allow other fields to fit without horizontal scrollbars appearing. For example, you might want the *Description* column displayed, but not have it force other fields off the edge of the file display. Setting it to **Collapse** means it will only appear if there’s space for it.

- **Fill**: Columns set to fill will be automatically sized to fill any available horizontal space in the file display. If there is more than one **Fill** column they divide the available space between them. Columns set to **Fill** can potentially end up wider than they need to be (contrast with **Auto** + **Fill** described below).

##### Minimum and Maximum widths

Columns that are set to automatically size (**Auto**, **Expand** or **Collapse**) can also have a minimum and maximum width set using the **Min** and **Max** fields.

![](/Manual/images/media/13/folder_format_width_set.png)

You can enter a maximum size in pixels. For a column set to **Auto** width you can also choose **Fill** for the maximum, which makes it auto-size up to but not beyond the width of the file display (to avoid horizontal scrolling), but unlike setting **Fill** for the width it won’t auto-size larger than it needs to be.

##### Setting the freeze point

The **Freeze** field lets you mark the point up to which columns are [frozen](/Manual/basic_concepts/folder_options/folder_options_dialog/columns/frozen_columns.md). Simply click in the **Freeze** column to set the freeze point - click again to clear it.

##### Selecting the sort columns

The **Sort** column indicates which field the list will be sorted by. If a single checkmark is shown, there is only one sort field (in the screenshot above, we're sorting by *Date modified*). To change the sort field, single click in column on the desired field.

To assign multiple sort fields, click on the first field as normal, then hold either the <kbd>Ctrl</kbd> or <kbd>Shift</kbd> keys and click on the second field, then the third, and so on. If you <kbd>Ctrl</kbd> or <kbd>Shift</kbd> click a field that's already sorted, the direction of the sort for that field only is changed - so you can for example sort by size in one direction and date in the other.

##### Other column options

- **Auto-size all columns in Details and Power modes**: This option causes column widths in details and power mode to be automatically sized to fit their contents. Instead of using this option, which affects all columns, you can also configure this on a per-column basis using the **Width** field in the column list above.
- **Hide file extension in Filename column**: This does just what it says - you might want to enable this if you have added the separate *Extension* column (or if you just hate file extensions!)
- **Include columns from other matching formats**: This option is only present when [editing a saved Folder Format via Preferences](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md). When you change to a folder which matches the format being edited, Opus will continue looking for other folder formats which also match the folder. Any columns that those other formats specify will be added as well.
  For example, if you change to `C:\Photos` you might have a format which explicitly matches the `C:\Photos` path and will be the main format Opus uses to set up how the folder is displayed. If the **Include columns...** checkbox is on in the main format, Opus will then look through the rest of the format list and might find that the **Images** [content type](../content_types.md) format also matches the folder, and specifies some additional columns not in the main format, which will be added to those displayed in the lister. 

- **Reverse Index column**: The *Index* column displays each item's index in the list (from 1 to however many items are in the list). By default the first item is \#1 and the number increases down the list. Turning on the **Reverse** option count puts the last index number at the top, and the number decreases down the list until reaching \#1 at the bottom.
