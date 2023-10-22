# Icon Images

As mentioned above, the actual image data for your icons can be supplied in any image format that Directory Opus understands. The most common of these would be JPEG, PNG, GIF and BMP. Any number of separate image files can be used, and each image file can provide one or more icons.

Say you have an image file called “MyIcons.png” that is 100x20 pixels in size, and that contains the imagery for 5 different icons. Each individual icon is therefore 20x20 pixels in size. In the XML definition file, you would have a **set** entry for that image file, and then up to five **icon** entries for each of the icons. The location of the image data for each icon is specified using the **row** and **col** attributes.For example,

    <set size="small" width="20" height="20" filename="MyIcons.png">
    <icon name="icon1" row="1" col="1" />
    <icon name="icon2" row="1" col="2" />
    <icon name="icon3" row="1" col="4" />
    <icon name="icon4" row="1" col="5" />
    </set>

This would add four icons from the image file – the first two and the last two, skipping over the third.

Note that an image file can also contain just a single image. For example, say you have a collection of single image icons that you wish to bundle together as an icon set. You would simply specify multiple **set** nodes, one for each image file, and each **set** node would contain a single **icon** node referring to row 1, column 1.

Images supplied in PNG or GIF format automatically support transparency – GIF supports a single transparent color, and PNG supports full 32 bit alpha. If you wish to provide transparent icons in a different format, you can specify **transparent="yes"** as an attribute of the **set** node. Opus will then make transparent any pixels in the image that have an RGB value of 255,0,255 (#FF00FF).

Filenames which start with “:INTERNAL:” reference internal image resources stored inside of the program. You would not normally use internal images yourself but may see them used in special icon sets, usually created by GP Software.

 
