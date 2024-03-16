# Directory Opus Colors

This page lets you configure the colors of everything that isn't a Windows control.

![](/Manual/images/media/13/prefs_opuscolors.png)

The various color categories are arranged in two main groups:

- **File and Folder Colors**: These are the colors [^1] that are used for the display of files and folders in the File Displays, and elements related to them.
- **Other Colors**: These are colors used elsewhere in the user interface - they're not related to file displays themselves, but to other parts of the Lister.

At the bottom of the color list is a search field that lets you search the color list.

Selecting a category from the color list displays its associated colors on the right. Some colors also display a preview of how it will look in real life - useful when you're picking both text and background colors and want to check for readability.

Note that when you edit colors on this page you're only editing the colors in the current set ("dark" or "light") - use the options on the [themes](themes.md) page to select which color set is in use.

##### Editing Colors

<img src="/media/13/color_picker.png" class="align-right" data-query="?nolink" /> The color picker button ![](/Manual/images/media/13/color_control.png) is the main control for editing colors. Some color pickers have a checkbox on them, which lets the associated color be enabled or disabled. Clicking the button displays the color picker.

The color picker lets you choose a color using both the red/green/blue and hue/saturation/luminance models. The current color values are shown at the top-left of the picker - you can click there to type new values in directly. If the color in question supports transparency, an additional slider lets you set the alpha value from 0 (fully transparent) to 255 (fully opaque).

The eyedropper icon ![](/Manual/images/media/13/eyedropper.png) can be dragged out to pick a color from somewhere else on your screen.

The 16 squares at the bottom let you save your own favorite colors - right-click on a slot to store the current color, or left-click to load a saved color in.

The ![prefs_menu.png](/Manual/images/media/13/prefs_menu.png) button shows a menu containing several commands:

- **Copy**: Copies the value of the current color to the clipboard.
- **Copy with alpha**: (Only for colors supporting transparency.) Copies the current color value to the clipboard, including the alpha channel (transparency).
- **Copy markup code**: Copies the current color as markup code that you can use in various places in Opus that support HTML (e.g. in [file type infotips](/Manual/file_types/filetype_editor/info_tip.md).)
- **Paste**: Paste a color value from the clipboard into the picker. If the color supports transparency, but the clipboard doesn't include that information, the clipboard's RGB values will be used and the existing alpha value will be kept.
- **Paste (swap with clipboard)**: Paste a color value into the picker, and put the previous value on the clipboard.
- **Reset to factory default**: Resets the color to the factory defaults.
- **Reset to initial value**: Resets the color to the value it had when the Preferences dialog opened.
- **Reset to last saved value**: Resets to the color value that was last saved to your configuration.
- **Get *other* mode color**: Lets you pull in the color from the other color set (e.g. if you're in dark mode, you can pull in the color from the light mode color set).
- **Use hex format**: The color value displayed at the top-right, or copied to the clipboard, will be in hex format (#RRGGBB) rather than decimal format (RRR,GGG,BBB).

Some of these commands may be disabled depending on the current color value (e.g. if it's the same as the initial or factory default, the reset commands will be disabled).

The commands in that menu are also available when you right-click the color picker button itself (so for example, you don't need to show the color picker in order to copy the color to the clipboard).

##### File and Folder Colors

- **File display background**: The background color of the file display area. You can also set a different color that's used when a file display is in [destination](/Manual/basic_concepts/source_and_destination.md) mode (either in a single file display Lister or as part of a dual display Lister), also when it's off (i.e. a single file display Lister that isn't either the source or destination). You can also set separate colors for when the [quick filter](/Manual/basic_concepts/searching_and_filtering/filter_bar.md) is active. \<WRAP\>

  
If you turn off the destination or background colors, the main background color will be used for both source and destination file displays (and similarly, if the 'filtered' colors are turned off the main colors will be used instead).

The **Inline Sub-folders** color is used in the icon view modes (e.g. thumbnails) when [sub-folders are expanded](/Manual/basic_concepts/expandable_folders.md). The different background color makes it easier to distinguish the contents of sub-folders from those of the parent folder. \</WRAP\>

- **File group column**: When the file display is grouped, you have the option of showing the group names as headings between each group or in a column on the side. If you choose to use the group column, this defines its colors.
- **File group header**: When the file display is grouped, and you opt for group names to be displayed as headings between each group, this defines the text and separator color for the group headings. The glyph colors are used for the icons you click to expand or collapse a group, in display modes which allow collapsing, with the "hot" color used when the mouse is over the glyph.
- **Files and folders**: The text and background colors for files and folders that don't derive a color from some other setting [^2]. You can specify colors for when these items are selected as well as in their unselected state. Using visual styles to draw items and selection boxes may override some of these colors; if this is happening, a clickable message will appear below the last color, and clicking it will take you to the option you can turn off if you don't want this to happen. \<WRAP\>

  
The **Current sort column** option lets you specify different colors to be used in details and Power modes. The column the list is currently sorted by will be displayed in the specified colors.\</WRAP\>

      * **Compressed**, **Encrypted** and **System**: Optional colors for various types of files that will override the defaults if activated. Compressed files are those with the **C** attribute, encrypted files are those with the **E** attribute, and system files are those with both the **H** and **S** attributes set. 
      * **Favorites**: Optional colors that are used for any folders you have added to the [[:basic_concepts:the_lister:navigation:favorites|Favorites]] list. 
      * **Matched Text**: Colors used to highlight text matches in filenames when using the [[:basic_concepts:the_lister:find-as-you-type_field|Find-as-you-Type]] field (and the **[[:preferences:preferences_categories:filtering_and_sorting:find_as_you_type:find_mode|Highlight matches]]** option is turned on). 
      * **Queued**: Colors that are used for files that are [[file_operations:copying_moving_and_deleting_files:copy_queues|queued to be copied]]. 
      * **Synchronize**: Colors that are used with the Synchronize tool to indicate files which are in conflict and what actions have been chosen.
    * **Folder expanders**: The buttons you click to [[:basic_concepts:expandable_folders|expand folders]] in the file display.
    * **Grid lines**: Style and color settings for grid lines in details and Power modes. You can set separate styles for horizontal and vertical grid lines, and set their colors. You can also set the style and color used to indicate [[:basic_concepts:folder_options:folder_options_dialog:columns:frozen_columns|frozen columns]].
    * **Highlighted cells**: Color settings for cells you have [[::basic_concepts:selecting_files:selecting_cells|selected]].
    * **Selection lasso**: Color and transparency settings for the lasso (marquee) that you see when dragging around files to select them.
    * **Thumbnails**: Colors used for thumbnail borders, both for folders and for images. You can also select the colors for the various thumbnails overlays.
    * **Tiles**: Colors used to draw tiles in tiles mode.

##### Other Colors

- **Cloud status icons**: Colors used to draw the status icons for files stored in cloud services (e.g. Dropbox or Onedrive). This only affects the separate Status column (which is optional), not any icon overlays added by the cloud service itself.
- **Code editor**: Colors used in the code editor (used mainly in the [command editor](/Manual/customize/creating_your_own_buttons/command_editor/advanced_command_editor.md) and in the [script editor](/Manual/scripting/script_editor/RAEDME.md).)
- **File display icon**: Defines the color used for the Opus logo icon that is shown in the File Display border, as well as that used for the Lister's window icon. You can define different colors for when the Lister is set as source, destination or off, as well as a separate color for when the Lister is in dual-display mode.
- **Folder tabs**: Text and background colors for folder tabs, as well as the background color for the bar (empty space) behind the tabs. You can also configure a separate "hot" color for when the mouse is over a tab, and an edge color to indicate when a tab is locked.
  - **Destination**: Lets you specify separate colors for tabs in the destination file display. These are optional; if not configured, the primary tab colors will be used.
  - **Linked tabs**: Lets you configure the colors used when folder tabs are linked. You can configure 15 separate linked tab colors. Each pair of linked tabs uses the colors in the order they are specified here.
- **File display border - Destination**, **Off**, **Source**: Defines the text and fill colors used for the File Display border (the "title" bar displayed at the top of the file display) in each of the [three Lister states](/Manual/basic_concepts/source_and_destination.md).
- **Folder tree**: Text and background colors for items in the folder tree, if not overridden by the above colors [^3]. The glyph colors are used for the icons you click to expand or collapse a branch, and the pin colors for the optional pin button which lets you pin folders to be permanently expanded.
  - **Destination**: When a dual-display Lister has two trees, or a single-display Lister with a tree is set as the destination, you can use this to specify different colors for the tree associated with the destination file display.
  - **Path to selection**: Colors used in the folder tree to highlight the path to the currently selected folder (if the appropriate options are enabled).
- **Graphs**
  - **Copy speed**: Colors used by the copy progress speed graph.
  - **Free space**: Colors used to draw the free-space graphs in places like the This PC (aka My Computer) folder and the status bar. The "warning" color is used when space gets below a threshold (usually 10% free). You can turn off the background color if you don't want to have one.
  - **Pie charts**: Colors used for the various segments of the pie chart used by the [file type summary](/Manual/additional_functionality/filetype_summary.md) feature.
  - **Relative age**: Colors for the Relative Age graphs Opus can display next to things in Details and Power modes. There are separate colors for files and folders.
  - **Relative size**: Colors for Relative Size graphs Opus can display next to things in Details and Power modes. There are separate colors for files and folders.
- **Jobs bar**: The text and background color used for the [jobs bar.](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.md)
  - **New job arrow**: Colors for the animated arrow that indicates a new job being scheduled to the jobs bar.
- **Location bar**: Various colors for the different elements of the [location bar](/Manual/basic_concepts/the_lister/navigation/file_display_border.md) and [path field](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md).
- **Logs**: Colors used in the [FTP](/Manual/ftp/ftp_log.md) and [script](/Manual/scripting/script_log.md) logs.
- **Metadata pane**: Colors for the metadata pane (text, background, and the color used to provide alternating colored stripes).
- **Miscellaneous**: Miscellaneous colors that wouldn't fit in any other category!
- **Pane borders**: Colors used for the borders surrounding the various panes (sub-windows) in the Lister (Folder Tree, Viewer pane, etc). Also has options to **Use for lister column headers** and **Use for lister scrollbars**. (The scrollbar option is only available if Windows visual styles are active, and is also disabled if WindowBlinds is detected).
- **Preferences UI**: Colors that affect the Preferences dialog itself.
- **Status bar**: Default text and background color for the Lister status bars. Normally, visual styles are used to draw the status bar's frames and borders; however, if a dark background color is chosen, Opus will draw the frames and borders itself using the **Pane borders** colors, since visual styles usually do not look good on dark backgrounds.
  - **Framed text**: The status bar can be configured to show a list of file extensions (using the \<ib:inline-code\>`{ft}`\</ib:inline-code\> code); these options control the appearance of those extensions.
- **Toolbars**: Colors used to draw toolbars and menus.
  - If **Use visual styles** is turned on, Opus uses visual styles to draw most toolbar and menu elements; if it is off, Opus still uses visual styles to a degree (re-coloring them as needed) but also draws some elements itself where it makes sense. Choosing a light text color or dark background color can influence how much is custom-drawn vs drawn using visual styles, since visual styles tend to only look good with dark-on-light colors.
  - The text and background colors can be [overridden on a per-toolbar basis](/Manual/customize/the_customize_dialog/toolbars.md).
  - The "shadow" and "highlight" colors are used to render toolbar borders and separators, and you can turn them off to avoid one or both borders entirely.
  - "Selected" and "Toggled" are used to render the background of toolbar buttons and menu items in different states. If you set them to "use default" they will use the system colors.
  - "Menu background" allows you to use a different background color for menus; choosing "Use Default" will give menus the same background color as toolbars. Note that some menus are drawn by Windows itself and will not be affected by any of these colors.
  - "Menu frame inner" and "Menu frame outer" are used to draw the frame around the outside of pop-up menus, one inside the other. You can turn the inner color off if you only want a single-color, one pixel border. Turning off both inner and outer colors will remove the border entirely.
  - "Field background" lets you change the background color of the search field on Lister toolbars. If no background color is specified, the fields are drawn using Windows visual styles. If a background color is specified, Opus takes over and also uses the other toolbar colors to draw the fields (e.g. the text color also applies to text in the fields, if the field's background color is being overridden).
- **Toolbars (Office-style)**: If turned on, Opus will draw toolbars and menus in a style inspired by Office 2003. If turned off, toolbars will be drawn in the "normal style" for your OS version.
  - **Gradients**: This specifies the gradient colors used to fill the left-hand edge ("gutter") of drop-down menus.
  - **Automatic highlight colors**: If this is enabled most colors are generated from the specified **Base color**.
  - **Custom highlight colors**: This lets you can completely configure the colors for all elements and states of the toolbar.
- **Viewer**: Colors that affect the [standalone viewer](/Manual/additional_functionality/viewing_images/RAEDME.md) and [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md).
  - **Viewer pane**: Colors that specifically affect the [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md).
  - **Plugin - Text**: Colors that affect the *text viewer plugin*.
  - **Plugin - Video & Audio**: Colors that affect the *video and audio plugin*.
  - **Plugin - WAV**: Colors that affect the *WAV sound file plugin*.

[^1]: You can specify colors for files and folders on a per file-type basis or for specific files and folders, using the [Labels](/Manual/file_operations/labels.md) system - this will override colors specified on this page

[^2]: On Vista and above, the file displays and folder trees use the Windows Theme by default to display item highlights by default. This normally overrides configured background colors for *selected* files and folders (text color, and non-selected background colors can still be changed). You can change this using the **Use visual styles to draw items** and **Visual styles override file selection colors** settings on the [Color Blending](color_blending.md) Preferences page

[^3]: The Folder Tree will use the colors set in the **File and Folder Colors** section by default, but you can set it to ignore these color settings by turning off the **[Use configured file display colors for tree items](../folder_tree/appearance.md)** option, in which case the colors in **Other Colors / Folder tree** will be used
