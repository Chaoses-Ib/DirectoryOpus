# Folder Tab Groups

Folder Tab Groups are sets of predefined tabs (folders) that can be opened in one operation. For example, you might have a set of work folders for a particular project that you always need quick access to. You could define a tab group that opens all the folders in folder tabs, and then when you're ready to work on that project, you only need to select the group in order to open all those folders at once.

![](/Manual/images/media/tab_groups.png) 

Use the toolbar buttons to configure tab groups. The buttons are ![](/Manual/images/media/favorites_-_add.png) (add a group), ![](/Manual/images/media/favorites_-_folder.png) (add a folder - useful for categorizing large numbers of groups), ![](/Manual/images/media/filters_-_duplicate.png) (duplicate an existing group), ![](/Manual/images/media/filters_-_rename.png) (rename a group), ![](/Manual/images/media/favorties_-_edit.png) (edit a group), ![](/Manual/images/media/favorites_-_delete.png) (delete a group) and ![](/Manual/images/media/layouts_mark_hidden.png) (mark as hidden, to stop it appearing in tab group lists outside of this Preferences page). If you click on a tab group in the list at the top, the tabs defined in that group will be previewed at the bottom of the window.

To organize tab groups into folders, use the ![](/Manual/images/media/favorites_-_folder.png) button to create a folder. You can then create tab groups in that folder, or use drag-and-drop to move existing groups into that folder.

To edit a tab group, select it and click the ![](/Manual/images/media/favorties_-_edit.png) button, or double-click it. The *Edit Tab Group* dialog will be displayed.

![](/Manual/images/media/edit_tab_group.png) 

The **Name** field lets you modify the tab group name, and the **Description** field lets you assign your own description to the group.

Each entry in the **Tabs** list represents a tab, or more specifically, a folder that will be opened in a tab. Use the toolbar buttons above the list to configure the tabs:  ![](/Manual/images/media/favorites_-_folder.png) (add a folder tab), ![](/Manual/images/media/tabs_-_edit.png) (edit an existing folder tab), ![](/Manual/images/media/favorties_-_edit.png) (edit the folder format for the tab), ![](/Manual/images/media/favorites_-_delete.png) (delete a tab), ![](/Manual/images/media/favorites_-_up.png) (move a tab up the list), ![](/Manual/images/media/favorites_-_down.png) (move a tab down the list), ![](/Manual/images/media/tabs_-_make_default.png) (set initial tab), ![](/Manual/images/media/tabs_-_lock.png) (set tab as locked), ![](/Manual/images/media/tab_chains.png) (set tab as linked) and ![](/Manual/images/media/tab_change_sides.png) (change sides).

- You can assign any label you like to a tab - it doesn't have to have the name of the folder displayed on it. Use ![](/Manual/images/media/tabs_-_edit.png) to assign a label to a tab (you can also use this button to change the folder for an existing tab). You can use several special "tokens" to insert information in the tab label:

**%P** - full path of the current folder  
**%N** - name of the current folder  
**%R** - drive root of the current folder  
\* Each tab has a [Folder Format](/Manual/basic_concepts/folder_options/folder_formats.md) specified for it. Note that this format is saved with the tab itself and so overrides the normal folder format system for the folder - for example, changing the format for a folder through the Folder Formats page will not affect that folder when it is saved in a tab group. Use the ![](/Manual/images/media/favorties_-_edit.png) button to edit the format for a tab.

- The arrow buttons let you move tabs up and down the list.  The top-to-bottom order of the list represents the left-to-right order of tabs in the file display.
- Each tab group can have one tab that is designated the active tab - this is the tab that will be initially selected when the group is opened. Use ![](/Manual/images/media/tabs_-_make_default.png) to set the active tab. The tab set as active is displayed in bold text.

When the **Define tabs on specific sides of a dual-display Lister** option is turned on, the tab group can define tabs that open in the left file display separately from those that open in the right. Selecting such a group will automatically put the Lister into dual-display mode if needed. When specific sides is enabled, the ![](/Manual/images/media/tab_change_sides.png) button switches the selected tab from one side to the other.

Folder Tabs can optionally be set to one of several different locked states. A padlock symbol will be displayed to the left of the tab to indicate it is locked. Use the ![](/Manual/images/media/tabs_-_lock.png) drop-down on the toolbar to set the lock mode for a tab. The different lock modes are:

- **Unlocked**: The tab is not locked, meaning you can freely navigate away from the initial folder.
- **![](/Manual/images/media/tab_-_locked.png) Locked**: The tab is locked. Attempts to navigate away from the initial folder will cause a new tab to open, leaving the original tab unchanged.
- **![](/Manual/images/media/tab_-_allow.png) Locked (allow folder changes)**: The tab is locked, but you can navigate away from the initial folder. If you click on the tab when it is already the active tab, the original folder will be restored. You can have the original folder restored as soon as you change to another tab via a setting in [Folder Tab Options](folder_tab_options.md). (You can also run **Go TABSELECT=home** to restore the folder via button or hotkey.)
- **![](/Manual/images/media/tab_-_reuse.png) Locked (reuse unlocked tab)**: The tab is locked. Attempts to navigate away from the initial folder will reuse an existing unlocked tab if one exists, otherwise a new tab will be opened.

Locked tabs may be protected against accidental closure via a setting in [Folder Tab Options](folder_tab_options.md). This will block most methods of closing individual locked tabs, and also hides their close buttons. This does not generally affect things which close multiple tabs, such as closing the entire window, closing the dual file display, or loading a new tab group, unless otherwise noted.

When the **Define tabs on specific sides** option is on, a tab on one side of the Lister can be linked to a tab on the other side. Linked tabs are indicated, as in the above screenshot, with an icon (![](/Manual/images/media/linked_tab.png)). The ![](/Manual/images/media/tab_chains.png) drop-down on the toolbar is used to link and unlink tabs. When two tabs are linked, selecting one in the Lister to make it active automatically activates the linked tab too. You can also link tabs in Navigation Lock mode, using the **Navigation Lock** option in the drop-down. When tabs are linked in Navigation Lock mode, the destination tab will automatically follow the source tab whenever the folder changes. (See the **[Tabs](/Manual/basic_concepts/the_lister/tabs/RAEDME.md)** page for more information.)

If the **Close existing folder tabs when opening this group** option is enabled, then when the tab group is opened in a file display, all existing tabs will be closed. If this option is off then the tabs defined by the group will be added to any existing tabs.
