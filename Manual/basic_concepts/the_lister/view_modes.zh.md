# 视图模式

![](/Manual/images/media/13/view_mode_menu.png)

文件列表模式可以多种方式显示文件和文件夹。您可以使用默认工具栏上的 **视图** 下拉菜单来改变视图模式。

# **视图** 菜单右侧的三个按钮提供了对最常用的视图模式的快速访问：

- ![](/Manual/images/media/13/detailsbutton.png) **详细信息**
- ![](/Manual/images/media/13/thumbtailsbutton.png) **详情 + 缩略图**
- ![](/Manual/images/media/13/thumbnailsbutton.png) **缩略图**

您可以使用 [文件夹格式](../folder_options/README.zh.md) 系统自动将视图模式应用到特定文件夹。例如，您可以让 Opus 自动以缩略图模式显示您的图片库。

在 **不** 显示文件名以外任何信息的模式中，您可以将鼠标悬停在文件上以查看其信息提示 (提示)。信息提示通常会向您显示有关文件的大量相关信息，您可以在 [文件类型](/Manual/file_types/filetype_editor/info_tip.zh.md) 对话框中精确配置显示的内容。

### 大图标

使用大图标显示文件夹内容。

![](/Manual/images/media/13/view_mode_-_large_icons.png)

“大”图标大小由 Windows 本身定义；这通常是 32 x 32 像素（针对系统 DPI 进行缩放）。

### 小图标

使用小图标显示文件夹内容。

![](/Manual/images/media/13/view_mode_-_small_icon.png)

“小”图标大小由 Windows 定义；这通常是 16 x 16 像素（针对系统 DPI 进行缩放）。

### 列表

类似于小图标，此模式以小图标和标签展示文件夹内容。

![](/Manual/images/media/13/view_mode_-_list.png)

这种视图模式受到很多人的欢迎，因为它同时在每个文件列表中显示最多的文件。该模式中的布局不同于几乎所有其它模式 - 而不是从左到右，然后从上到底显示图标，这个顺序是倒置的 - 文件以向下延伸到文件列表中的列展示，显示垂直而不是水平滚动。

### 详细信息

以表格的形式显示文件夹内容，每行代表一个文件，每列代表有关每个文件的信息。

![](/Manual/images/media/13/view_mode_-_details_001.png)

此模式除了文件名外，还可以显示每列有关每个文件的其它信息列。您可以使用 **[文件夹格式](../folder_options/README.zh.md)** 系统选择要显示哪些列。请参阅 **[文件列表模式 / 详细信息模式](/Manual/preferences/preferences_categories/file_display_modes/details_mode.zh.md)** 偏好设置页面，了解详细模式下可配置的设置说明。您还可以配置网格线等内容，以便在列表中明显界定项目。

在 **详细信息** 模式中，您可以按住 <kbd>Ctrl</kbd> 键并转动鼠标滚轮以增加或减小用于显示文件夹内容的字体大小。

### 详情 + 缩略图

这不是严格意义上的视图模式——相反，这是标准 **详细信息** 模式，添加了 **缩略图** 列。

![](/Manual/images/media/13/detailsthumbnails.png)

列的宽度决定了缩略图的大小——可以使用 [文件列表列 / 外观](/Manual/preferences/preferences_categories/file_display_columns/appearance.zh.md) 偏好设置页面上的 **默认宽度** 选项设置默认列宽。您可以将 *缩略图* 列放置在您喜欢的任何位置，但如果它紧贴 *名称* 列，Opus 会将两者视为在选择和高亮显示时单列（如上图所示）。

**[文件列表模式 / 详细信息](/Manual/preferences/preferences_categories/file_display_modes/details_mode.zh.md)** 和 **[文件列表模式 / 加强模式](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.zh.md)** 偏好设置页面都具有可让您配置 *缩略图* 列宽高比的选项（默认为 16:9），该选项决定列中的缩略图是否显示边框以及在 *缩略图* 列可见时是否应自动隐藏文件图标。

### 加强

这与 **详细信息** 模式非常相似（看起来一模一样），但列表在通过鼠标和键盘与之交互时的行为可以在更大程度上配置。

默认情况下，**加强** 模式使用持久选择 - 与其它视图模式不同，当您单击文件列表中的空白处时，文件不会自动取消选择。请参阅 **[文件列表模式 / 加强模式](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.zh.md)** 和 **[加强模式 / 按钮](/Manual/preferences/preferences_categories/file_display_modes/power_mode/buttons.zh.md)** 偏好设置页面，了解 **加强** 模式配置选项的完整说明。

在 **加强** 模式中，您可以按住 <kbd>Ctrl</kbd> 键并转动鼠标滚轮以增加或减小用于显示文件夹内容的字体大小。

### 缩略图

此模式显示文件和文件夹的缩略图，这对于图像或视频文件特别有用。

![](/Manual/images/media/13/view_mode_-_thumbs.png)

Opus 可以为许多不同的文件格式生成缩略图；无法生成缩略图的文件将显示该文件类型的常用图标。除了文件名之外，此模式还可以选择在每个缩略图下方显示文件大小和（对于图像文件格式）图像尺寸。您可以在 **[文件列表模式 / 缩略图模式](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.zh.md)** 偏好设置页面中配置缩略图的大小和外观。

默认情况下，无论何时将文件列表设置为缩略图模式，Opus 都会显示一个特殊工具栏——[图像工具栏](toolbars/the_default_toolbars/images_toolbar.zh.md) 。这其中包含用于处理图像的多个命令，以及用于调整缩略图大小的滑块。您还可以在按住 <kbd>Ctrl</kbd> 键的同时转动鼠标滚轮来增加或减小缩略图大小。

### 平铺

此模式将大图标（或可选缩略图）与详细信息模式显示文件名的功能合并在一起。

![](/Manual/images/media/13/view_mode_-_tiles.png)

您可以通过 [文件类型](/Manual/file_types/filetype_editor/tiles_mode.zh.md) 系统选择为每个文件类型显示哪些信息。另外，请参阅 **[文件列表模式 / 平铺模式](/Manual/preferences/preferences_categories/file_display_modes/tiles_mode.zh.md)** 偏好设置页面，了解可针对平铺模式配置的设置。