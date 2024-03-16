# Localization

The Icon Set format optionally supports localization of both the icon display names and custom icon category names. To localize your custom icon names, you need to specify one or more \<ib:inline-code\>`language_map`\</ib:inline-code\> nodes in the definition XML file. For example,

    <iconset name="sample">
        <language_map language="deutsch">
            <icon name="ftpimage" display_name="Hochladen Sie dieses Bild" />
            <category name="Image" display_name="Bild" />
        </language_map>
        <language_map language="francais">
            <icon name="ftpimage" display_name="Téléchargez cette image" />
            <category name="Image" display_name="Image" />
        </language_map>
        <set size="small" width="20" height="20" filename="UtilIcons.png">
            <icon name="ftpimage" display_name="Upload Image" row="3" col="1" category="Image" />
        </set>
    </iconset>

This defines a set containing one icon, with the internal name of “ftpimage” and the default display name of “Upload Image”. This icon is placed in a custom category called “Image”.

In English, or any language other than French or German, Opus would display “Upload Image (ftpimage)” as the icon name when hovering over the image in the *Select Icon* dialog. However, thanks to the \<ib:inline-code\>`language_map`\</ib:inline-code\> nodes, German users would see “Hochladen Sie dieses Bild (ftpimage)” and French users “Téléchargez cette image (ftpimage).” Additionally, the custom “Image” category would appear as “Bild” in German.

The name of the language specified in each \<ib:inline-code\>`language_map`\</ib:inline-code\> node must be the same as the name (without extension) of the Language DLL used by Opus, as found in the Languages sub-folder in the program directory.
