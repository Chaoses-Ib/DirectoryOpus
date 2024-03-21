# Automated image conversion tasks

Using the internal **[Image](/Manual/reference/command_reference/internal_commands/image.md)** command, it is possible to configure buttons and toolbars that automate various simple image conversion functions. That way, you can simply select the image files in question and click on a button to perform the conversion, without having to display and configure the [Image Conversion]() dialog.

Listed below are some example uses of the **Image** command - please see the [Creating your own buttons](/Manual/customize/creating_your_own_buttons/README.md) page for information on how to create a button.

- **Image ROTATE=270 HERE REPLACE**

Rotates selected image files 90 degrees to the left (i.e. 270 degrees clock-wise). The images are rotated "in-place" - that is, the rotated file will be saved over the top of the original. JPEG images will be rotated losslessly if possible.  
\* **Image ROTATE=90 HERE REPLACE**

Rotates selected image files 90 degrees to the right.  
\* **Image ROTATE=EXIF HERE REPLACE**

Rotates selected image files to compensate for the orientation value stored in the EXIF tag. This lets you "correct" photos taken on digital cameras that appear incorrectly rotated. The image will be automatically rotated to be the "right way up" and the EXIF orientation tag will be reset. This will replace the original files. If a selected file does not have an EXIF orientation tag it will be unaffected.  
\* **Image CONVERT=png HERE**

Converts selected image files to PNG format. The converted images will be saved in the same folder as the originals, with **.png** file extensions.  
\* **Image CONVERT=jpg QUALITY=90 HERE**

Converts selected image files to JPEG format, at 90% quality.  
\* **Image CONVERT=jpg WIDTH=256 HEIGHT=256 PRESERVEASPECTRATIO ADDSUFFIX "\_thumb"**

Makes JPEG thumbnails from selected image files. The thumbnails will be sized to at most 256x256 pixels (the original aspect ratio will be preserved, so the final dimensions will depend upon the original image). The thumbnails will be saved in the current destination folder, and will have the suffix **\_thumb** appended to their filename.  
\* **Image CONVERT=png HEIGHT=1200 PRESERVEASPECTRATIO HERE REPLACE**

Resizes selected images to 1200 pixels high - the width will be determined automatically based on the aspect ratio of the original image. The resized image files will be saved in PNG format - if the original images were also PNG format they will be replaced.
