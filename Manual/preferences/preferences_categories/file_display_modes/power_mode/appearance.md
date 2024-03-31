# Appearance

Contains options that affect the appearance of *Power* mode file displays.

- **Display icons**: Lets you turn off the display of file icons in *Power* mode.
  - **Hide icons when thumbnail column is visible**: If the *Thumbnail* column is displayed, you may not want to show file icons as well - turning this option on will hide the icons automatically when the *Thumbnail* column is present.
- **Extra line padding**: Lets you add additional padding inside each line, making each line taller and a larger area to click on. The padding you specify will be scaled if your config is used in a different DPI.
- **Extra line spacing**: (This setting may be removed in the future.) Lets you add additional spacing between each line. A particular use for this *was* to add one extra pixel between lines if you disliked the way selection boxes overlapped (producing a thin line between selected items) in some versions of Windows; however, there is now an explicit option for that under [Color Blending](/Manual/preferences/preferences_categories/colors_and_fonts/color_blending.md), independent of spacing and padding. If you add more than one pixel of spacing, you will start to get gaps between items where clicking them is like clicking the folder background. Unlike padding, the spacing value does not change when you move to different DPIs.

  

### File selection / highlighting style

Lets you control both how selected files are displayed and which areas of the line respond to mouse clicks for selecting files.

- **Filename only**: \<wrap\>Only the filename is active - clicking anywhere to the left or right of the filename will not select the item.

  
  
![](/Manual/images/media/13/fileselection_nameonly.png)  
  
\</wrap\>

- **Full width of the Name column**: \<wrap\>The entire *Name* column is active - clicking anywhere to the left or right of that column will not select the item.

  
  
![](/Manual/images/media/13/fileselection_fullwidth.png)  
  
\</wrap\>

- **Full row**: \<wrap\>The entire row is active - you can click anywhere on the item, in any column, to activate it.

  
  
![](/Manual/images/media/13/fileselection_fullrow.png)  
  
\</wrap\>

- **Always highlight full row**: Normally the option above controls both the active area for selection and the width of the highlight that is displayed for selected items. If this option is on, the full row will be highlighted when an item is selected, irrespective of which option is selected for the active area.

  
==Thumbnail column==

These options affect the *Thubmnail* column.

- **Aspect ratio**: Controls the aspect ratio of the column. The width of the *Thumbnail* column is set like the width of any other column - by resizing the column header using the mouse (or using the **Default width** option on the [File Display Columns / Appearance](/Manual/preferences/preferences_categories/file_display_columns/appearance.md) page). The aspect ratio you specify controls the row height. For example, setting the aspect ratio to 1:1 would mean the row height of each line would be the same as the width of the column.
- **Padding**: Lets you add internal padding to the column. This doesn't affect how big the column is - it changes how large the thumbnail is by adding empty space around it.
- **Resize mode**: Let's you choose how images are resized to fit the space available in the *Thumbnail* column.
