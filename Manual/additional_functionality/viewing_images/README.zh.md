# 查看图像

Opus 具有两个主要图像查看器。两个查看器均可用于查看图像、电影、文档和其它格式，这些格式存在插件。

### 查看器窗格

此程序集成了 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md)，该窗格嵌入在文件窗口中：

![](/Manual/images/media/13/viewer_pane.png)

### 单独查看器

这里还有单独的（浮动）图像查看器。

![](/Manual/images/media/13/standalone_viewer.png)

主要区别在于 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md) 绑定到文件窗口，而单独查看器几乎像独立实用程序一样。单独查看器还具有基本的图像编辑功能，而查看器窗格没有。

### 访问单独查看器

有数种方式可用于访问单独查看器：

- 如果在配置中“[文件操作/对文件双击](/Manual/preferences/preferences_categories/file_operations/double-click_files/README.zh.md)”页上的 **使用内部图片查看器** 选项已开启，那么双击可识别的图像文件，将用单独查看器将其打开。

- 默认工具栏上的 **幻灯片放映** 按钮将使用单独查看器启动当前文件夹中所有图像的幻灯片放映。幻灯片放映的速度在配置的 **[幻灯片放映](/Manual/preferences/preferences_categories/viewer/standalone_viewer/slideshow.zh.md)** 页中进行控制。

- 内部 **[显示](/Manual/reference/command_reference/internal_commands/show.zh.md)** 命令将在单独查看器中显示选定的文件。此命令在附加到 **幻灯片放映** 按钮的的下拉菜单中可用。

- 从 Opus 外部，可以使用 `d8viewer.exe` 或 `dopusrt.exe /show` 命令用 Opus 查看器打开文件。

### 单独查看器的选项

有许多选项可用于控制单独查看器的外观和行为。这些选项可在配置的 **[查看器](/Manual/preferences/preferences_categories/viewer/README.zh.md)** 类别中找到。默认情况下，查看器将：

- 自动调整大小以适合每张图片 - 在浏览图像时，如果需要，窗口将调整大小以显示图片。
- 在当前显示器上居中打开。
- 在图片周围显示边框（如上屏摄所示）。
- 在查看图像时显示或隐藏滚动条。
- 在通过双击图像文件打开时，自动生成文件夹中所有其它图片的列表（当达到开头或结尾时，列表还有额外的换行选项）。
- 自动旋转图像以补偿 EXIF 方向标记，该标记由大多数数码相机保存。

所有这些选项均可通过配置进行更改。

更多内容：  
[查看器鼠标、键和工具栏](/Manual/additional_functionality/viewing_images/viewer_keys_and_toolbar.zh.md)  
[图像标记](/Manual/additional_functionality/viewing_images/image_marking.zh.md)