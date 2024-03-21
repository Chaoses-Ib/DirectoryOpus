# Folder Sizes

This page lets you control whether or not Opus automatically [calculates folder sizes](/Manual/basic_concepts/folder_sizes.md) when you navigate to a new location. If automatic calculation is disabled you can always use the **Calculate Folder Sizes** command in the Edit menu to trigger a manual calculation.

- **Calculate folder sizes automatically**: When you navigate to a new location, Opus will launch a background thread that calculates the total size of all sub-folders. When this option is on you can choose what type of drives to apply it to.
- **Cache folder sizes when going back and forward in the history**: If turned on, when you use the back and forward buttons to move through the tab's history, folder sizes that have already been calculated will be remembered. If turned off, they'll need to be recalculated every time.
- **Update folder sizes after file operations where possible**: Folder sizes are essentially static - they're calculated once, and the calculated size is then shown until it's recalculated. This means they can become inaccurate if files are created or deleted inside the folder. With this option on, Opus will try to update after file operations to keep the folder size current. Currently this is limited to local and removable disks only.
- **Use Everything to calculate folder sizes where possible**: If [Everything by Voidtools](https://voidtools.com) is installed, Opus can leverage its index to calculate folder sizes much faster than normal.
  - **Calculate automatically even if automatic calculation is otherwise disabled**: If Everything is installed, then a folder's size will be automatically calculated if it's been indexed, even if the other settings on this page would normally mean its size wouldn't be calculated.

##### Per-folder overrides

The list at the bottom lets you override size calculation on per-folder basis. You can add specific folders or use a wildcard string.

For each folder you add to the list you can use the options at the bottom to either enable or disable folder size calculation. Note that this setting applies **within** the specified folder. For example, if you add *C:\Temp* to the list, and set it to **Calculate size**, then navigating to *C:\Temp* would trigger a size calculation for any sub-folders within it. It doesn't mean that *Temp* would have its size calculated if you navigated to *C:\\*.
