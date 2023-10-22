# Advanced Selection

The **Select Files** dialog has two modes; *simple* and *advanced*. It is accessed with the **Edit / Select by Pattern** command. The dialog remembers which mode it was last used in and will open in that mode the next time it is used; you can switch modes using the **Advanced** or **Simple** button at the bottom of the dialog.

![](/Manual/images/media/select_files_-_advanced.png) 

The **Advanced Selection** dialog is built upon the file filter control. It lets you select files by building up complex filters that can compare files and folders against many different attributes. Please see the section on [Filtered Operations](/Manual/file_operations/copying_moving_and_deleting_files/filtered_operations/RAEDME.md) for a full description of the filter system. The above example shows a filter that would select all files that end in **.jpg** that were modified within the past week.

At the top of the dialog, the **Action** drop-down lets you choose the action to perform:

- **Select matching items**: Any files and folders that match the defined filter will be selected.
- **Deselect matching items**: Any files and folders that match the filter will be deselected. This lets you perform a simple "not" operation - you could first use the **Edit / Select All** command to select all files in the folder, and then use this action to deselect files based on the filter.
- **Hide matching items**: Any files and folders that match the filter will be removed from the display

The **Hide items that don't match** option can be used in conjunction with both the **Select** and **Deselect** actions (it doesn't make much sense to use it with the **Hide** action). If this option is enabled, items that don't match the filter will be removed from the display altogether.

When items are removed from the display (hidden) by the use of this function, they can be brought back in two ways:

- The easiest way is to simply refresh the folder listing by pressing **F5** (or select **Refresh** from the **Go** menu). This will re-read the folder and redisplay any files you had hidden using the selection function.
- They can also be redisplayed by running an internal command. This command is not present on the default menus or toolbars and so you would need to [create a button](/Manual/customize/creating_your_own_buttons/RAEDME.md) for it or assign it to a [hotkey](/Manual/customize/the_customize_dialog/keys.md). The command you would use for this is **Select NOPATTERN SHOWHIDDEN**. Please see the documentation for the internal **[Select](/Manual/reference/command_reference/internal_commands/select.md)** command for more information on its command line parameters.

Once you have built your filter, or selected one from the drop-down Filter list, click the **OK** button to make the selection. Alternatively, you can click the **Apply** button - this lets you apply the selection without closing the dialog. You could then edit the filter and click **Apply** again if your selection filter didn't quite perform as expected.

Clicking the **Simple** button at the bottom of the dialog takes you back to [simple mode](simple_wildcard_selection.md).
