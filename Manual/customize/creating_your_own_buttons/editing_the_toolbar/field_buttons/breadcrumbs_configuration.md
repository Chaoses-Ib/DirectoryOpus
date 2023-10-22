# Breadcrumbs Configuration

You can control the behaviour and appearance of [breadcrumbs location fields](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md) by editing the button definition of the field in [Customize](/Manual/customize/RAEDME.md) mode.

![](/Manual/images/media/edit_breadcrumbs_2.png)

Select **Customize** from the **Settings** menu, and then right-click on the breadcrumbs location field (it will have reverted to a simple frame - see the discussion on [Field Buttons]() for more information on this) and choose **Edit**. The **Args** field in the command editor dialog is used to provide various comma-separated keywords that define the behaviour and appearance of the breadcrumbs field. The available keywords are:

- **dragignoreself**: Blocks drag & drop from the path field to itself. Turn this on to avoid accidents when dragging out of the path field and releasing the mouse button prematurely. Note that, even if this is on, you can still hover over the arrows between path components and drop into the menus that pop-up, should you need to. Whether or not this is on, dragging from one path field to another is always enabled, as is dragging from the file display or other elements to the path field.  
  \* **dragsafetyoff**: Makes it possible to copy or move folders by dragging them from the breadcrumbs field without having to hold a qualifier key. Without this, the drag & drop action defaults to creating shortcuts to folders unless you explicitly override it by holding **Ctrl** to copy or **Shift** to move. The default mode is safer if you primarily drag from breadcrumbs to the folder tab bar to open new tabs for parent folders; if you accidentally drop the folder on the way then it will create a harmless shortcut rather than copy or move the whole parent folder structure.  
  \* **drivelabel**: Displays the drive label along with the drive letter (e.g. *System (C:)* instead of *C:*).

- **driveroot**: Removes the *Computer* branch from the field. So for example, instead of the breadcrumbs trail *Desktop -\> Computer -\> C: -\> Program Files*, you would get *Desktop -\> C: -\> Program Files.*

- **editend**: Moves the initial cursor position to the end of the path string, with none of it selected, when you edit the path. This makes it easier to add a subdirectory or modify the last component of the path. If this is not used, the whole path string will be selected when you start editing the path, making it easier to type a completely new path over the top of it. Whichever you use, you can always push **Ctrl+A** to select the whole path or **End** to go to the end.  
  \* **ftphost:** Used in conjunction with **ftpsitename**, causes the host details (IP address and port) to be displayed for an FTP location as well as the site name.**\\**
- **ftpsitename:** For an FTP site from the address book, this will show the name of the address book entry (site name) rather than URL/IL address of the site. Combine with **ftphost** to show both.  
- **hidedesktopfolders**: Any folders on the desktop will be omitted from the *Desktop* branch drop-down.**\\**
- **hideemptydrives**: Hides empty disk drives from the *Computer* branch drop-down. This overrides the **Show Empty disk drives** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** page in Preferences.  
  \* **hidefavorites**: Does not display your favorite folders in the *Desktop* branch drop-down. This overrides the **Show Favorites** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** page in Preferences.  
  \* **hidehidden**: Forces hidden folders (ones with the **H** attribute but not the **S** attribute) not to be included in the branch drop-down menus. This partially overrides the **Show hidden and system folders** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** Preferences page and the **Global Hide Filter** settings on the [Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md) Preferences page.  
  \* **hidesystem**: Forces protected operating system folders (ones with both the **H** and **S** attributes set) not to be included in the branch drop-down menus. This partially overrides the **Show hidden and system folders** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** Preferences page and the **Global Hide Filter** settings on the [Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md) Preferences page.  
  \* **hotkeymenu**: If there is a hotkey assigned to the Breadcrumbs control, pressing it will open the *Desktop* branch drop-down instead of giving focus to the edit field.  
  \* **mycomputericon**: Displays the *Computer* branch as an icon instead of a label.  
  \* **mycomputerfull**: Enable the display of non-drive folders in the drop-down for the *Computer* folder.  
  \* **noghostpath**: Prevents the field from preserving "ghost" crumbs of your previous location when navigating up the folder tree.  
  \* **noitalicghosts**: Displays ghost crumbs in a normal font rather than in italics.  
  \* **noarchives**: Prevents archives being included in the drop-down menus as if they were folders.  
  \* **nopreservepath**: Specify this keyword if you wish to keep ghost paths when going up a level but prevent them from remaining when you switch into a new directory that has the same folders below it.  
  \* **noselectprevious**: Overrides the "Select previous folder when going up" Preferences option, acting as if it was always off when navigating to the parent of the current folder. (The folder may still be selected for other reasons. e.g. If you go into a folder using double-click and then go back to a cached view of its parent, the view will remember that the folder was selected by the double-click itself.)  
  \* **notheme**: Modifies the look & feel of the breadcrumbs path field. Also slightly affects its height. The breadcrumbs themselves will be drawn without using the current system theme (Windows visual style), and the field background will not fade in and out when active or inactive. As an alternative to the **notheme** keyword, if you instead specify the **Toolbar and menu defaults / Field background** color under **[Preferences / Display / Colors and Fonts](/Manual/preferences/preferences_categories/display/colors_and_fonts.md)**, that will override much of the breadcrumb aesthetics while keeping certain elements of the visual style and re-coloring them according to the other color choices on the same Preferences page. That is often preferable to using **notheme** if you dislike the standard look & feel. If the **Field background** color is not specified, and **notheme** is in use, then the colors used to draw the field come from the **Office 2003-style** settings (a legacy option nowadays) on the **[Toolbars / Appearance](/Manual/preferences/preferences_categories/toolbars/toolbar_appearance.md)** Preferences page.  
  \* **selectprevious**: Overrides the "Select previous folder when going up" Preferences option, acting as if it was always on when navigating to the parent of the current folder. In other words, if you click part of the path to go up a level, the folder you were in before clicking will be selected.  
  \* **showemptydrives**: Shows empty disk drives in the *Computer* branch drop-down. This overrides the **Show Empty disk drives** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** page in Preferences.  
  \* **showfavorites**: Displays your favorite folders in the *Desktop* branch drop-down. This overrides the **Show Favorites** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** page in Preferences.  
  \* **showhidden**: Forces hidden folders (ones with the **H** attribute but not the **S** attribute) to be included in the branch drop-down menus. This partially overrides the **Show hidden and system folders** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** Preferences page and the **Global Hide Filter** settings on the [Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md) Preferences page.  
  \* **showsystem**: Forces protected operating system folders (ones with both the **H** and **S** attributes set) to be included in the branch drop-down menus. This partially overrides the **Show hidden and system folders** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** Preferences page and the **Global Hide Filter** settings on the [Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md) Preferences page.  
  \* **size**: This lets you configure the size of various elements of the breadcrumbs field. This keyword accepts up to five numeric values, each separated with a **+** sign.

The full template for this keyword is **size=***\<arrow width\>***+***\<folder left\>***+***\<folder right\>***+***\<text left\>***+***\<text right\>*.

*\<arrow width\>* is the width of the drop-down button in each path part. *\<folder left\>* and *\<folder right\>* control the left and right spacing of the *Desktop* button (and the *Computer* branch if **mycomputericon** is specified), and *\<text left\>* and *\<text right\>* specify the spacing of the text buttons.

The default values if this keyword is not provided are **size=13+1+4+4+4**. You can specify **0** for a value to indicate the default setting.

The supplied sizes will be automatically scaled to compensate for your system DPI settings. If you want to disable DPI scaling for a size, specify it as a negative value.

The breadcrumbs field also supports the [standard path field](path_field_configuration.md) keywords:

- **left**: The breadcrumbs field will always control the left (or top) file display.
- **right**: The breadcrumbs field will always control the right (or bottom) file display.
- **dest**: The breadcrumbs field will always control the destination file display.
- **focus:** If the breadcrumbs field is configured to control a file display other than the source, adding the **focus** keyword as well will cause the focus to be set to that file display automatically (i.e. that file display will become the new source whenever the folder is changed).

 
