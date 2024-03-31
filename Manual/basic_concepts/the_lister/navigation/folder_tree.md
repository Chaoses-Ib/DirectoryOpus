# Folder Tree

The Folder Tree is a common user-interface both for navigation and representing the folder hierarchy of the file system.

![](/Manual/images/media/13/tree.png) 

### Relationship to the file display

Normally, there is one file display and one tree. In a dual-display Lister, there are two file displays, but you have the option of using one or two trees. If you have two trees then each file display has its own - but a single tree can be shared by both file displays. In this mode, the tree will change to display the location of the active, or source, file display, and clicking on a folder in the tree will only change the location of the source file display).

### Navigation

Navigating using the tree is as simple as clicking on a folder; the file display attached to that tree will instantly change location to display the contents of the folder you clicked on.

If the folder tree has input focus (i.e. if it is the active user-interface element in the Lister, and keystrokes are directed to it), then it's also possible to navigate with the keyboard using the cursor keys.

### Keyboard interface

The folder tree supports several keyboard commands by default:

- <kbd>Up</kbd> and <kbd>Down</kbd> to move the selection up and down the list
- <kbd>Right</kbd> and <kbd>Left</kbd> to expand/collapse the selected folder
- <kbd>F2</kbd> to rename the selected folder
- <kbd>Del</kbd> to delete the selected folder

Using the [Customize](/Manual/customize/README.md) system it's also possible to program your own [keys](/Manual/customize/the_customize_dialog/keys.md) that work specifically on the folder tree. Some of these are configured by default:

- <kbd>+</kbd> to expand the selected folder on the first press, and on the second press expand all second-level folders below it
- <kbd>-</kbd> performs a similar function for collapse
- <kbd>\*</kbd> to expand all folders
- <kbd>Ctrl+Space</kbd> toggles a folder's pinned state, if pins are enabled in [Preferences](/Manual/preferences/preferences_categories/folder_tree/expand_collapse/pins.md).

### Displaying child folders

The small glyph displayed to the left of each item in the folder tree is known as the *expansion button*. If you're using a different version of Windows or a third-party theme, this may look different to the screenshot above, but in general the glyph has two main states - *open* and *closed*.

In the above screenshot, the **Desktop**, **This PC** and **Local Disk** branches are *open* - the folders have been expanded, and their child folders in the hierarchy are visible. The other branches are closed - their sub-folders are not displayed. The **Logs** and **PerfLogs** branches don't show a glyph at all - this indicates that the folders have no sub-folders, and so can't be expanded.

### Context menu

As in other programs, you can access the context menu for an item in the tree by right-clicking on it. From the keyboard, you can press <kbd>Shift+F10</kbd> to display the context menu for the selected item. Some keyboards also have a dedicated key to the right of the space bar for this.

### Renaming folders

You can use the folder tree to rename folders (those that support being renamed, anyway). This can be activated in several ways:

- If you left-click an item (to select it), you can rename it by clicking it again after the double-click timeout has elapsed (this is referred to as a *slow double-click*).
- If the tree has input focus (e.g. after you click in it) you can rename the selected item by pressing <kbd>F2</kbd>.
- You can right-click on an item and choose **Rename** from the context menu.

Push <kbd>Enter</kbd> to apply the current folder's new name or <kbd>Esc</kbd> to cancel renaming the current folder.

In Opus the rename field has some features not found in Explorer:

- The <kbd>Up</kbd> and <kbd>Down</kbd> let you apply the current folder's new name and start renaming an adjacent folder.
- Various keys can be used to transform the selected text. See the page on [inline rename](/Manual/file_operations/renaming_files/inline_rename.md) for more information.

### Drag and drop

You can copy or move files to folder in the tree using drag and drop. You can also drag folders out of the tree to copy or move (or create shortcuts to) them.

### Folder tree title buttons

The title bar has a number of buttons to help work with the folder tree.

![](/Manual/images/media/13/tree_buttons.png) 

From left to right they are:

- **Locate**: If the currently selected folder has been scrolled out of view, clicking this button will reposition it so that it is as close to the centre of the display as possible.
- **Collapse**: Collapses all folders in the tree except those that lead to the current folder. This is a good way to get the tree back to a manageable state quickly.
- **Presets**: The preset dropdown lets you save and load "tree expansion presets". These remember which folders have been expanded and which are not, and let you restore the tree to a previous expansion state instantly.
- **Close**: This closes the folder tree. To re-open it, select the **Folder Tree** command from the **Lister Configuration** menu (or press <kbd>F8</kbd>).

There's also an option in Preferences to enable a lock button in the title bar. When locked the tree stops following the file display around, and won't change location automatically.

### Path highlighting

The tree can be configured to highlight the path to the currently selected folder as a visual aid. It can make the current selection in the folder tree much more conspicuous. The highlight can be displayed all the time, or only when the tree itself is active.

![](/Manual/images/media/13/tree_path.png)

Additionally, as in the screenshot above, the path to all currently open tabs can optionally be displayed as well. These options are all configured on the **[Folder Tree / Appearance](/Manual/preferences/preferences_categories/folder_tree/appearance.md)** page in Preferences.
