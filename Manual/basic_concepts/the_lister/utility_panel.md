# Utility Panel

The Utility Panel is a multi-purpose panel that appears at the bottom of the Lister whenever certain functions are activated. It acts as a container for several different functions - various tools and log files are displayed that way.

When the utility panel is displayed, you can switch between its various modes using the dropdown in the title bar.

![](/Manual/images/media/13/utility_pane_dropdown.png)

### Tools

These are all accessed from the **Tools** menu:

- [Find Files](../searching_and_filtering/find_files/README.md): Lets you search your computer for files and folders.
- [Synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md): Synchronize the contents of two different folders.
- [Find Duplicate Files](/Manual/additional_functionality/duplicate_file_finder.md): Search your computer for any duplicated files (or for duplicates of a specific file).

### Logs

These are all accessed from the **Help / Logs** menu.

- **FTP Log**: Displays [FTP](/Manual/ftp/README.md) site activity.
- **File Log**: Displays a [log of file actions](/Manual/file_operations/tracking_and_undoing_file_operations.md) (files copied, deleted, renamed, etc). You can configure the file log from the [File Operations / Logging](/Manual/preferences/preferences_categories/file_operations/logging.md) Preferences page.
- **Undo Log**: Displays the most recent file actions that can be [undone](/Manual/file_operations/tracking_and_undoing_file_operations.md) (e.g. if a file has been deleted to the recycle bin, you can recover the file).
- **Email Log**: Displays a log of any [outgoing email](/Manual/preferences/preferences_categories/internet/email.md) that Opus has sent.
- **Script Log**: Displays output from [scripts](/Manual/scripting/README.md) and [the evaluator](/Manual/evaluator/README.md).

### Shrinking the panel

The panel has a button in the top-right corner which shrinks (collapses) it down to just its title bar - this can be useful if, for example, you're running a long find operation and want to do other work while you're waiting.

![](/Manual/images/media/13/utilpane_shrink.png)

Right-click the shrink button to show a context menu which lets you select whether the panel should be automatically shrunk when an operation starts. You can choose this separately for find, synchronize and find duplicates.
