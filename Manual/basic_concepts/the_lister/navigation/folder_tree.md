# Folder Tree

The Folder Tree is a common user-interface both for navigation and representing the folder hierarchy of the file system.

![](/Manual/images/media/tree.png) 

The folder tree, while appearing at first as a simple list of folders, is actually quite a versatile control:

- **Navigation**: Navigating using the tree is as simple as clicking on a folder; the file display attached to that tree will instantly change location to display the contents of the folder you clicked on. If the selected folder is already open in another [folder tab](../tabs/RAEDME.md), and the **Switch to existing tab if already open** option is enabled on the **[Folder Tree / Selection Events](/Manual/preferences/preferences_categories/folder_tree/selection_events.md)** page in Preferences, Opus will switch to that tab rather than change the location in the current tab.

(A note on the relationship between folder trees and file displays: normally, there is one file display and one tree. In a dual-display Lister, there are two file displays, but you have the option of using one or two trees. If you have two trees then each file display has its own - but a single tree can be shared by both file displays. In this mode, the tree will change to display the location of the active, or source, file display, and clicking on a folder in the tree will only change the location of the source file display).

If the folder tree has input focus (i.e. if it is the active user-interface element in the Lister, and keystrokes are directed to it), then it's also possible to navigate with the keyboard using the cursor keys.

- **Displaying child folders**: The small glyph displayed to the left of each item in the folder tree is known as the *expansion button*. If you're using a different version of Windows or a third-party theme, this may look different to the screenshot above, but in general the glyph has two main states - **open** and **closed**. In the above screenshot, the **Libraries** and **Pictures** branches are **open** - the folders have been expanded, and their child folders in the hierarchy are visible. The **Documents**, **Music** and **Videos** branches are closed - their sub-folders are not displayed. The **My Pictures** branch doesn't show a glyph at all - this indicates that the folder has no sub-folders, and so can't be expanded.
- **Context menu**: As in other programs, you can access the context menu for an item in the tree by right-clicking on it. From the keyboard, you can press **Shift+F10** to display the context menu for the selected item. Some keyboards also have a dedicated key to the right of the space bar for this.
- **Rename**: You can use the folder tree to rename folders (those that support being renamed, anyway). This can be activated in several ways:
  - If you left-click an item (to select it), you can rename it by clicking it again after the double-click timeout has elapsed (this is referred to as a *slow double-click*).
  - If the tree has input focus (e.g. after you click in it) you can rename the selected item by pressing **F2**.
  - You can right-click on an item and choose **Rename** from the context menu.
  - When renaming a folder in the tree, you can use the up and down **cursor keys** to apply the current folder's new name and start renaming an adjacent folder. When done, push **Return** to apply the current folder's new name or **Esc** to cancel renaming the current folder.
  - When renaming a folder, you can push various hotkeys to transform the selected text: **Ctrl+L** (lower-case all), **Ctrl+U** (upper-case all), **Ctrl+W** (capitalize all words), **Ctrl+P** (capitalize first word), or **Ctrl+.** (replace dots and underscores with spaces; dots with numbers on both sides are left alone; use the key on the main keyboard, not the numeric keypad).

- **Drag and drop**: You can copy or move files to folder in the tree using drag and drop. You can also drag folders out of the tree to copy or move (or create shortcuts to) them.
- **Keyboard shortcuts**: In addition to the well-known **cursor keys**, you can use the following shortcuts to control the folder tree:
  - **Numpad** \* will recursively expand everything below the selected item.
  - **Numpad +** expands the selected item the first time you push it; pushing it again expands the first level of child items (but not the children of those items).
  - **Numpad -** collapses the selected item (the same as **left-arrow**, except it won't go to the parent folder if you push it twice).

In the screenshot above you can see that the Folder Tree's title bar contains three buttons:

- ![](/Manual/images/media/tree_-_zoom.png) **Locate**: If the currently selected folder has been scrolled out of view, clicking this button will reposition it so that it is as close to the centre of the display as possible.
- ![](/Manual/images/media/tree_-_lock.png)  **Lock**: Normally the selection in the folder tree will change automatically as you navigate in the file display, to always reflect the current folder. If you turn the lock button on, the tree will never change selection by itself - the selected item will only change if you specifically select something else.
- ![](/Manual/images/media/tree_-_close.png) **Close**: This closes the folder tree. To re-open it, select the **Folder Tree** command from the **Lister Configuration** menu (or press **F8**).

The tree can be configured to highlight the path to the currently selected folder as a visual aid. It can make the current selection in the folder tree much more conspicuous. The highlight can be displayed all the time, or only when the tree itself is active.

![](/Manual/images/media/tree_path.png)

Additionally, as in the screenshot above, the path to all currently open tabs can optionally be displayed as well. These options are all configured on the **[Folder Tree / Appearance](/Manual/preferences/preferences_categories/folder_tree/folder_tree_appearance.md)** page in Preferences.
