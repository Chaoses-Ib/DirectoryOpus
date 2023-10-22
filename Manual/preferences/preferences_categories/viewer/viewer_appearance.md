# Viewer Appearance

These options affect the [Standalone Image viewer](/Manual/additional_functionality/viewing_images/RAEDME.md) - the Opus viewer that opens in a separate window. Options that affect the [Viewer Pane](/Manual/basic_concepts/the_lister/viewer_pane.md) are configured on a [separate page](viewer_pane.md).

- **Auto-size viewer window**: Normally the viewer will remember the size and position of its window from one use to the next. If you turn this option on then when the viewer opens it will automatically resize itself; the options available for this are:  
  \* **To fit every picture**: The viewer will resize to fit the first picture, and resize itself for every subsequent picture as well.
  - **To fit the first picture**: The viewer will resize itself to fit the first picture only.
  - **Full screen**: The viewer will always open in full-screen mode.

- **Minimum window width**: If the viewer is auto-sized, this option lets you specify a minimum width below which it won't go. You can save this from a existing viewer using the **View / Save Minimum Width** command in the menu.
- **Center viewer window**: This causes the viewer window to be centred on the screen. If this is turned off you can position the viewer where you like and it will remember its position in future.
- **Default gamma correction**: Use this option if you need to adjust the gamma of images for proper color reproduction on your monitor. This sets a default gamma adjustment but you can adjust the display on-the-fly from within the viewer.
- **Frame picture**: This option causes a frame (with shadowing) to be drawn around the image displayed in the viewer.
- **Hide scrollbars**: If this option is turned on the viewer will not display scrollbars even if the image is too large to fit in the display. You can pan around an image with the cursor keys, and using the mouse (depending on the options set below). Note that some viewer plugins may not support this option.
- **Show status icons**: If the currently viewed image has any [status icons](/Manual/file_operations/labels.md) assigned these will be displayed in the status bar (or top-left corner of the viewer window if the status bar is turned off).
- **Show thumbnails in Marked Pictures pane**: If this option is on, thumbnails of each [marked image](/Manual/additional_functionality/viewing_images/image_marking.md) will be shown in the Marked Pictures pane in the viewer.  
  \* **Show in icon mode**: Thumbnails will be shown when the Marked Pictures pane is in icon mode.
  - **Thumbnail size**: Lets you configure how big the thumbnails in the Marked Pictures pane will be. 

- **Use EXIF information to auto-rotate pictures**: Most modern digital cameras contain an orientation sensor that records into the image the orientation of the camera when the picture was taken. If this option is turned on Opus will read the orientation information from the image and automatically rotate the displayed picture so that it appears the right way up. The actual image file on disk is not modified, only the display in the viewer.
- **Background color**: This lets you define the background color used by the viewer. If an image doesn't completely fill the viewer's window it will be framed by this color. You can turn on the **Auto** option to have Opus try to pick a background color that matches the current image.
- **Toolbar**: This lets you select a different toolbar to use in the viewer.
- **Viewer title bar**: These options let you configure the text shown in the viewer's title bar.  
  \* **Display full path**: Turn this option on to display the full path to each file in the title bar of the viewer window. If turned off, only the filename will be shown.
  - **Custom title**: This option lets you completely configure the string used in the  title bar. If you turn this option on, the text you provide in the *Custom title* field will be used to generate the title string.

You can use several special "tokens" in the title string to insert various pieces of information:

**%P** - full path of the currently viewed image  
**%N** - name of the current displayed image  
**%R** - drive root of the current image  
**%E** - displays \* if the image's metadata has been modified and not saved  
**%I** - current image's index (number) in the list of images  
**%O** - total number of images in the list  
**%W** - width of the current image  
**%H** - height of the current image  
**%D** - depth of the current image (bits per pixel)  
**%M** - current image's dimensions  
**%S** - file size on disk  
**%F** - folder name  
**%C** - collection name if current image is [marked](/Manual/additional_functionality/viewing_images/image_marking.md)  
**%L** - any [labels](/Manual/file_operations/labels.md) assigned to the current image  
**%T** - complete original title (useful for simply adding a prefix or suffix to the title)  
**%%%%%%** - insert a literal % character  
**%!** - hide empty blocks withing %!...%! (see below)  
  
The **%!** code is special in that it should be used in pairs around the things you want to hide. They will be hidden if all tokens within the block expand to empty values.  
  
Consider "**%!Dimensions: %W x %H%!**", for example: If **%W** and **%H** (width and height) are unavailable (e.g. because the viewer isn't displaying an image) then this will output nothing at all instead of a meaningless *"Dimensions: 0 x 0"*.
