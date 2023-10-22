# Colors and Fonts

This page lets you configure the colors and fonts that are used throughout much of the program. The list of items that can be configured is divided into three categories:

- **File and Folder Colors**: These are the (default - see [Note 1](colors_and_fonts.md#Note1)) colors that are used for the display of files and folders in the File Displays.          
  \* **File display background**: Ok, that's not actually the color for a file or a folder - it's the background color of the file display area. You can also set a different color that's used when a file display is in [destination](/Manual/basic_concepts/source_and_destination.md) mode (either in a single file display Lister or as part of a dual display Lister), also when it's off (i.e. a single file display Lister that isn't either the source or destination). You can also set separate colors for when the [quick filter](/Manual/basic_concepts/searching_and_filtering/filter_bar.md) is active. If you leave the destination or off background colors set to *transparent* the main background color will be used for both source and destination file displays (and similarly, if the 'filtered' colors are set to *transparent* the main colors will be used instead).
  - **File group column**: When the file display is grouped, you have the option of showing the group names as headings between each group or in a column on the side. If you choose to use the group column, this defines its colors.
  - **File group header**: When the file display is grouped, and you opt for group names to be displayed as headings between each group, this defines the text and separator color for the group headings. The glyph colors are used for the icons you click to expand or collapse a group, in display modes which allow collapsing, with the "hot" color used when the mouse is over the glyph.
  - **Files and folders**: The text and background colors for files and folders that don't derive a color from some other setting. You can specify colors for when these items are selected as well as in their unselected state. Using visual styles to draw items and selection boxes may override some of these colors; if this is happening, a clickable message will appear below the last color, and clicking it will take you to the option you can turn off if you don't want this to happen.
  - **Files and folders - Compatibility**, **Compressed**, **Encrypted** and **System**: Optional colors for various types of files that will override the defaults if activated. [Compatibility files](/Manual/basic_concepts/virtual_file_system/compatibility_files.md) are those from "compatibility folders" when Opus displays the contents merged with the main folder (that's a bad explanation, follow the link for a proper discussion of this concept). Compressed files are those with the **C** attribute, encrypted files are those with the **E** attribute, and system files are those with both the **H** and **S** attributes set.
  - **Files and folders - Matched Text**: Colors used to highlight text matches in filenames when using the [Find-as-you-Type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field (and the **[Highlight matches](../file_displays/fayt_and_filter_bar_keys.md)** option is turned on).
  - **Folders - favorites**: Optional colors that are used for any folders you have added to the [Favorites](/Manual/basic_concepts/the_lister/navigation/favorites.md) list.
  - **Synchronize conflicts**: Colors that are used with the Synchronize tool to indicate files which are in conflict.

- **Other Colors**: These are colors used elsewhere in the user interface - they're not related to file displays themselves, but to other parts of the Lister.  
  \* **File display border - Destination**, **Off**, **Source**: Defines the text and fill colors used for the File Display border (the "title" bar displayed at the top of the file display) in each of the [three Lister states](/Manual/basic_concepts/source_and_destination.md).
  - **File display icon**: Defines the color used for the Opus logo icon that is shown in the File Display border, as well as that used for the Lister's window icon. You can define different colors for when the Lister is set as source, destination or off, as well as a separate color for when the Lister is in dual-display mode.
  - **Folder tabs**: Text and background colors for folder tabs, as well as the background color for the bar (empty space) behind the tabs. You can also configure a separate "hot" color for when the mouse is over a tab.
  - **Folder tabs (linked)**: Lets you configure the colors used when folder tabs are linked. You can configure eight separate linked tab colors. Each pair of linked tabs uses the colors in the order they are specified here.
  - **Folder tree**: Text and background colors for items in the folder tree, if not overridden by above colors (see [Note 2](colors_and_fonts.md#Note2)). The glyph colors are used for the icons you click to expand or collapse a branch; the hot glyph color only applies when using visual styles.
  - **Folder tree (destination)**: When a dual-display Lister has two trees, or a single-display Lister with a tree is set as the destination, you can use this to specify different colors for the tree associated with the destination file display.
  - **Graphs - Free Space**: Colors used to draw the free-space graphs in places like the This PC (aka My Computer) folder and the status bar. The "warning" color is used when space gets below a threshold (usually 10% free). You can set the background color to transparent if you don't wish to have one.
  - **Graphs - Relative Age**: Colors for the Relative Age graphs Opus can display next to things in Details and Power modes. There are separate colors for files and folders. You can set the background color to transparent if you don't wish to have one.
  - **Graphs - Relative Size**: Colors for Relative Size graphs Opus can display next to things in Details and Power modes. There are separate colors for files and folders. You can set the background color to transparent if you don't wish to have one.
  - **Jobs Bar**: The text and background color used for the [jobs bar.](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.md)
  - **Metadata pane**: Colors for the metadata pane (text, background, and the color used to provide alternating colored stripes).
  - **Pane borders**: Colors used for the borders surrounding the various panes (sub-windows) in the Lister (Folder Tree, Viewer pane, etc). Also has options to **Use for lister column headers** and **Use for lister scrollbars**. (The scrollbar option is only available if Windows visual styles are active, and is also disabled if WindowBlinds is detected).
  - **Status bar**: Default text and background color for the Lister status bars (see [Note 4](colors_and_fonts.md#Note4)). Normally, visual styles are used to draw the status bar's frames and borders; however, if a dark background color is chosen, Opus will draw the frames and borders itself using the **Pane borders** colors, since visual styles usually do not look good on dark backgrounds.
  - **Thumbnail relative dimensions**: Color used to render the [thumbnail relative dimension bars](../file_display_modes/thumbnails_mode/RAEDME.md).
  - **Toolbar and menu defaults**: Colors used to draw toolbars and menus.
    - If **use system colors** is turned on, Opus uses visual styles to draw most toolbar and menu elements; if it is off, Opus still uses visual styles to a degree (re-coloring them as needed) but also draws some elements itself where it makes sense. Choosing a light text color or dark background color can influence how much is custom-drawn vs drawn using visual styles, since visual styles tend to only look good with dark-on-light colors.
    - The text and background colors can be [overridden on a per-toolbar basis](/Manual/customize/the_customize_dialog/toolbars.md).
    - The "shadow" and "highlight" colors are used to render toolbar borders and separators, and you can set them to transparent to avoid one or both borders entirely.
    - "Selected" and "Toggled" are used to render the background of toolbar buttons and menu items in different states. If you set them to "use default" they will use the system colors.
    - "Menu background" allows you to use a different background color for menus; choosing "Use Default" will give menus the same background color as toolbars. Note that some menus are drawn by Windows itself and will not be affected by any of these colors.
    - "Menu frame inner" and "Menu frame outer" are used to draw the frame around the outside of pop-up menus, one inside the other. You can set the inner color to transparent if you only want a single-color, one pixel border. Setting both inner and outer colors to transparent will remove the border entirely.
    - "Field background" lets you change the background color of the breadcrumbs path field and search field on Lister toolbars. If no background color is specified, the fields are drawn using Windows visual styles. If a background color is specified, Opus takes over and also uses the other toolbar colors to draw the fields (e.g. the text color also applies to text in the fields, if the field's background color is being overridden).
    - "Field glyphs" lets you change the color of the arrows between path components on the breadcrumbs path field.

      * **Tree highlight path to selection**: Colors used in the folder tree to highlight the path to the currently selected folder (if the appropriate options are enabled). 
      * **Viewer pane background**: Background color for the Viewer pane when it's empty (see [[colors_and_fonts#Note5|Note 5]]).

- **Fonts**: These control the fonts that are used in various parts of the user interface.  
  \* **File display**: The font used to display files and folders in the File Display in all modes except Thumbnails
  - **File display border**: The font used in the File Display border at the top of the file display
  - **File display groups**: The font used for group headings when the file display is grouped
  - **File display header**: The font used for the File Display header in Details mode
  - **Folder tabs**: The font used for Folder Tabs
  - **Folder tree**: The font used for the Folder Tree
  - **FTP log**: The font used for the FTP output log
  - **Info Tip**: The font used for file and folder info tips (tooltips shown when hovering the mouse over a file or folder)
  - **Jobs Bar**: The font used for the [jobs bar.](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.md)
  - **Metadata pane**: The font used in the metadata editor.
  - **Pane borders**: The font used for the title of the various panes (sub-windows) in the Lister (Folder Tree, Metadata pane, etc)
  - **Rename macro builder**: The font used for the [rename macro builder](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.md) (must be fixed-width)
  - **Status bar**: The font used for the Lister status bar
  - **Thumbnail labels**: The font used for item labels when the File Display is in Thumbnails mode

Some notes relating to the above:

1.  ![](/anchor/Note1/)You can specify colors for files and folders on a per file-type basis or for specific files and folders, using the [Labels](/Manual/basic_concepts/folder_options/folder_options_dialog/labels.md) system - this will override colors specified on this page.
2.  ![](/anchor/Note2/)The Folder Tree will use the colors set in the **File and Folder Colors** section by default, but you can set it to ignore these color settings by turning off the **[Use configured file display colors for tree items](../folder_tree/folder_tree_appearance.md)** option, in which case the colors in **Other Colors / Folder tree** will be used.
3.  ![](/anchor/Note3/)On Vista and above, the file displays and folder trees use the Windows Theme by default to display item highlights by default. This normally overrides configured background colors for *selected* files and folders (text color, and non-selected background colors can still be changed). You can change this using the **Use visual styles to draw items** and **Visual styles override file selection colors** settings in [Display Options](display_options.md).
4.  ![](/anchor/Note4/)On Vista and Windows 7 (but not later versions) the status bar will be set to use "glass" mode by default, which overrides the background color setting - turn off the **[Show glass status bar option](display_options.md)** if you prefer a more traditional status bar.
5.  ![](/anchor/Note5/)The viewer pane background color is only used when the Viewer pane is empty. When the viewer is displaying a picture, and the picture doesn't fill the display completely, or has transparent areas, a separate color is used to fill the background. This is configured on the [Viewer Pane](../viewer/viewer_pane.md) page.

 
