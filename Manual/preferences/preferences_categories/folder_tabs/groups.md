# Groups

Folder Tab Groups are sets of predefined tabs (folders) that can be opened in one operation. For example, you might have a set of work folders for a particular project that you always need quick access to. You could define a tab group that opens all the folders in folder tabs, and then when you're ready to work on that project, you only need to select the group in order to open all those folders at once.

The toolbar buttons above the list let you create and manage your configured tab groups.

To organize tab groups into folders, use the **New Folder** button to create a folder. You can then create tab groups in that folder, or use drag-and-drop to move existing groups into that folder.

The **Mark as hidden** button lets you mark a group as hidden, to stop it appearing in tab groups lists outside of this page - hidden groups can only be accessed using the `Go` command.

To edit a tab group, select it and click the **Edit** button (or double-click it). This shows the *Edit Tab Group* dialog.

### Edit Tab Group dialog

The **Name** field lets you modify the tab group name, and the **Description** field lets you assign your own description to the group. The other options at the top are:

- **Close existing folder tabs when opening this group**: When the tab group is opened in a file display, all existing tabs will be closed. If this option is off then the tabs defined by the group will be added to any existing tabs.
- **Define tabs on specific sides of a dual-display Lister**: The tab group can define tabs that open in the left file display separately from those that open in the right. Selecting such a group will automatically put the Lister into dual-display mode if needed.

Each entry in the list below represents a tab, or more specifically, a folder that will be opened in a tab when the group is loaded. Use the toolbar buttons above the list to configure the tabs in the group. Most of the buttons are self-explanatory; those that aren't so obvious include:

- **Edit Format**: Each tab has a [folder format](/Manual/basic_concepts/folder_options/folder_formats.md) specified for it. Note that this format is saved with the tab itself and so overrides the normal folder format system for the folder - for example, changing the format for a folder through the Folder Formats page will not affect that folder when it is saved in a tab group. The dropdown menu attached to the button lets you copy the format to all other tabs if you want them all the same.
- **Set Active**: Set which tab is initially active when the group is loaded.
- **Change Side**: When the "specific sides" option above is on, this switches the selected tab from one side to the other (e.g. left to right).
- **Locked Tab**: Set tab as [locked](/Manual/basic_concepts/the_lister/tabs/locked_tabs.md).
- **Link Tab**: Set tab as [linked](/Manual/basic_concepts/the_lister/tabs/linked_tabs.md). This is only available if the "specific sides" option is turned on.

You can also use the palette button to the right of **Link Tab** to assign an [edge color](edge_colors.md) to the tab.

### Tab labels

You can assign any label you like to a tab - it doesn't have to have the name of the folder displayed on it. Click the **Edit Tab** button to edit a tab's label (or to change the folder for an existing tab). You can use several special "tokens" to insert information in the tab label:

|        |                                  |
|--------|----------------------------------|
| **%P** | full path of the current folder  |
| **%N** | name of the current folder       |
| **%R** | drive root of the current folder |
