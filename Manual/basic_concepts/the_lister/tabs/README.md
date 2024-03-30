# Tabs

Directory Opus supports multiple tabs in each file display of a Lister, which means you can have multiple folders open at the same time, and rapidly switch between them to compare the contents, copy or move files from one to the other, or simply to provide quick access to multiple locations.

![](/Manual/images/media/13/tabs_-_make_default_001.png) 

In the above screenshot, two tabs are open - the visible tab shows the **Saved pictures** folder and the non-visible tab (if you were to switch to it) shows the **Pictures** library.

To switch between tabs, simply click on the tab you want to become active. Using the keyboard, you can press <kbd>Ctrl+Left</kbd> and <kbd>Ctrl+Right</kbd> to move from one tab to the next. You can also use the [tab switcher](/Manual/basic_concepts/the_lister/tabs/tab_switcher.md) by pressing <kbd>Ctrl+Tab</kbd>.

Folder tabs are enabled by default - even if only one tab is actually open, the *tab bar* will be displayed at the bottom of the file display (or in a dual-display Lister, at the bottom of each file display). There are a number of options in the **[Folder Tabs](/Manual/preferences/preferences_categories/folder_tabs/README.md)** Preferences category that let you control the folder tabs system. For example, you can configure it so that the tab bar is only displayed when there is more than one tab open, or display the tabs vertically on the left or right of the file display.

##### Opening a new tab

There are a number of ways to open a new tab.

- Click the `+` button shown to the right of the last tab.
- Double-click an empty part of the tab bar (to the right of the `+` button).
- Right-click on a folder and choose **Open in new folder tab** from the context menu.
- Hold the <kbd>Alt</kbd> key down when you double-click a folder to open it in a new tab.

You can configure these from the [Folder Tabs / Folder Tab Bar](/Manual/preferences/preferences_categories/folder_tabs/folder_tab_bar.md) Preferences page (e.g. you can turn off the `+` button, or change which folder opens by default).

The <kbd>Alt</kbd> double-click behavior is configured via the [File Types](/Manual/file_types/README.md) system.

##### Tab colors

Tabs can be colored individually, to make them easier to identify. If you right-click on a folder tab you can select the **Set Tab Color** command from the context menu, which lets you change the color.

![](/Manual/images/media/13/colorful_tabs.png)

##### Tab groups

Folder Tab Groups are sets of predefined tabs (folders) that can be opened in one operation. For example, you might have a set of work folders for a particular project that you always need quick access to. You could define a tab group that opens all the folders in folder tabs, and then when you're ready to work on that project, you only need to select the group in order to open all those folders at once.

Tab groups preserve colors and names you've assigned to your individual tabs.

You can create and manage your tab groups from the [Folder Tabs / Groups](/Manual/preferences/preferences_categories/folder_tabs/groups.md) Preferences page.

##### Default menu commands

![](/Manual/images/media/13/tab_menu.png)

The **Folder / Folder Tabs** menu in the default toolbars contains a number of commands used to control tabs:

- **New Tab for Current**: Opens the current folder in a new tab.
- **New Tab for Parent**: Opens the parent of the current folder in a new tab.
- **New Tabs for Selected**: Opens any selected folders in new tabs (for example, selecting three sub-folders in the current folder and run this command, would result in three new tabs being opened showing those folders).
- **New Tabs for Parents**: Opens the parents of any selected items in new tabs. This is useful in a collection (e.g. Find Results) where the parent of the selected items is not necessarily the current folder.
- **Close Tab**: Closes the current folder tab.
- **Undo Close Tab**: Re-opens the most recently closed folder tab.
- **Manage Tab Groups**: Opens Preferences to the [Tab Groups](/Manual/preferences/preferences_categories/folder_tabs/groups.md) page.
- **Save Tabs**: Save tabs in the current source file display as a tab group.
- **Save Tabs (Both Sides)**: Save tabs from both file displays as a single tab group.

##### Using tabs with the mouse

You can manipulate a folder tab with the mouse in the following ways:

- You can switch between tabs by clicking on them with the left mouse button.
- Double-clicking a tab with the left button will close it (this can be disabled through Preferences).
- You can also click a tab with the middle-mouse button to close it.
- Dragging files from the current folder over another tab will copy or move them to that tab's folder. If you hover over the other tab without releasing the mouse button, that tab will be made active which lets you drop files into sub-folders within that tab.
- You can also drag and drop the folder tabs themselves - this lets you change the order they appear in the file display, and you can also move tabs from one file display to another (or one Lister to another) this way. You can create a duplicate of a tab by holding the <kbd>Ctrl</kbd> key down when you drag and drop the tab. You can also drag a tab out of a Lister and drop it on the desktop to open the folder in a new Lister.
- Normally tabs display the name of the folder they are showing, but if you click the left button on the label of the currently active tab, you are able to assign your own name to the tab. Once a tab has an assigned name it will not change even if you change folders in the tab.
- Right-clicking a tab displays the tab's context menu.

##### Folder tab context menu

![](/Manual/images/media/13/tab_context_menu.png)

Right-click a folder tab to see its context menu. Note that the commands in the menu can vary depending on whether you're in single or dual-display mode. The menu can also be edited via the [Customize](/Manual/customize/README.md) system.

- **Groups**: This sub-menu lets you access any [tab groups](/Manual/basic_concepts/the_lister/tabs/tab_groups.md) you have defined. You can also use this to save the current set of tabs as a new group.
  When selecting a group from this menu you can hold down either the <kbd>Shift</kbd> or the <kbd>Ctrl</kbd> keys to override the tab group's **Close existing Folder Tabs** setting; <kbd>Shift</kbd> means existing tabs will not be closed, <kbd>Ctrl</kbd> means they will.

- **Open New Tab**: Opens a new tab using the settings in Preferences.
- **Duplicate Tab**: Opens a duplicate of the current tab.
- **Duplicate Tab On Right**: Opens a duplicate of the current tab, in the other file display (depending on which file display you access this command from, 'right' may be 'left', 'above' or 'below').
- **Move Tab Right**: Moves the current tab to the other file display.
- **Open Parent As Tab**: Opens the parent of the current folder in a new tab.
- **Open In New Lister**: Opens the tab's folder in a new Lister.
- **Split To Dual Display**: Switches to dual-display mode and splits this tab and any subsequent tabs to the newly opened display.
- **Split To New Lister**: Splits this tab and any subsequent tabs to a new Lister (the existing tabs are closed, a new Lister is opened, and the tabs re-opened in the new Lister).
- **Rename Tab**: Assign your own name to the tab.
- **Set Tab Color**: Assign a color to the tab to make it easier to identify.
- **Lock Tab**: Lock or unlock the tab - see below for more information on locked tabs.
- **Link Tab**: Link or unlink the tab - see below for more information on linked tabs.
- **Close Tabs To Left**: Closes all tabs to the left of this tab. (Does not affect locked tabs unless you hold <kbd>Shift</kbd> when selecting the option.)
- **Close Tabs To Right**: Closes all tabs to the right of this tab. (Locked tabs: As above.)
- **Close All Other Tabs**: Closes all open tabs except for this one. (Locked tabs: As above.)
- **Close Tab**: Closes this tab. (If the tab is locked, and closing locked tabs is disabled, this will only appear if you hold <kbd>Shift</kbd> when opening the menu.)
- **Position**: Change the position of the tab bar.
- **Settings**: Provides a quick link to the tab bar settings in Preferences.

##### Custom tab labels

When you customise a tab's label (by renaming it), you can use several special "tokens" to insert information in the tab label:

|            |                                                                                     |
|------------|-------------------------------------------------------------------------------------|
| **%P**     | full path of the current folder                                                     |
| **%N**     | name of the current folder                                                          |
| **%R**     | drive root of the current folder                                                    |
| **%%%%%%** | insert a literal % character                                                        |
| **%!**     | hide empty blocks within `%!...%!` (see below) |

The `%!` code is special in that it should be used in pairs around the things you want to hide. They will be hidden if all tokens within the block expand to empty values.

Consider `%!(%R) %!%N`, for example. If `%R` expands to nothing and `%P` expands to *My Folder* then you will get just *My Folder* instead of *"() My Folder"*.

If you need something even more custom or dynamic, the labels for individual tabs can also be overridden via commands and scripts.

##### Linked tabs

In a dual-display Lister, a folder tab on one side of the Lister can be linked with a tab on the other side. When two tabs are linked, selecting one in the Lister to make it active automatically activates the linked tab too. Linked tabs are displayed in different colors from unlinked tabs, and you can configure these colors from the **[Directory Opus Colors](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.md)** page in preferences.

You can hold various qualifier keys down to modify the linked state of a tab when you click it:

- <kbd>Ctrl</kbd>-click a tab to link it with the active tab in the other file display (or, if already linked, unlink it).
- <kbd>Ctrl+Shift</kbd>-click a tab to toggle navigation lock mode on or off (see below).
- <kbd>Shift</kbd>-click a tab to override the normal behavior when clicking linked tabs (e.g., its partner tab will not come to the front as normal).

##### Navigation Lock tabs

You can also place linked tabs into Navigation Lock mode, using the \*\*Navigation Lock \*\*option in the context menu. When linked tabs are in this mode the destination tab will always follow the source tab whenever the folder changes, in a similar manner to **[Navigation Lock](dual_display/navigation_lock.md)**.

##### Locked tabs

Folder tabs can be locked in a number of different ways. Primarily, when a tab is locked, it always displays the same folder. It can also be prevented from closing, although this is optional.

To lock a tab, right-click on it and choose a command from the context menu's **Lock Tab** menu. You can also hold <kbd>Alt</kbd> and click a tab to cycle through its lock modes.

The different ways a tab can be locked are:

- **![](/Manual/images/media/13/tab_unlocked.png) Unlocked**: The tab is not locked, meaning you can freely navigate away from the initial folder. 
- **![](/Manual/images/media/13/tab_-_locked.png) Locked**: The tab is locked. Attempts to navigate away from the initial folder (that is, the folder that was displayed when you locked the tab) will cause a new tab to open, leaving the original tab unchanged.
- **![](/Manual/images/media/13/tab_-_allow.png) Locked (allow folder changes)**: The tab is locked, but you can navigate away from the initial folder. If you click on the tab when it is already the active tab, the original folder will be restored. You can have the original folder restored as soon as you change to another tab via a setting in [Folder Tab / Locking](/Manual/preferences/preferences_categories/folder_tabs/locking.md). (You can also run `Go TABSELECT=home` to restore the folder via button or hotkey.)
- **![](/Manual/images/media/13/tab_-_reuse.png) Locked (reuse unlocked tab)**: The tab is locked. Attempts to navigate away from the initial folder will reuse an existing unlocked tab if one exists, otherwise a new tab will be opened.

Locked tabs may be protected against accidental closure via a setting in [Folder Tab / Locking](/Manual/preferences/preferences_categories/folder_tabs/locking.md).

This will block most methods of closing individual locked tabs, and also hides their close buttons. This does not generally affect things which close multiple tabs, such as closing the entire window, closing the dual file display, or loading a new tab group, unless otherwise noted.

You can also use the lock commands to lock or unlock multiple tabs at once; select the commands from the menu while holding down the following keys:

- <kbd>Shift</kbd>: Lock or unlock all tabs
- <kbd>Ctrl</kbd>: Lock or unlock the active tab and all other tabs to the right
- <kbd>Ctrl+Shift</kbd>: Lock or unlock the active tab and all tabs to the left

More:  
[Tab Groups](/Manual/basic_concepts/the_lister/tabs/tab_groups.md)  
