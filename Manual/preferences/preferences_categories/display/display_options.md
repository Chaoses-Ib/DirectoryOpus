# Display Options

This page contains various options relating to the appearance of Listers. For all items that include an "opacity" setting, this is used to specify the level of blending that is performed, from 1% (nearly transparent) to 99% (nearly opaque).

- **Blend file background colors with background**: Useful when you have defined a background image or color for the File display, this option causes the solid background colors of files and folders to be blended with the background of the display. Note that if visual styles are in use then this option will have no effect for selected items (as the visual style will override the item's selected background color).
- **Blend file selection rectangle**: When you click in an empty area of the file display and drag out the selection rectangle ("marquee") it will be drawn as a filled rectangle blended with the background, rather than just as an outline.
- **Blend row and column background colors**: In Details and Power mode, when you have defined colors for various fields, this option causes those colors to be mixed with the ordinary file and folder background colors rather than overriding them.
- **Blend selected items with column colors**: Blends sort-column and other custom field/column colors with each other and with the background colors (if any) of unselected files. This option is not available if **Use visual styles to draw items** is on, since the visual styles determine the amount of blending in that case. (Visual styles typically use different blending amounts to indicate item states in addition to selection and deselection, such as the "hot" item under the mouse pointer and the item with keyboard focus.)
- **Enable background images in virtual folders**: With this option on, Opus will try to use your background image settings when it is displaying a [virtual folder](../folders/virtual_folders/RAEDME.md) (e.g. Network Neighborhood). As these folders are provided by the operating system and Opus merely hosts them as a container, it won't necessarily work! Note that it isn't possible to change the text color in these folders, so this option isn't suitable for inverted color schemes.
- **Enable custom fonts in virtual folders**: With this option on, your choice of File Display font will be applied to [virtual folder](../folders/virtual_folders/RAEDME.md) in addition to the normal folders which Opus handles itself. Virtual folders are handled by Windows, or sometimes third-party components, and are largely outside of Opus's control. Opus can ask them to use a different font, but this can result in cosmetic issues or even crashes. If you run into problems using virtual folders, or when opening new windows or tabs, you should turn this option off again.
- **Fade selected item colors when file display does not have focus**: When the file display isn't the active window, the background colors of selected files and folders will be faded to indicate the non-active nature of the window. The checkbox always has an effect, but the opacity setting is only effective if either (or both) of **Use visual styles to draw items** and **Visual styles override file selection colors** are off. When using visual styles and allowing them to override selection colors, this option is a simple on/off switch and the faded look is determined by the Windows theme.
- **Fade selected item colors when tree does not have focus**: The same as the above option, except it applies to the Folder Tree rather than the file display.
- **Use visual styles to draw items**: Except on Windows XP (or when visual styles are disabled system-wide), this option renders files and folders in both the tree and the file display using Windows visual styles (themes). When on, item spacing is slightly increased (in addition to any [extra spacing or padding](../file_display_modes/details_mode.md) added explicitly), selection boxes look different, the way icons and labels are highlighted when selected changes, and the "hot" item under the mouse pointer will be highlighted. See below for comparison screenshots.
  - **Hot-tracking of mouse cursor:** When using visual styles, file displays usually highlight the item under the mouse pointer (known as the "hot" item) as you move the mouse around. If you find this distracting, you can turn it off here.
  - **Selection rectangles overlap:** When using visual styles, the boxes drawn behind selected items in Details and Power modes are normally one pixel taller than the items themselves, causing an overlap between adjacent selected items. This looks good with the Windows Vista/7 theme: It stops the solid borders around selected items from doubling-up. It's a matter of taste in Windows 10: The overlap causes lines between selected items, while turning off the overlap gives you solid blocks of color. The single file with focus always has a box drawn around it, regardless of this setting. Note that if you want lines between items (not just *selected* items), you can use the grid lines options under [Details Mode](../file_display_modes/details_mode.md) and [Power Mode](../file_display_modes/power_mode/RAEDME.md).
  - **Visual styles override file selection colors:** Visual styles normally override any text and background colors you have configured for selected files and folders. This is because the look of the selection indicator comes from the visual style (theme) rather than from Opus. Your configured "unselected" text colors are used even when things are selected, and the visual style determines the color and look of the selection box behind each file (usually blue with a very low opacity). Turning off *Visual styles override file selection colors* results in a hybrid mode: Selection indicators will be drawn by Opus again, with full support for independent text and background colors when items are selected, but you will still retain the other aspects of using visual styles to draw the file display and folder tree (item spacing, icon/label selection style, "hot" items, and so on). If you are using dark background colors, you will almost certainly want to turn off this option because the selection indicators drawn by Windows are difficult to see on dark backgrounds. Example screenshots are below.

- **Lister title bar**: By default, the Lister title bar displays just the name of the current folder. You can change that here.
  - **Display full path:** Puts the full path into the title bar instead of just the folder name.
  - **Display layout name (if any):** Adds the name of the [layout](/Manual/basic_concepts/the_lister/layouts/RAEDME.md) that the Lister came from. (Does nothing extra when the window wasn't opened via a layout.)
  - **Custom title**: Lets you configure a completely custom string for the Lister title bar. You can even leave the field empty if you don't want a title!

The codes below can be used to insert information into the custom title bar string.

When using the **Custom title** option, the **Display full path** and **Display layout name (if any)** options still affect what the **%T** code inserts.

**%P** - full path of the current (source) folder  
**%N** - name of the current (source) folder  
**%R** - drive root of the current (source) folder  
**%D** - full path of the destination folder  
**%M** - name of the destination folder  
**%G** - target if the folder is a junction or softlink  
**%1** - full path in the left file display  
**%2** - full path in the right file display  
**%3** - folder name in the left file display  
**%4** - folder name in the right file display  
**%L** - name of the Layout the Lister came from (if any)  
**%S** - name of the current Style selected in the Lister (if any)  
**%T** - complete original title (useful for simply adding a prefix or suffix to the title)  
**%%%%%%** - insert a literal % character  
**%!** - hide empty blocks withing %!...%! (see below)  
  
The **%!** code is special in that it should be used in pairs around the things you want to hide. They will be hidden if all tokens within the block expand to empty values.  
  
Consider a title of "**%!%N - %!Directory Opus**", for example: If **%N** expands to *"My Folder"* then you will get *"My Folder - Directory Opus"*. If **%N** expands to nothing (e.g. the active folder tab is empty and has no path) then you will get *"Directory Opus"*, rather than *" - Directory Opus"*.  
  
If you need something even more custom or dynamic, the titlebars for individual windows can also be overridden via commands and scripts.  
  

      * **Use current folder's icon**: When turned on, the icon for  the current folder (i.e. the source, active folder tab) will be used as the  icon for the whole window. When turned off, the Directory Opus logo is used  instead, where the logo changes color to indicate the window's state  (//source//, //destination// or //dual file  display//).\\ \\ 
    * **Drag image opacity**: Specifies how transparent files and  folders are when they are being dragged. 

Examples of the settings related to visual styles, with standard and dark color schemes:

**Use visual styles to draw items** on,  
**Visual styles override file selection colors** on:

![](/Manual/images/media/files_-_visual_styles.png) ![](/Manual/images/media/files_-_visual_styles_dark.png)  

**Use visual styles to draw items** on,  
**Visual styles override file selection colors** off:

![](/Manual/images/media/files_-_hybrid.png) ![](/Manual/images/media/files_-_hybrid_dark.png)  

**Use visual styles to draw items** off:

![](/Manual/images/media/files_-_no_styles.png) ![](/Manual/images/media/files_-_no_styles_dark.png)
