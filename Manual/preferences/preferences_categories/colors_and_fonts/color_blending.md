# Color Blending

This page contains options that control how some colors are blended with other colors or with background images.

For all items that include an "opacity" setting, this is used to specify the level of blending that is performed, from 1% (nearly transparent) to 99% (nearly opaque).

- **Blend file background colors with background**: Useful when you have defined a background image or color for the file display, this option causes the solid background colors of files and folders to be blended with the background of the display. Note that if visual styles are in use then this option will have no effect for selected items (as the visual style will override the item's selected background color).
- **Blend row and column background colors**: In Details and Power mode, when you have defined colors for various fields, this option causes those colors to be mixed with the ordinary file and folder background colors rather than overriding them.
- **Blend selected items with column colors**: Blends sort-column and other custom field/column colors with each other and with the background colors (if any) of unselected files. This option is not available if **Use visual styles to draw items** is on, since the visual styles determine the amount of blending in that case. (Visual styles typically use different blending amounts to indicate item states in addition to selection and deselection, such as the "hot" item under the mouse pointer and the item with keyboard focus.)
- **Use visual styles to draw items**: Except when visual styles are disabled, this option renders files and folders in both the tree and the file display using Windows visual styles (themes). When on, item spacing is slightly increased (in addition to any [extra spacing or padding](../file_display_modes/details_mode.md) added explicitly), selection boxes look different, the way icons and labels are highlighted when selected changes, and the "hot" item under the mouse pointer will be highlighted. See below for comparison screenshots.
  - **Selection rectangles overlap:** When using visual styles, the boxes drawn behind selected items in Details and Power modes are normally one pixel taller than the items themselves, causing an overlap between adjacent selected items. This looks good with the Windows 7 theme: It stops the solid borders around selected items from doubling-up. It's a matter of taste in Windows 10: The overlap causes lines between selected items, while turning off the overlap gives you solid blocks of color. The single file with focus always has a box drawn around it, regardless of this setting. Note that if you want lines between items (not just *selected* items), you can use the grid lines options under [Details Mode](../file_display_modes/details_mode.md) and [Power Mode](../file_display_modes/power_mode/RAEDME.md).
  - **Visual styles override file selection colors:** Visual styles normally override any text and background colors you have configured for selected files and folders. This is because the look of the selection indicator comes from the visual style (theme) rather than from Opus. Your configured "unselected" text colors are used even when things are selected, and the visual style determines the color and look of the selection box behind each file (usually blue with a very low opacity). Turning off *Visual styles override file selection colors* results in a hybrid mode: Selection indicators will be drawn by Opus again, with full support for independent text and background colors when items are selected, but you will still retain the other aspects of using visual styles to draw the file display and folder tree (item spacing, icon/label selection style, "hot" items, and so on). If you are using dark background colors, you will almost certainly want to turn off this option because the selection indicators drawn by Windows are difficult to see on dark backgrounds. Example screenshots are below.
- **Drag image opacity**: Specifies how transparent files and folders are when they are being dragged.
- **Background graph opacity**: Some file information columns in details mode can display a bar graph behind the text (to indicate file size and age - enabled via the [File Display Columns \> Options](../file_display_columns/options.md) page). This option controls the transparency of those graphs.

  
The items under the **Selection opacities** heading affect the opacity/transparency of selected file and folder items in the file display and folder tree.

- **Inactive file display**: Turn this on to have selected files in the file display faded more (or less) when the window is inactive.
- **Inactive folder tree**: Turn this on to have selected folders in the tree faded more (or less) when the window is inactive.
- **Hot**: Specifies the opacity for items under the mouse pointer.
- **Selected**: Specifies the opacity for selected items.
- **Selected & hot/focused**: Specifies the opacity for selected items under the mouse pointer.

  
Examples of the settings related to visual styles:

**Use visual styles to draw items** on, **Visual styles override file selection colors** on:

![](/Manual/images/media/13/colorblending_1.png)

**Use visual styles to draw items** on, **Visual styles override file selection colors** off:

![](/Manual/images/media/13/colorblending_2.png)

**Use visual styles to draw items** off:

![](/Manual/images/media/13/colorblending_3.png)
