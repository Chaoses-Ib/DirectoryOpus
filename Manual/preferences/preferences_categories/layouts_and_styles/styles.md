# Styles

This page lets you create and edit [Lister styles](/Manual/basic_concepts/the_lister/styles.md). A style is a pre-defined configuration that can be applied to an existing Lister. For example, you can define a style that opens the viewer pane and the metadata pane, and closes the folder tree all in one operation. You can switch between styles using the *Lister* drop-down menu on the default toolbar.

Use the toolbar buttons above the list to create and manage styles. Double-click an existing style, or select it and click the **Edit** button to edit it.

##### Edit Lister Style

Creating or editing a style brings up the **Edit Lister Style** dialog.

- **Name**: Edit the name for the style.
- **Description**: Lets you assign a description to a style. If you don't assign a description Opus will show a default one based on the settings in the style.

Below these fields are a number of checkboxes and drop-downs that let you define exactly which Lister elements the style affects. If an item's checkbox is turned off, that element in the Lister will be completely unaffected by the style. If the checkbox is on, the setting for that element will be used when the style is applied. The elements that a style can effect are:

- **File Display**: The style can force the Lister into [single or dual-display](/Manual/basic_concepts/source_and_destination.md) modes. The drop-down lets you select Single or Dual in either horizontal or vertical layout. You can also choose to set the lister into dual display with the [Navigation Lock](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.md) automatically activated (represented by the ![](/Manual/images/media/style_navlock.png) icons in the drop-down list).
- **Folder Tree**: You can make the style turn the [folder tree](/Manual/basic_concepts/the_lister/navigation/folder_tree.md) off or on. You can also set the style to turn dual folder trees on if the Lister is in dual-display mode.
- **Viewer Pane**: The style can turn the [Viewer Pane](/Manual/basic_concepts/the_lister/viewer_pane.md) off or on in either horizontal or vertical orientations.
- **Metadata Pane**: You can turn the [Metadata Pane](/Manual/basic_concepts/the_lister/metadata_pane.md) either off or on in either horizontal or vertical orientations.
- **Toolbar**: To have the style change which toolbars are displayed, turn this on and select an individual toolbar or a **[toolbar set](../toolbars/toolbar_sets.md)**.
- **Utility Panel**: The style can turn the [Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md) off or on. If turning it on you can choose which mode it opens in - [Find](/Manual/basic_concepts/searching_and_filtering/find_files/README.md), [Synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) or [Duplicates](/Manual/additional_functionality/duplicate_file_finder.md).
- **Status Bar**: The style can turn the Lister's [status bar](/Manual/basic_concepts/the_lister/status_bar.md) on or off.
- **Format Lock**: The style can turn the [Format Lock](/Manual/basic_concepts/folder_options/locking_the_format.md) on or off.
- **Filmstrip**: This option puts the Lister into a special mode with the Viewer Pane turned on, and a single scrollable row of thumbnails shown in a single file display.

##### File display configuration

Below the options for the Lister elements are additional options that let you configure the folder, folder format and tabs that the style displays. If these options are turned off then the style will only reconfigure the Lister - it won't change what folder the Lister is currently showing - but you can also define a style that reads a new folder, opens a set of tabs, etc.

These options are configured for the **Left File Display** and **Right File Display** separately. If the Lister is not in dual-display mode then only the options on the **Left File Display tab** are used.

- **Tab Group**: Makes the style open a folder tab group. The drop-down displays a list of all tab groups configured on the **[Folder Tabs / Tab Groups](../folder_tabs/groups.md)** Preferences page. Selecting a tab group overrides all of the subsequent options.
- **Close existing folder tabs**: This option makes the style close all existing tabs before opening the new tabs defined by the style. If turned off, any tabs defined here will be added to the existing tabs in the file display.
- **View Mode**: The style can change the [view mode](/Manual/basic_concepts/the_lister/view_modes.md) in the file display. You can select any of the standard view modes (Details, List, etc) from the drop-down, as well as Auto. Auto is a special mode that means "reset the view mode to what would normally be the default for the folder shown". The [Folder Formats](/Manual/basic_concepts/folder_options/folder_formats.md) system will be consulted to determine the appropriate view mode for the displayed folder.
- **Format**: The style can define a folder format that is applied either to the current folder, or (if **Folder** , below, is activated) the new folder after it is read.
- **Flat View**: The style can turn [Flat View](/Manual/basic_concepts/flat_view.md) off, or turn if on in any of its various modes.
- **Folder**: The style can define a new folder to read into the file display when the style is activated.
