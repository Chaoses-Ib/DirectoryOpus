# Image Conversion

The Image Converter is a simple tool that provides a quick way to perform basic image conversion tasks:

- It can convert from any image format Opus understands to **BMP**, **GIF**, **PNG** and **JPG** formats.
- It can rotate images in 90 degree increments, and also automatically rotate to compensate for EXIF orientation.
- It can resize or enlarge images, by a percentage or to an absolute size, optionally retaining the original aspect ratio.

To access the image converter, select the image or images you want to convert, and choose the **Convert** command from the **Tools / Convert Images** menu. The **Images** [file type group](/Manual/file_types/file_type_groups.md) also adds a command to the context menu of common image formats, so you can also access the converter by right-clicking on an image file and choosing the **Convert Image** command.

![](/Manual/images/media/image_conversion.jpg) 

The image converter displays a thumbnail of the next image to be processed. You can enable some or all of the following options at once; for example, you can rotate and resize in the one step.

- **Convert**: Set this option on if you want to convert the image to a different format. Opus is able to save images in **Bitmap**, **GIF**, **PNG** and **JPEG** formats. If the source image is not already in one of these then you have to choose an output format to save in, but if the source image is already one of these formats then you can leave the **Convert** option disabled.

When converting to JPEG format, you must choose a **JPEG Quality** setting from **0** to **100**. JPEG is a [lossy compression](http://en.wikipedia.org/wiki/Lossy_compression) method, and the quality setting specifies how accurately the converted image will represent the source image data. The higher the number the better the quality will be, but also the larger the resulting file size.

When converting from a format that supports an alpha (transparency) channel, like PNG, you can specify the **Alpha conversion background color**. This color will be used as the background color if saving out in a format that doesn't support the alpha channel.  
\* **Rotate**: Turn this on if you want to rotate the image. You can select the amount of rotation to apply from **90**, **180** and **270** degrees - the thumbnail preview will update in real time to reflect your setting. If the source image has EXIF orientation information saved within it (e.g. a photo from a digital camera that was taken as portrait instead of landscape), you can also select **Use EXIF information** from the drop-down. If this is selected then Opus will use the EXIF information to automatically rotate the image to its correct orientation. If the image has no EXIF information or is already in the correct orientation, the output image won't be rotated.

Selecting **Reset** from the drop-down has the opposite effect to **Use EXIF information** - instead of using the EXIF orientation to rotate the image, Opus will leave the image alone and reset the EXIF orientation field to 0. Again, if the image has no EXIF information in it this option will not modify the image.

Opus supports lossless JPEG rotation if possible. Normally when you load and re-save a JPEG image, there is a reduction in quality of the new image. This can be hard to notice at first but errors accumulate, and a JPEG file that has been repeatedly decompressed and recompressed will often look quite a lot worse than the original. The JPEG format allows for image rotations to be lossless (i.e. no reduction in quality) if certain conditions are met; namely, the width and height of the image must be an exactly multiple of the "block size" the image has been saved in (usually 8x8 or 16x16). Luckily, most digital cameras do produce images of these dimensions. You don't need to do anything special in Opus to enable lossless rotation - if a JPEG image can be rotated losslessly it will be.  
\* **Resize**: Turn this option on if you want to resize the image. You can select some predefined output sizes, or reduction or enlargement ratios from the drop-down, or choose **Custom size** and enter your own width and height values (specified in pixels).

The **Add filename suffix** option causes Opus to automatically add an appropriate suffix to the filename when it saves the output file. For example, if you resized **IMG_2483.jpg** to 150% of the original size, the output file would be called **IMG_2483-150%.jpg**.

Turn on the **Preserve aspect ratio** option to avoid changing the aspect ratio of the image when it's resized. Opus will adjust the output dimensions to keep the same ratio between width and height as the source image.  
\* **Write converted images to destination folder**: Normally Opus will save the converted images in the same folder as the source images. If you turn this option on Opus will instead save the converted images to the [current destination](/Manual/basic_concepts/source_and_destination.md) file display. If you leave this option off, and the output filename isn't changed because of the **Add filename suffix** option (above), the original image file will be overwritten. You will be prompted for confirmation (and given a chance to change the output filename manually) in this case.

When you have set your conversion parameters as desired, click the **OK** button to convert the current image. If you originally selected multiple images, you can apply the same conversion to all of them (as a batch operation) by clicking the **All** button instead. If you click **OK** and have multiple images selected, the first image will be processed, and the image conversion dialog will then re-open for the second image.

More:

[Automated image conversion tasks](/Manual/additional_functionality/image_conversion/automated_image_conversion_tasks.md)  
