# Paired Folders

This page lets you configure pairs of folders that Opus treats specially. For example, navigating to one half of a pair can automatically open the other in the opposite file display.

The toolbar buttons above the list let you create and manage your paired folders.

Paired folders can be based on absolute paths or regular expressions. Regular expression pairs are evaluated in the order they appear in the list, and the **Move Up** and **Move Down** buttons can be used to change their order if needed.

When you add or edit a folder pair, the *Paired Folder* dialog is shown.

### Paired Folder editor

You can configure the folders in the pair in two different ways.

- **Absolute paths**: Using this method, you specify two specific folder paths (a **primary** and a **secondary**). This style of pair is bidirectional.
- **Regular expression**: Specify **match** and **replace** patterns. If a folder matches the **match** pattern it becomes the **primary**, and the **replace** pattern is used to generate its pair.

![](/Manual/images/media/13/paired_folder.png)

This shows a simple example that sets up an automatic pair between any folder beneath `C:\Work\Staging` and its equivalent folder beneath `C:\Work\Production`. The regular expression uses a capture group to copy the remainder of the path after `Staging` and appends it to the path for production folders.

The options that control the pair are:

- **Primary folder**: Specify the primary folder as an absolute path (you use aliases here).
- **Secondary folder**: Specify the secondary folder.
- **Match**: Specify the primary folder as a regular expression.
- **Replace**: Specify the replacement pattern to generate the secondary folder.
- **Expand folder aliases**: Folder aliases in the regular expressions will be expanded.
- **If non-existent**: Specifies what to do when the secondary folder doesn't exist.
  - **Go up to first existing parent**: Opus will go up the folder tree until it finds a folder that exists.
  - **Ignore the pair**: The pair is treated as if it doesn't exist.
  - **Use path even if it doesn't exist**: Opus will try to read the path, and show an error if it fails.
- **Apply settings to all sub-folders**: All sub-folders below the primary folder will be treated the same way. This option allows the example shown above to be implemented more simply as:
  - **Primary folder**: `C:\Work\Staging`
  - **Secondary folder**: `C:\Work\Production`
- **Default dual-display folder**: The paired folder will be used as the default location when switching the Lister into dual-display mode.
  - **Always display primary folder at the left/top**: If the secondary folder is the one already open when you switch into dual-display mode, the primary folder will be set as the left/top file display.
  - **Turn on Navigation Lock automatically**: [Navigation Lock](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.md) will be automatically turned on when switching into dual-display mode.
- **Default Navigation Lock target**: Allows Navigation Lock to be turned on even if the Lister is in single display mode. The paired folder will be loaded as the default target automatically.
- **Default Synchronize target**: The [Synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) tool will use the paired folder as the default synchronize target.

At the bottom of the dialog, the **Test folder** field lets you test your pair settings. Enter or browse for a folder path, and if it matches the **Result** field below will show you what the secondary path would be.
