# Tiles Mode

This page contains options that control the appearance of the file display in *Tiles* mode.

- **Label size**: This specifies the size of individual tiles (or more accurately, of the text part of individual tiles). It is given as the number of characters wide and the number of lines of text high.
- **Spacing**: This is the spacing between tiles (*horizontal* x *vertical*), in pixels.
- **Spread excess space between columns**: Leftover space will be shared between each tile column instead of appearing to the right of the last column.
- **Expand tile with focus if needed**: When a tile has the input focus, it will be expanded to overlap other adjacent tiles if its label is bigger than the size allowed in the **Label size** setting. This lets you read the full name of the selected item when it may otherwise be clipped.
- **Vertical layout**: Normally *Tiles* mode has a horizontal layout - tiles are drawn from left-to-right, top-to-bottom, and if a scrollbar is needed the list scrolls vertically. With this option on, the layout is switched to a vertical one - tiles go top-to-bottom, left-to-right, and scrolling is horizontal, similar to *List* mode.

  

##### Thumbnails in tiles

You can optionally have *Tiles* mode also display thumbnails for files.

- **Thumbnail size**: Specify the size in pixels of thumbnail images (*width* x *height*). Thumbnails will be scaled down to fit within these boundaries, preserving their aspect ratio. The ![](/Manual/images/media/13/pathlink-linked.png) **Make square** button provides a quick way to set the width and height to the same values.
- **Resize mode**: Let's you choose how images are resized to fit the space available in the thumbnail.
- **Show file type icon in tile**: Because the thumbnail replaces the display of the normal file icon, this option lets you display a small version of the icon in the bottom corner of the tile. Either the frame or fill options for Tiles must be enabled on the [Directory Opus Colors](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.md) page for this to work - it's disabled otherwise, because the file type icon would end up floating in space.
- **Hide file type icon if type not registered**: With the above option on, the file type icon will not be shown if the file type is not registered. This mostly applies to image files that may have no file extension - Opus is still able to display thumbnails for them as it looks at the file contents to determine their type, but there would be no valid icon registered in the system that could be shown.
