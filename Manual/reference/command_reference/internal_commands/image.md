# Image

The **Image** internal command can be used to:

- Change the format of images
- Resize and rotate images
- Upload or synchronize images with an online service
- Locate an image using its embedded GPS information

The `Image CONVERT` command displays the [image conversion](/Manual/additional_functionality/image_conversion/README.md) dialog in interactive mode, letting you select the conversion options to apply to selected images. Using the various arguments of this command it is possible to automate the image conversion function. The image conversion function can accept as input any image format that Opus is able to view (including those supported by plugins), but can only output in JPEG, PNG, GIF or Bitmap formats.

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>
ADDSUFFIX</td><td>
/O</td><td>

*(no value)*</td><td>

Add a suffix to the output filename when resizing images. The suffix used indicates the new image size. If the image is not resized, no suffix is added.

*Example:* `Image CONVERT=jpg WIDTH=1024 HEIGHT=768 ADDSUFFIX`
</td></tr><tr><td>
</td><td>
</td><td>

*\<suffix\>*</td><td>

Adds the specified suffix to the output filename.

*Example:* `Image CONVERT=jpg WIDTH=128 HEIGHT=128 ADDSUFFIX=thumb`

The specified suffix is used provided a new image is written, but there are cases where no image will be written by default, such as when converting images in-place (not to a separate destination directory) and the source image already matches the specified criteria. If you need to ensure that a second copy of the image is created no matter what, using the specified suffix to modify its name, then you should prefix the suffix with the keyword **always:**.

*Example:* `Image CONVERT=jpg WIDTH=128 HEIGHT=128 ADDSUFFIX=always:thumb`
</td></tr><tr><td>
AS</td><td>
/K</td><td>

*\<output filename\>*</td><td>

Specify the output filename when converting images. By default the output filename is the same as the input filename, with the possibility of an additional suffix (with the **ADDSUFFIX** argument) and a different file extension if the image has been converted to a different format.

*Example:* `Image CONVERT=jpg AS=thumbnail.jpg WIDTH=128 HEIGHT=128`
</td></tr><tr><td>
BACKGROUND</td><td>
/O</td><td>

\<nobr\>*RRR,GGG,BBB*\</nobr\>  
*(decimal)*  
\<nobr\>*\#RRGGBB*\</nobr\>  
*(hexadecimal)*\</nobr\></td><td>

When an image with an alpha channel (transparency) is converted to a format that doesn't support the alpha channel, this argument is used to specify the background color that replaces the transparent area. The color can be specified in either decimal or hex format.

*Example:* `Image CONVERT=jpg BACKGROUND=#ff8000`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

Specify **BACKGROUND=none** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndCrop BACKGROUND=none`
</td></tr><tr><td>
CONVERT</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the [image conversion](/Manual/additional_functionality/image_conversion/README.md) dialog in interactive mode when no other arguments are provided.

*Example:* `Image CONVERT`
</td></tr><tr><td>
</td><td>
</td><td>

**jpg**</td><td>

Automates the image conversion function; the converted image will be saved in JPEG format.

*Example:* `Image CONVERT=jpg`
</td></tr><tr><td>
</td><td>
</td><td>

**png**</td><td>

The converted image will be saved in PNG format.

*Example:* `Image ROTATE=EXIF CONVERT=png`
</td></tr><tr><td>
</td><td>
</td><td>

**gif**</td><td>

The converted image will be saved in GIF format.

*Example:* `Image WIDTH=128 HEIGHT=128 CONVERT=gif`
</td></tr><tr><td>
</td><td>
</td><td>

**bmp**</td><td>

The converted image will be saved in BMP format.

*Example:* `Image CONVERT=bmp`
</td></tr><tr><td>
CROP</td><td>
/K</td><td>

\<arguments\></td><td>

Crops selected images. The crop parameters can be specified in several ways:

|                            |                                                                                           |
|----------------------------|-------------------------------------------------------------------------------------------|
| W,H                        | Crop to specified size (width,height). Centers the crop rectangle in the original image.  |
| X,Y,W,H                    | Crop from specified position (x,y) to specified size (width,height).                      |
| \<nobr\>X,Y-X1,Y1\</nobr\> | Crop from specified position (x,y) to specified position (x1,y1).                         |
| W:H                        | Crop to specified ratio (width:height). Centers the crop rectangle in the original image. |
| X,Y,W:H                    | Crop from specified position (x,y) to specified ratio (width:height).                     |

*Example:* `Image CONVERT CROP=16:9`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Specify **CROP=no** in conjunction with a preset to override the saved setting and disable cropping.

*Example:* `Image CONVERT PRESET=ScaleAndCrop CROP=no`
</td></tr><tr><td>
FLIP</td><td>
/K</td><td>

**h**</td><td>

Flip (mirror) the image horizontally.

*Example:* `Image FLIP=h`
</td></tr><tr><td>
</td><td>
</td><td>

**v**</td><td>

Flip the image vertically.

*Example:* `Image FLIP=v ROTATE=90 HERE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Specify **FLIP=no** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndRotate FLIP=no`
</td></tr><tr><td>
FROM</td><td>
/M</td><td>

*\<filename\> ...*</td><td>

Specify the image file or files to operate on. Without this argument the command will operate on all currently selected files. This is the default argument for the Image command and so you do not need to specify the FROM keyword. Remember that if the filename contains a space it needs to be enclosed in quotes.

*Example:* `Image CONVERT=png FROM C:\MyPhotos\\.jpg HERE`
</td></tr><tr><td>
HEIGHT</td><td>
/K/N</td><td>

*\<height\>*</td><td>

Resize the image to the specified height.

*Example:* `Image HEIGHT=768 PRESERVEASPECTRATIO CONVERT=jpg`
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(no value)*</td><td>

Write converted images to the source folder. Without this argument converted images are written to the current destination folder.

*Example:* `Image CONVERT=bmp WIDTH=128 HEIGHT=128 ADDSUFFIX HERE`
</td></tr><tr><td>
LOCATE</td><td>
/K</td><td>

*\<keyword\>*</td><td>

Locates the real-world position of the selected image file from its embedded GPS information, using a third-party mapping service. With the exception of Google Earth (which must be installed on your machine), all services open a web browser.

The list of location services is configurable via **[Preferences / Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md): image_locate_services.** Several services are defined by default, these are listed below.

If the selected image does not have GPS information this command will have no effect.

*Example:* `Image LOCATE=\<keyword\>`
</td></tr><tr><td>
</td><td>
</td><td>

**bing**</td><td>

Locates the image using Bing maps (will open in a web browser).

*Example:* `Image LOCATE=bing`
</td></tr><tr><td>
</td><td>
</td><td>

**google**</td><td>

Locates the image using Google maps (will open in a web browser).

*Example:* `Image LOCATE=google`
</td></tr><tr><td>
</td><td>
</td><td>

**googleearth**</td><td>

Locates the image using Google Earth (the software must be installed on your computer for this to work). Supports multiple images selected at once.

*Example:* `Image LOCATE=googleearth`
</td></tr><tr><td>
</td><td>
</td><td>

**kml**</td><td>

Locates the image using the default handler for **.kml** (*Keyhole Markup Language*) files on your computer. This is the format Google Earth uses; indeed, this option does exactly the same thing as the **googleearth** option does except that it doesn't specifically check for the existence of Google Earth (and so will work with any app that implements default handling for *.kml* files).

*Example:* `Image LOCATE=kml`
</td></tr><tr><td>
</td><td>
</td><td>

**osm**</td><td>

Locates the image using Open Street Map (will open in a web browser).

*Example:* `Image LOCATE=osm`
</td></tr><tr><td>
</td><td>
</td><td>

**windowsmaps**</td><td>

Locates the image using Windows Maps (included by default in Windows 10). Supports multiple images selected at once (up to 25 maximum).

*Example:* `Image LOCATE=windowsmaps`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

Generates a menu listing the configured location services. Selecting an item from the menu will launch the service to locate the selected image.

*Example:* `Image LOCATE=menu`
</td></tr><tr><td>
</td><td>
</td><td>

**nohide**</td><td>

Use this in conjunction with **menu**. By default services that are unavailable will be hidden from the menu - add the **nohide** parameter to disable them rather than hiding them.

*Example:* `Image LOCATE=menu,nohide`
</td></tr><tr><td>
NOADDSUFFIX</td><td>
/S</td><td>

*(no value)*</td><td>

Specify **NOADDSUFFIX** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndCrop NOADDSUFFIX`
</td></tr><tr><td>
NOAUTORUN</td><td>
/S</td><td>

*(no value)*</td><td>

Even if the other arguments on the command line would allow for automated image conversion, if **NOAUTORUN** is specified the conversion dialog will open first. This lets you use the other arguments to pre-configure the dialog but then make final adjustments manually.

*Example:* `Image CONVERT=png CROP=4:3 NOAUTORUN`
</td></tr><tr><td>
NOENLARGE</td><td>
/O</td><td>

*(no value)*</td><td>

Prevents images from being enlarged if the resize operation would otherwise cause this. Selected images that are already smaller than the specified size will remain untouched.

*Example:* `Image CONVERT=jpg WIDTH=1024 HEIGHT=768 NOENLARGE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Specify **NOENLARGE=no** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndCrop NOENLARGE=no`
</td></tr><tr><td>
NOLOSSLESS</td><td>
/O</td><td>

*(no value)*</td><td>

Disables the ability of Opus to perform lossless JPEG rotation. Normally Opus will rotate JPEG images losslessly if possible, but you may specifically want to recompress the image to a lower quality (to make it smaller) and this keyword allows you to do that. You can also use this without performing a rotation, if all you want to do is recompress a JPEG image to a different quality setting.

*Example:* `Image CONVERT=jpg QUALITY=50 ROTATE=EXIF NOLOSSLESS`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Specify **NOLOSSLESS=no** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndRotate NOLOSSLESS=no`
</td></tr><tr><td>
NOREDUCE</td><td>
/O</td><td>

*(no value)*</td><td>

Prevents images from being reduced in size if the resize operation would otherwise cause this. Selected images that are already larger than the specified size will remain untouched.

*Example:* `Image CONVERT=jpg WIDTH=800 HEIGHT=600 NOREDUCE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Specify **NOREDUCE=no** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndCrop NOREDUCE=no`
</td></tr><tr><td>
NORENAME</td><td>
/S</td><td>

*(no value)*</td><td>

Specify **NORENAME** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndCrop NORENAME`
</td></tr><tr><td>
NOUSEIMAGEDATA</td><td>
/S</td><td>

*(no value)*</td><td>

When used with the **CONVERT** argument (in the standalone image viewer), overrides the **@useimagedata** command modifier and makes the image converter load the image from disk rather than obtaining it from the viewer.

*Example:* `Image CONVERT NOUSEIMAGEDATA`
</td></tr><tr><td>
PERCENT</td><td>
/K/N</td><td>

*\<resize percent\>*</td><td>

Resize the image to the specified percentage of the original size. This can enlarge images as well as reduce them.

You can set this to 0 or 100 to disable percentage resizing and override the settings in a saved preset.

*Example:* `Image CONVERT=jpg PERCENT=125`
</td></tr><tr><td>
PRESERVEASPECTRATIO</td><td>
/O</td><td>

*(no value)*</td><td>

Preserve the original aspect ratio when resizing images. The output width or height will be automatically adjusted to ensure the aspect ratio is maintained. Using this switch means you can resize an image by just supplying a new width or a new height - this missing dimension will be calculated automatically.

*Example:* `Image CONVERT=png WIDTH=1280 PRESERVEASPECTRATIO HERE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Specify **PRESERVEASPECTRATIO=no** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndCrop PRESERVEASPECTRATIO=no`
</td></tr><tr><td>
PRESERVEDATE</td><td>
/S</td><td>

*(no value)*</td><td>

When converting images, this option preserves the *creation* and *last modified* timestamps of the original file. By default, when this option is not specified, the *last modified* timestamp will be updated to the current time, as will the *creation* timestamp if the operation creates a new file. (Operations which convert an existing file "in place", overwriting the original with **REPLACE HERE**, will preserve the *creation* timestamp regardless of this option.)

*Example:* `Image ROTATE=EXIF REPLACE HERE PRESERVEDATE`
</td></tr><tr><td>
PRESET</td><td>
/K</td><td>

*\<name\>*</td><td>

Invokes a saved preset on selected images. Presets can be created via the user interface (run `Image CONVERT` by itself with no other arguments) - once saved, they can be automated using the **PRESET** argument. Any other supplied arguments will override the settings in the preset.

*Example:* `Image CONVERT=jpg PRESET=HDResize`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

Use this to display the conversion dialog with its default settings. Otherwise, if no preset is specified, the last used settings are loaded.

*Example:* `Image CONVERT PRESET=!default`
</td></tr><tr><td>
</td><td>
</td><td>

**!list**</td><td>

Generates a list of saved presets. Selecting a preset from the list will run it on all selected images.

*Example:* `Image CONVERT PRESET=!list`
</td></tr><tr><td>
</td><td>
</td><td>

**!menu**</td><td>

Generates a menu of saved presets. Selecting a preset from the menu will run it on all selected images.

*Example:* `Image CONVERT PRESET=!menu`
</td></tr><tr><td>
QUALITY</td><td>
/K/N</td><td>

*\<quality\>*</td><td>

Specify the quality (1 - 100) when an image is saved in JPEG format.

*Example:* `Image CONVERT=jpg QUALITY=10 NOLOSSLESS`
</td></tr><tr><td>
REPLACE</td><td>
/O</td><td>

*(no value)*</td><td>

Automatically replaces existing files in the destination folder. Use this in conjunction with the **HERE** argument to convert an image "in-place". This only applies if the output filename is the same as the input filename - if the output filename has changed (via **ADDSUFFIX**, etc) and the file already exists, you will still be prompted for confirmation.

*Example:* `Image ROTATE=EXIF REPLACE`
</td></tr><tr><td>
</td><td>
</td><td>

**always**</td><td>

Always replace existing files, even if the output filename has changed.

*Example:* `Image PERCENT=50 ADDSUFFIX HERE REPLACE=always`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Specify **REPLACE=no** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndCrop REPLACE=no`
</td></tr><tr><td>
</td><td>
</td><td>

**readonly**</td><td>

Replace existing files, even if they are read-only, without prompting. (Has no effect if read-only prompts are turned off in Preferences.)

*Example:* `Image PERCENT=50 REPLACE=readonly`

Can be combined with **always**:

*Example:* `Image PERCENT=50 REPLACE=always,readonly`
</td></tr><tr><td>
ROTATE</td><td>
/K</td><td>

*\<angle\>*</td><td>

Rotate the image the specified angle (in degrees). Positive values rotate clock-wise, negative values counter-clockwise.

You can set this to 0 to disable rotation and override the saved setting within a preset.

*Example:* `Image ROTATE=90 HERE REPLACE`
</td></tr><tr><td>
</td><td>
</td><td>

**EXIF**</td><td>

Uses the rotation (orientation) information stored in the images' EXIF tags to rotate the image. The effect of this is to negate the original orientation of the camera, resulting in a "right way up" image. If the selected image does not have an EXIF rotation tag this operation has no effect.

*Example:* `Image ROTATE=EXIF HERE REPLACE`
</td></tr><tr><td>
</td><td>
</td><td>

**RESET**</td><td>

Does not actually rotate the image data, but will clear out the rotation (orientation) field from the images' EXIF tags.

*Example:* `Image ROTATE=RESET HERE REPLACE`
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<destination path\>*</td><td>

Specifies the destination path for converted images. Remember to enclose the path in quotes if it contains spaces. If not provided, and the **HERE** argument is not specified, the current destination file display will be used as the target path.

*Example:* `Image CONVERT=jpg WIDTH=80 HEIGHT=80 TO "C:\Photos\Image Thumbnails"`
</td></tr><tr><td>
TODEST</td><td>
/S</td><td>

*(no value)*</td><td>
Forces the output to go to the current destination folder. This lets you override the saved destination within a preset.
</td></tr><tr><td>
NOADDSUFFIX</td><td>
/S</td><td>

*(no value)*</td><td>

Specify **NOADDSUFFIX** in conjunction with a preset to override the saved setting.

*Example:* `Image CONVERT PRESET=ScaleAndCrop TODEST`
</td></tr><tr><td>
WIDTH</td><td>
/K/N</td><td>
</td><td>

Resize the image to the specified width.

*Example:* `Image WIDTH=1024 PRESERVEASPECTRATIO CONVERT=jpg`
</td></tr></tbody>
</table>

