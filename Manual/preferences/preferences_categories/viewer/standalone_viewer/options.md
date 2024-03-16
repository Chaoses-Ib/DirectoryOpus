# Options

These options affect the [standalone image viewer](/Manual/additional_functionality/viewing_images/RAEDME.md).

- **Default gamma correction**: Use this option if you need to adjust the gamma of images for proper color reproduction on your monitor. This sets a default gamma adjustment but you can adjust the display on-the-fly from within the viewer.
- **Hide scrollbars**: The viewer won't display scrollbars even if the image is too large to fit in the display. You can pan around an image with the cursor keys, and using the mouse (depending on the options set below). Some viewer plugins may not support this option.
- **Show status icons**: If the currently viewed image has any [status icons](/Manual/file_operations/labels.md) assigned these will be displayed in the status bar (or top-left corner of the viewer window if the status bar is turned off).
- **Show thumbnails in Marked Pictures pane**: Thumbnails of each [marked image](/Manual/additional_functionality/viewing_images/image_marking.md) will be shown in the *Marked Pictures* pane in the viewer. You can configure the thumbnail size below.
- **Use EXIF information to auto-rotate pictures**: Most modern digital cameras contain an orientation sensor that records into the image the orientation of the camera when the picture was taken. If this option is turned on Opus will read the orientation information from the image and automatically rotate the displayed picture so that it appears the right way up. The actual image file on disk is not modified, only the display in the viewer.

##### Viewer title bar

- **Custom title**: Lets you completely configure the string used in the  title bar. If you turn this option on, the text you provide will be used to generate the title string. See below for more information.
- **Display full path**: Turn this option on to display the full path to each file in the title bar of the viewer window. If turned off, only the filename will be shown.

##### Custom title bar

You can use several special "tokens" in the title string to insert various pieces of information:

|            |                                                                                                      |
|------------|------------------------------------------------------------------------------------------------------|
| **%P**     | full path of the currently viewed image                                                              |
| **%N**     | name of the current displayed image                                                                  |
| **%R**     | drive root of the current image                                                                      |
| **%E**     | displays \* if the image's metadata has been modified and not saved                                  |
| **%I**     | current image's index (number) in the list of images                                                 |
| **%O**     | total number of images in the list                                                                   |
| **%W**     | width of the current image                                                                           |
| **%H**     | height of the current image                                                                          |
| **%D**     | depth of the current image (bits per pixel)                                                          |
| **%M**     | current image's dimensions                                                                           |
| **%S**     | file size on disk                                                                                    |
| **%F**     | folder name                                                                                          |
| **%C**     | collection name if current image is [marked](/Manual/additional_functionality/viewing_images/image_marking.md) |
| **%L**     | any [labels](/Manual/file_operations/labels.md) assigned to the current image                                  |
| **%T**     | complete original title (useful for simply adding a prefix or suffix to the title)                   |
| **%%%%%%** | insert a literal % character                                                                         |
| **%!**     | hide empty blocks within %!...%! (see below)                                                         |

The `%!` code is special in that it should be used in pairs around the things you want to hide. They will be hidden if all tokens within the block expand to empty values.

Consider `%!Dimensions: %W x %H%!`, for example: If `%W` and `%H` (width and height) are unavailable (e.g. because the viewer isn't displaying an image) then this will output nothing at all instead of a meaningless *"Dimensions: 0 x 0"*.
