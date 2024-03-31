# Image
**Image** 内部命令可用于：

- 更改图片格式
- 调整图片大小和旋转图片
- 使用在线服务上传或同步图片
- 根据图片嵌入的 GPS 信息定位图片

在互动模式下，`Image CONVERT` 命令会显示 [图片转换](/Manual/additional_functionality/image_conversion/README.zh.md) 对话框，让你选择应用于所选图片的转换选项。使用此命令的各种参数可以将图片转换函数自动化。图片转换函数可以将 Opus 能够查看的任何图片格式（包括插件支持的格式）作为输入，但只能以 JPEG、PNG、GIF 或位图格式输出。

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>
ADDSUFFIX</td><td>
/O</td><td>

*(无值)*</td><td>

调整图片大小时，向输出文件名添加后缀。新图片大小由所用的后缀表示。如果图片未调整大小，则不添加后缀。

*示例：* `Image CONVERT=jpg WIDTH=1024 HEIGHT=768 ADDSUFFIX`
</td></tr><tr><td>
</td><td>
</td><td>

*\<后缀\>*</td><td>

向输出文件名添加指定的后缀。

*示例：* `Image CONVERT=jpg WIDTH=128 HEIGHT=128 ADDSUFFIX=thumb`

如果写入新的图片，则使用指定的后缀，但有一些默认情况下不会写入图片的情况，例如将图片转换到原处（而非单独的目标目录）并且源图片已匹配指定条件。如果你需要确保无论如何都创建图片的第二个副本，并将指定的后缀用于修改其名称，那么你应使用关键字 **always：** 为后缀添加前缀。

*示例：* `Image CONVERT=jpg WIDTH=128 HEIGHT=128 ADDSUFFIX=always:thumb`
</td></tr><tr><td>
AS</td><td>
/K</td><td>

*\<输出文件名\>*</td><td>

在转换图片时指定输出文件名。默认情况下，输出文件名与输入文件名相同，有可能包含其他后缀（通过 **ADDSUFFIX** 参数添加）以及不同的文件扩展名，前提是图片已转换为不同格式。

*示例：* `Image CONVERT=jpg AS=thumbnail.jpg WIDTH=128 HEIGHT=128`
</td></tr><tr><td>
BACKGROUND</td><td>
/O</td><td>

\<nobr\>*RRR,GGG,BBB*\</nobr\>  
*(十进制)*  
\<nobr\>*\#RRGGBB*\</nobr\>  
*(十六进制)*\</nobr\></td><td>

当将具有 alpha 通道（透明度）的图片转换为不支持 alpha 通道的格式时，此参数用于指定用于替换透明区域的背景颜色。颜色可以使用十进制或十六进制格式指定。

*示例：* `Image CONVERT=jpg BACKGROUND=#ff8000`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

将 **BACKGROUND=none** 与预设一同指定以覆盖已保存设置。

*示例：* `Image CONVERT PRESET=ScaleAndCrop BACKGROUND=none`
</td></tr><tr><td>
CONVERT</td><td>
/O</td><td>

*(无值)*</td><td>

在没有提供其他参数时，在互动模式下显示 [图片转换](/Manual/additional_functionality/image_conversion/README.zh.md) 对话框。

*示例：* `Image CONVERT`
</td></tr><tr><td>
</td><td>
</td><td>

**jpg**</td><td>

使图片转换函数自动化；转换后的图片将以 JPEG 格式保存。

*示例：* `Image CONVERT=jpg`
</td></tr><tr><td>
</td><td>
</td><td>

**png**</td><td>

转换后的图片将以 PNG 格式保存。

*示例：* `Image ROTATE=EXIF CONVERT=png`
</td></tr><tr><td>
</td><td>
</td><td>

**gif**</td><td>

转换后的图片将以 GIF 格式保存。

*示例：* `Image WIDTH=128 HEIGHT=128 CONVERT=gif`
</td></tr><tr><td>
</td><td>
</td><td>

**bmp**</td><td>

转换后的图片将以 BMP 格式保存。

*示例：* `Image CONVERT=bmp`
</td></tr><tr><td>
CROP</td><td>
/K</td><td>

\<arguments\></td><td>

裁剪所选图片。裁剪参数可以通过多种方式指定：

|                            |                                                                                           |
|----------------------------|-------------------------------------------------------------------------------------------|
| W,H                        | 裁剪为指定大小（宽、高）。裁剪矩形置中于源图片中。  |
| X,Y,W,H                    | 从指定位置 (x,y) 裁剪到指定大小（宽、高）。                      |
| \<nobr\>X,Y-X1,Y1\</nobr\> | 从指定位置 (x,y) 裁剪到指定位置 (x1,y1)。                         |
| W:H                        | 裁剪到指定比率（宽：高）。裁剪矩形置中于源图片中。 |
| X,Y,W:H                    | 从指定位置 (x,y) 裁剪到指定比率（宽：高）。                     |

*示例：* `Image CONVERT CROP=16:9`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

将 **CROP=no** 与预设一同指定以覆盖已保存设置并禁止裁剪。

*示例：* `Image CONVERT PRESET=ScaleAndCrop CROP=no`
</td></tr><tr><td>
FLIP</td><td>
/K</td><td>

**h**</td><td>

水平翻转（镜像）图片。

*示例：* `Image FLIP=h`
</td></tr><tr><td>
</td><td>
</td><td>

**v**</td><td>

垂直翻转图片。

*示例：* `Image FLIP=v ROTATE=90 HERE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

将 **FLIP=no** 与预设一同指定以覆盖已保存设置。

*示例：* `Image CONVERT PRESET=ScaleAndRotate FLIP=no`
</td></tr><tr><td>
FROM</td><td>
/M</td><td>

*\<filename\> ...*</td><td>

指定一个或多个图片文件以执行操作。不使用此参数，命令将对当前所有选定文件执行操作。这是 Image 命令的默认参数，所以你无需指定 FROM 关键字。请记住，如果文件名包含空格，则需要将其放在引号中。

*示例：* `Image CONVERT=png FROM C:\MyPhotos\\.jpg HERE`
</td></tr><tr><td>
HEIGHT</td><td>
/K/N</td><td>

*\<height\>*</td><td>

将图片调整到指定高度。

*示例：* `Image HEIGHT=768 PRESERVEASPECTRATIO CONVERT=jpg`
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(无值)*</td><td>

将转换后的图片写入源文件夹。不使用此参数，转换后的图片将写入当前目标文件夹。

*示例：* `Image CONVERT=bmp WIDTH=128 HEIGHT=128 ADDSUFFIX HERE`
</td></tr><tr><td>
LOCATE</td><td>
/K</td><td>

*\<关键字\>*</td><td>

从嵌入的 GPS 信息中使用第三方映射服务定位所选图片文件在现实世界中的位置。除了 Google 地球（必须安装在你的机器上），所有服务都将打开网络浏览器。

可以通过 **[配置/杂项/高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md): image_locate_services** 配置定位服务列表。默认情况下定义了多项服务，它们列在下方。

如果所选图片没有 GPS 信息，此命令将无法生效。

*示例：* `Image LOCATE=\<关键字\>`
</tr><tr><td>
</td><td>
</td><td>

**bing**</td><td>

使用 Bing 地图定位图像（会在 Web 浏览器中打开）。

*示例：* `Image LOCATE=bing`
</td></tr><tr><td>
</td><td>
</td><td>

**google**</td><td>

使用 Google 地图定位图像（会在 Web 浏览器中打开）。

*示例：* `Image LOCATE=google`
</td></tr><tr><td>
</td><td>
</td><td>

**googleearth**</td><td>

使用 Google 地球定位图像（必须在电脑上安装该软件后才能工作）。支持一次选择多幅图像。

*示例：* `Image LOCATE=googleearth`
</td></tr><tr><td>
</td><td>
</td><td>

**kml**</td><td>

使用电脑上针对** .kml**(*Keyhole Markup Language*) 文件的默认处理程序定位图像。这是 Google 地球使用的格式；实际上，此选项执行的动作与**googleearth** 选项完全相同，只是它并不特别检查 Google Earth 的存在（因此会适用于实现对 *.kml* 文件的默认处理的任何应用）。

*示例：* `Image LOCATE=kml`
</td></tr><tr><td>
</td><td>
</td><td>

**osm**</td><td>

使用 OpenStreetMap 定位图像（会在 Web 浏览器中打开）。

*示例：* `Image LOCATE=osm`
</td></tr><tr><td>
</td><td>
</td><td>

**windowsmaps**</td><td>

使用 Windows 地图（在 Windows 10 中默认包含）定位图像。支持一次选择多幅图像（最多 25 幅）。

*示例：* `Image LOCATE=windowsmaps`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

生成一个菜单，列出已配置的位置服务。从菜单中选择一个项目将启动服务以定位选定的图像。

*示例：* `Image LOCATE=menu`
</td></tr><tr><td>
</td><td>
</td><td>

**nohide**</td><td>

将其与**menu** 结合使用。默认情况下，不可用的服务将从菜单中隐藏 - 添加 **nohide** 参数以禁用它们（而不是隐藏它们）。

*示例：* `Image LOCATE=menu,nohide`
</td></tr><tr><td>
NOADDSUFFIX</td><td>
/S</td><td>

*(无值)*</td><td>

指定 **NOADDSUFFIX** 并结合一个预设以覆盖已保存的设置。

*示例：* `Image CONVERT PRESET=ScaleAndCrop NOADDSUFFIX`
</td></tr><tr><td>
NOAUTORUN</td><td>
/S</td><td>

*(无值)*</td><td>

即使命令行中的其他参数允许图像自动转换，如果指定了 **NOAUTORUN**，那么首先会打开转换对话框。这允许你使用其他参数预先配置对话框，然后手动进行最终调整。

*示例：* `Image CONVERT=png CROP=4:3 NOAUTORUN`
</td></tr><tr><td>
NOENLARGE</td><td>
/O</td><td>

*(无值)*</td><td>

防止图像放大（如果调整大小的操作会引起放大）。如果所选图像的尺寸已经小于指定尺寸，它们将保持不变。

*示例：* `Image CONVERT=jpg WIDTH=1024 HEIGHT=768 NOENLARGE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

指定 **NOENLARGE=no** 并结合一个预设以覆盖已保存的设置。

*示例：* `Image CONVERT PRESET=ScaleAndCrop NOENLARGE=no`
</td></tr><tr><td>
NOLOSSLESS</td><td>
/O</td><td>

*(无值)*</td><td>

禁用 Opus 执行无损 JPEG 旋转的能力。通常，Opus 尽可能无损地旋转 JPEG 图像，但你可能特别想将图像重新压缩到较低质量（使其更小），此关键字允许你执行此操作。即使你只想将 JPEG 图像重新压缩到不同的质量设置，也可以在不执行旋转的情况下使用此功能。

*示例：* `Image CONVERT=jpg QUALITY=50 ROTATE=EXIF NOLOSSLESS`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

指定 **NOLOSSLESS=no** 并结合一个预设以覆盖已保存的设置。

*示例：* `Image CONVERT PRESET=ScaleAndRotate NOLOSSLESS=no`
</td></tr><tr><td>
NOREDUCE</td><td>
/O</td><td>

*(无值)*</td><td>

防止图像缩小（如果调整大小的操作会引起缩小）。如果所选图像的尺寸已经大于指定尺寸，它们将保持不变。

*示例：* `Image CONVERT=jpg WIDTH=800 HEIGHT=600 NOREDUCE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

指定 **NOREDUCE=no** 并结合一个预设以覆盖已保存的设置。

*示例：* `Image CONVERT PRESET=ScaleAndCrop NOREDUCE=no`
</td></tr><tr><td>
NORENAME</td><td>
/S</td><td>

*(无值)*</td><td>

指定 **NORENAME** 并结合一个预设以覆盖已保存的设置。

*示例：* `Image CONVERT PRESET=ScaleAndCrop NORENAME`
</td></tr><tr><td>
NOUSEIMAGEDATA</td><td>
/S</td><td>

*(无值)*</td><td>

当它与 **CONVERT** 参数（在独立图像查看器中）一起使用时，它会覆盖 **@useimagedata** 命令修饰符并使图像转换器从磁盘加载图像，而不是从查看器获取图像。

*示例：* `Image CONVERT NOUSEIMAGEDATA`
</td></tr><tr><td>
PERCENT</td><td>
/K/N</td><td>

*\<调整大小的百分比\>*</td><td>

将图像调整到原始尺寸的指定百分比。它既可以放大图像，也可以缩小图像。

你可以将其设置为 0 或 100 以禁用按比例调整大小并覆盖已保存预设中的设置。

*示例：* `Image CONVERT=jpg PERCENT=125`
</td></tr><tr><td>
PRESERVEASPECTRATIO</td><td>
/O</td><td>

*(无值)*</td><td>

调整图像大小时保留原始纵横比。输出宽度或高度将自动调整以确保维持纵横比。使用此开关意味着你只需提供新宽度或新高度即可调整图像大小 - 将自动计算这个缺少的尺寸。

*示例：* `Image CONVERT=png WIDTH=1280 PRESERVEASPECTRATIO HERE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

指定 **PRESERVEASPECTRATIO=no** 并结合一个预设以覆盖已保存的设置。

*示例：* `Image CONVERT PRESET=ScaleAndCrop PRESERVEASPECTRATIO=no`
</td></tr><tr><td>
PRESERVEDATE</td><td>
/S</td><td>

*(无值)*</td><td>

在转换图像时，此选项保留原始文件的*创建* 和*上次修改* 时间戳。默认情况下，如果不指定此选项，*上次修改* 时间戳将更新为当前时间，如果操作创建了一个新文件，*创建* 时间戳也会更新为当前时间。（直接用 **REPLACE HERE** 覆盖原始文件的“就地”转换操作将保留*创建*时间戳，而不管此选项如何。）

*示例：* `Image ROTATE=EXIF REPLACE HERE PRESERVEDATE`
</td></tr><tr><td>
PRESET</td><td>
/K</td><td>

*\<名称\>*</td><td>

对选定的图像调用已保存的预设。可以通过用户界面（用其他参数单独运行 `Image CONVERT`）创建预设 - 一旦保存，就可以使用 **PRESET** 参数自动执行它们。所提供的任何其他参数都将覆盖预设中的设置。

*示例：* `Image CONVERT=jpg PRESET=HDResize`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

使用它以默认设置显示转换对话框。否则，如果未指定预设，将加载上次使用的设置。

*示例：* `Image CONVERT PRESET=!default`
</td></tr><tr><td>
</td><td>
</td><td>

**!list**</td><td>

生成已保存预设的列表。从列表中选择一个预设将在所有选定的图片上运行它。

*示例：* `Image CONVERT PRESET=!list`
</td></tr><tr><td>
</td><td>
</td><td>

**!menu**</td><td>

生成已保存预设的菜单。从菜单中选择一个预设将在所有选定的图片上运行它。

*示例：* `Image CONVERT PRESET=!menu`
</td></tr><tr><td>
质量</td><td>
/K/N</td><td>

*\<quality\>*</td><td>

当以 JPEG 格式保存图片时，指定质量 (1 - 100)。

*示例：* `Image CONVERT=jpg QUALITY=10 NOLOSSLESS`
</td></tr><tr><td>
替换</td><td>
/O</td><td>

*(无值)*</td><td>

自动替换目标文件夹中已存在的文件。将其与 **HERE** 参数一起使用，可以在原地转换一张图片。如果输出文件名和输入文件名相同，则此操作才适用；如果输出文件名已更改（通过 **ADDSUFFIX** 等），且文件已存在，系统仍会提示您进行确认。

*示例：* `Image ROTATE=EXIF REPLACE`
</td></tr><tr><td>
</td><td>
</td><td>

**always**</td><td>

始终替换现有文件，即使输出文件名已更改。

*示例：* `Image PERCENT=50 ADDSUFFIX HERE REPLACE=always`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

与预设一起指定 **REPLACE=no** 来覆盖已保存设置。

*示例：* `Image CONVERT PRESET=ScaleAndCrop REPLACE=no`
</td></tr><tr><td>
</td><td>
</td><td>

**readonly**</td><td>

替换现有文件（即使它们是只读文件）且不提示。（如果在「配置」中关闭了只读提示，这不起作用。）

*示例：* `Image PERCENT=50 REPLACE=readonly`

可以用 **always** 组合：

*示例：* `Image PERCENT=50 REPLACE=always,readonly`
</td></tr><tr><td>
旋转</td><td>
/K</td><td>

*\<angle\>*</td><td>

旋转图像指定的角度（以度为单位）。正值顺时针旋转，负值逆时针旋转。

你可以将此设置为 0 以禁用旋转，并覆盖预设中已保存的设置。

*示例：* `Image ROTATE=90 HERE REPLACE`
</td></tr><tr><td>
</td><td>
</td><td>

**EXIF**</td><td>

使用存储在图片 EXIF 标记中的旋转（方向）信息来旋转图像。这样做的效果就是抵消相机的初始方向，从而得到一幅垂直的图像。如果选定的图像没有 EXIF 旋转标记，此操作不会产生任何效果。

*示例：* `Image ROTATE=EXIF HERE REPLACE`
</td></tr><tr><td>
</td><td>
</td><td>

**RESET**</td><td>

实际上不会旋转图像数据，但会清除图像 EXIF 标记中的旋转（方向）字段。

*示例：* `Image ROTATE=RESET HERE REPLACE`
</td></tr><tr><td>
到</td><td>
/K</td><td>

*\<destination path\>*</td><td>

为转换的图像指定目标路径。如果路径包含空格，请记住用引号引起来。如果没有提供，并且未指定 **HERE** 参数，则当前的目标文件列表将用作目标路径。

*示例：* `Image CONVERT=jpg WIDTH=80 HEIGHT=80 TO "C:\Photos\Image Thumbnails"`
</td></tr><tr><td>
TODEST</td><td>
/S</td><td>

*(无值)*</td><td>

强制输出转到当前目标文件夹。这可以让你覆盖预设中的已保存目标。
</td></tr><tr><td>
NOADDSUFFIX</td><td>
/S</td><td>

*(无值)*</td><td>

与预设一起指定 **NOADDSUFFIX** 来覆盖已保存的设置。

*示例：* `Image CONVERT PRESET=ScaleAndCrop TODEST`
</td></tr><tr><td>
宽度</td><td>
/K/N</td><td>
</td><td>

将图像调整到指定宽度。

*示例：* `Image WIDTH=1024 PRESERVEASPECTRATIO CONVERT=jpg`
</td></tr></tbody>
</table>