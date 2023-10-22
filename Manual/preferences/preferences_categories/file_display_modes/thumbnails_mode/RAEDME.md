# Thumbnails

This page contains options that affects the appearance of thumbnails in file displays.

- **Thumbnail size**: Specify the size in pixels of thumbnail images (*width* x *height*). Thumbnails will be scaled down to fit within these boundaries, preserving their aspect ratio. The ![](/Manual/images/media/13/pathlink-linked.png) **Make square** button provides a quick way to set the width and height to the same values.
- **Spacing**: Specify the spacing between thumbnails (*horizontal* x *vertical*). (Note that if labels are enabled and set to more than one line, the vertical spacing shares its space with the extra label lines and will not have much effect on the actual spacing until the value is very large.)
- **Spread excess space between columns**: Leftover space will be shared between each thumbnail column instead of appearing to the right of the last column.
- **Resize mode**: Let's you choose how images are resized to fit the space available in the thumbnail.
- **Rotate images automatically using EXIF metadata**: Most modern digital cameras contain an orientation sensor that records into the image the orientation of the camera when the picture was taken. If this option is turned on Opus will read the orientation information from the image and automatically rotate the displayed thumbnail so that it appears the right way up.

  
==Labels==

If the **Labels** option is turned on, the filename will be displayed below each thumbnail.

- **Lines**: Specify the maximum number of lines of text that the thumbnail's label can display.
- **Display date taken in label**: Opus will display the date taken (in the case of digital photos), or the last modified file date, in a smaller font below the thumbnail's label.
- **Display image and file size in label**: Opus will display the size of the image (and the size of the file) in a smaller font below the thumbnail's label.

  
==Overlays==

Controls various overlay icons that can appear on top of the thumbnail.

- **Overlay film sprockets on videos and animations**: Adds film sprockets to the sides of video and animation thumbnails.
- **Overlay rating stars**: Opus will overlay the thumbnail image with stars to indicate its assigned rating (if you have assigned the file a rating, that is). Ratings are assigned using the [metadata](/Manual/file_operations/editing_metadata/RAEDME.md) functions.  
  \* **Overlay aspect ratio bars**: Overlay bars representing each image's aspect ratio. Similar to the **Overlay relative dimension bars** option, but represents the dimensions of each image relative to each other, rather than to the respective widest and tallest image in the folder. A visual representation of the aspect ratio can help if you're using the "fill (resize and crop)" resize mode, where it can be hard to tell whether an image has been cropped and how much. (If you aren't using that mode, you can obviously see an image's aspect ratio from the thumbnail itself, making the bars redundant except for unusual cases with lots of transparency around the edges.)
- **Overlay relative dimension bars**: Opus will draw small horizontal and vertical bar graphs over the thumbnail to represent the dimensions of that image file relative to the largest image in the current directory. This is particularly useful when you have multiple copies of the same image saved at different resolutions - their thumbnails will ordinarily all look the same, and the bar graphs let you tell at a glance which relative size each file is. This option can also be changed from a button or hotkey using the **RELDIMENSIONOVERLAYS** argument to the internal **[Set](/Manual/reference/command_reference/internal_commands/set.md)** command.
- **Overlay thumbnail with file type icon**: Opus will display a small icon for the type of file in question in the bottom corner of the thumbnail image (e.g. a JPEG image will have the generic **.jpg** icon displayed in the corner of the thumbnail).
- **Hide file type icon if type not registered**: With the above option on, the file type icon will not be shown if the file type is not registered. This mostly applies to image files that may have no file extension - Opus is still able to display thumbnails for them as it looks at the file contents to determine their type, but there would be no valid icon registered in the system that could be shown.
