# 本地化

Icon Set 格式可选择本地化图标显示名称和自定义图标类别名称。要本地化自定义图标名称，你需要在定义 XML 文件中指定一个或多个 `language_map` 节点。例如：

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

此操作定义了一个包含一个图标的集合，其内部名称为“ftpimage”，默认显示名称为“Upload Image”。此图标置于名为“Image”的自定义类别中。

在英语或除法语或德语以外的任何语言中，Opus 会将“Upload Image (ftpimage)”显示为鼠标悬停在“*选择图标*”对话框中的图标上时的图标名称。但是，由于采用了 `language_map` 节点，德语用户会看到“Hochladen Sie dieses Bild (ftpimage)”，而法语用户会看到“Téléchargez cette image (ftpimage)”。此外，自定义的“Image”类别在德语中会显示为“Bild”。

每个 `language_map` 节点中指定语言的名称必须与 Opus 使用的语言 DLL 的名称（不带扩展名）相同，该名称位于程序目录中的“Languages”子文件夹中。