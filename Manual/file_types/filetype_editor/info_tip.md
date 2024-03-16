# Info Tip

The **Info Tip** page in the [file type editor](../filetype_editor/RAEDME.md) lets you define what is shown on the info tip (the popup tooltip) that's displayed when the mouse hovers over files of this type.

When Opus looks for an info tip to display for a file, it checks file types in the following order:

1.  The specific file type for that file (e.g. for a **.jpg** file this might be the **JPEG Image** file type)
2.  The file type group that contains that file extension (e.g. **Images**)
3.  The **Recognized images** file type if the file is a recognized image file
4.  The **All files** file type (or for a folder, **All folders**)
5.  The **All files and folders** file type.

The first, most specific, info tip found is the one used. So if you want to assign an info tip to all members of a group you can edit the file type group definition, and then override it on a per file-type basis if needed.

![](/Manual/images/media/images_infotip.png) 

The info tip definition (the image above illustrates the default info tip for the **Images** group) uses various **{..}** codes to insert information about the file into the info tip. Each line in the edit field corresponds to a line in the info tip. If a line in the definition uses a code that isn't valid for the specified file (for example, a **.bmp** file doesn't support EXIF metadata in it, and so fields like **{cameramake}** would be empty), the whole line is omitted from the info tip. You can have multiple codes on the one line and in that case, the line is only omitted if all codes on the line are empty.

![](/Manual/images/media/infotip_-_jpeg.png)     ![](/Manual/images/media/infotip_-_bmp.png)

You can see that for the **.jpg** file in the above screenshot, all the EXIF information defined in the info tip is shown, but the info tip for the **.bmp** file simply displays the top line (**{desc}** produces the *800 x 599 x 24 Bitmap Image* description and **{thumbnail}** displays the image's thumbnail).

##### Inserting information

Information about the file is inserted into the info tip using `{ ... }` codes, containing a keyword referring to a file information column.

The keywords used in info tips are the same as used by the [Rename](/Manual/file_operations/renaming_files/RAEDME.md) function when [renaming files using metadata](/Manual/file_operations/renaming_files/advanced_rename/renaming_with_metadata.md), and the **[Set](/Manual/reference/command_reference/internal_commands/set.md)** command when adding and removing columns to the file display. See the [Keywords for Columns](/Manual/reference/metadata_keywords/keywords_for_columns.md) page for a full list of supported keywords.

You can also insert information using the [evaluator](/Manual/evaluator/RAEDME.md).

##### Special code: {foldersize}

This code applies to the info tips for folders, and its use will cause Opus to calculate the total size of the folder when its info tip is displayed. This lets you display the size of a folder by simply hovering over it. You can add the **noprefix** keyword to suppress the default ***Size:*** prefix - for example, `{foldersize:noprefix}`.

##### Special code: {foldercontents}

This code also applies to folders; it will result in Opus displaying the names of the first few files and sub-folders contained in the folder. You can control the output with these keywords:

- **files** and **dirs**: By default, both files and folders are shown. You can use the **files** and **dirs** keywords to limit the contents to just one or the other. For example, `{foldercontents:files}`
- **noprefix**: By default, `Folders:` and `Files:` prefixes are added before each list, respectively. You can use the **noprefix** keyword to suppress this. For example: `{foldercontents:files,noprefix}`
- **singleline**: By default, each file or folder is displayed on a separate line for easy reading. You can use the **singleline** keyword to compact everything into a single line (one line for folders, another for files). For example: `{foldercontents:files:singleline}`
- **indent**: In multi-line mode, each line begins with `    ` (four spaces) by default. In single-line mode, each item is separated by `, `. You can use the **indent** keyword to change both of these. The **indent** keyword must be the last parameter, since it uses everything up to the end of the string. For example: `{foldercontents:indent=--> }` or `{foldercontents:singleline,indent= :: }`
- **maxitems**: To limit the maximum total number of items (files and folders, combined), use the **maxitems** keyword. Where a single **{foldercontents}** tag lists both files and folders, the limit applies to the count of both together, not to each category individually. The default maximum is 10 items in total (files and folders). Note that there is a hard maximum of 20 items *in each category* (files or folders) and thus a hard maximum of 40 items in total. When there are more items than the maximum, the list or lists will be truncated with `...`. For example: `{foldercontents:files,maxitems=20}`
- **maxitemlength**: To limit the maximum length of each individual item, use the **maxitemlength** keyword. Note that there is a hard maximum of 260 characters, and a default limit of 40 characters. When a name is too long, it will be truncated with `...`. For example: `{foldercontents:maxitemlength=20}`

##### Special code: {thumbnail}

This code displays the thumbnail for the file if Opus is able to generate one. You can configure how the thumbnail is displayed by appending a border style value to the code:

      * **{thumbnail:0}** displays the thumbnail with no border (frame) 
      * **{thumbnail:1}** displays the thumbnail with a normal border (this is the default if no value is given) 
      * **{thumbnail:2}** displays a border if the thumbnail does not have an alpha channel. For 32 bit images with an alpha channel (transparency) no border is shown. 
      * **{thumbnail:3}** displays no border for folders, but normal borders for files

Additionally, you can configure the size of the thumbnail. By default thumbnails will appear the same size in the info tip as they do in the file display, but you can append a size value to the code to specify a different size. Note that the border style value must also be provided if you want to provide the size. For example,

      * **{thumbnail:1:512}** displays the thumbnail with normal border and 512 pixels in size (the image will be scaled to preserve the correct aspect ratio) 
      * **{thumbnail:0:64}** displays the thumbnail with no border, 64 pixels in size

##### Special code: {infotip}

This code causes Opus to display the standard, system info tip for the file (if there is one). This would be the text that is shown in the tooltip in Explorer when you hover over the file. The main use for this is to display information from third-party *tooltip shell extensions* that you may have installed.

##### Hide sections

You can create *hide sections* that hide text when certain information isn't available. For example, you could show the GPS coordinates of an image if it has them, but you might not want the labels for those fields to be visible if it doesn't.

Use the code `{! ... }` to open a hide section, and `{!}` to close it. The opening code should contain the names of one or more fields to test for. Field names should be separated by `&` characters. All specified fields must exist for the hide section to be visible. If one or more doesn't, then all text between the open and close of the section will be hidden.

For example,

    {!picwidth&picheight}Size: {picwidth} x {picheight}{!}

This might display, for example, `Size: 1024 x 768` for an image, but would display nothing for a text file.

You can also define hide sections using the [evaluator](/Manual/evaluator/RAEDME.md).

##### HTML markup

Any text you enter into the info tip definition that isn't a **{..}** code is displayed as-is (unless it appears on a line that uses a non-applicable **{..}** code, in which case the whole line is omitted as described above). You can also use some simple HTML-style markup codes to control font styles in the info tip:

- **\<#RRGGBB\>...\</#\>**: This sets the text color for text between the tags. The color is given in [hexadecimal](http://en.wikipedia.org/wiki/Web_colors), e.g. **\<#32CD32\>Hello!\</#\>** would display the text **Hello!** in lime green.
- **\<b\>..\</b\>**: This displays text between the tags in **bold**.
- **\<i\>..\</i\>**: This displays the text between the tags in *italics.*
- **\<u\>..\</u\>**: This underlines the text between the tags.

##### Other information

At the bottom of the info tip page are several buttons:

- **Insert Field**: This displays a drop-down list of all the information fields (arranged by category) that you can use in info tips. This list is also automatically displayed in a pop-up menu when you press the **{** key in the info tip definition field. So don't worry, you don't have to memorise all of the codes!
- **Samples**: This lets you access several sample info tip definitions for reference (the samples are the defaults for the various default file type groups plus generic info tips for other files and folders).
- **Clear**: Clears the info tip definition completely.
- **Never show an InfoTip for this File Type**: If this option is on, the info tip field will be disabled and Opus will be prevented from ever showing an info tip for this type of file (hovering over the file will do nothing).
