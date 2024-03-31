# 自动化图像转换任务

使用内部 **[Image](/Manual/reference/command_reference/internal_commands/image.zh.md)** 命令，可以配置按钮和工具栏，以便自动执行各种简单的图像转换功能。这样，您可以只选择有问题的图像文件，然后单击一个按钮执行转换，而无需显示和配置 [图像转换]() 对话框。

下面列出 **Image** 命令的一些示例用法 - 有关如何创建按钮的信息，请参阅 [创建您自己的按钮](/Manual/customize/creating_your_own_buttons/README.zh.md) 页面。

- **Image ROTATE=270 HERE REPLACE**

将选定的图像文件向左旋转 90 度（即顺时针旋转 270 度）。图像被“就地”旋转 - 即，旋转后的文件将被保存到原始文件之上。如果可能，JPEG 图像将无损旋转。  
\* **Image ROTATE=90 HERE REPLACE**

将选定的图像文件向右旋转 90 度。  
\* **Image ROTATE=EXIF HERE REPLACE**

旋转选定的图像文件以补偿 EXIF 标签中存储的方向值。这样，您可以“修正”数码相机上拍摄的照片，但照片旋转时显示不正确。图像将自动旋转至“正确方向”，并且 EXIF 方向标签将被重置。这将替换原始文件。如果选定的文件没有 EXIF 方向标签，它将保持不受影响。  
\* **Image CONVERT=png HERE**

将选定的图像文件转换为 PNG 格式。转换后的图像将保存在与原始图像相同的文件夹中，文件扩展名为 **.png**。  
\* **Image CONVERT=jpg QUALITY=90 HERE**

将选定的图像文件转换为 JPEG 格式，质量为 90%。  
\* **Image CONVERT=jpg WIDTH=256 HEIGHT=256 PRESERVEASPECTRATIO ADDSUFFIX "\_thumb"**

使用选定的图像文件制作 JPEG 缩略图。缩略图的大小将调整为最多 256x256 像素（将保留原始宽高比，因此最终尺寸将取决于原始图像）。缩略图将保存在当前目标文件夹中，并且它们的 Filename 中将附加后缀 **\_thumb**。  
\* **Image CONVERT=png HEIGHT=1200 PRESERVEASPECTRATIO HERE REPLACE**

将选定的图像大小调整为 1200 像素高 - 宽度将根据原始图像的宽高比自动确定。调整了大小的图像文件将以 PNG 格式保存 - 如果原始图像也是 PNG 格式，它们将被替换。