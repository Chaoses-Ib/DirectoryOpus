# 编辑元数据

元数据是存储在描述文件本身的文件中的信息。例如，您使用数码相机拍摄的照片包含元数据，如拍摄日期和时间，以及用于拍照的曝光设置。

Opus 允许您使用三种方式编辑文件元数据：

- [元数据面板](/Manual/basic_concepts/the_lister/metadata_pane.zh.md) 是最简单的；它允许您直接在文件窗口或图像查看器中查看元数据并对选定文件进行更改。
- **设置元数据** 对话框的工作方式类似于典型文件操作 - 它显示一个对话框，用于选择要进行的更改，然后当您单击 **确定** 时，更改将应用于所有选定的文件。
- [以编程方式](/Manual/file_operations/editing_metadata/programmatic_setting_of_metadata.zh.md)，使用 `SetAttr META` 命令，您可以创建自动修改所选文件元数据的按钮或热键。

### 显示元数据面板

要在文件窗口中显示 **元数据面板**，请从 **文件窗口** 下拉菜单中选择 **元数据面板** 命令。当您在文件列表中选择和取消选择文件时，面板将实时更新。

在独立的 [图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中，从 **编辑** 菜单中选择 **编辑元数据**。

### 显示“设置元数据”对话框

要调用 **设置元数据** 对话框，请选择您要编辑的文件，然后从下拉 **属性** 菜单中选择 **编辑元数据** 命令。

无论您选择哪种编辑方法，都会使用相同的显示来显示当前元数据设置并允许您进行更改。

![](/Manual/images/media/13/metadata_example.png)

### 元数据类别

元数据属性列表分为多个类别。根据您选择的文件类型或类型，显示的类别和属性会发生变化。可以通过单击类别名称左侧的按钮来折叠各个类别以隐藏其内容，![](/Manual/images/media/metadata_collapse.png)

- **不可编辑属性**：这些是文件仅仅供参考的*固有*属性 - 它们无法编辑。这些属性仅显示在 **元数据面板** 中，不显示在 **设置元数据** 对话框中。
- **[文档属性](/Manual/file_operations/editing_metadata/document_properties.zh.md)**：适用于文档的属性（作者、版权、主题等）。某些非文档文件类型也支持其中一些属性 - 例如，图像文件可以像 Word 文档一样具有作者和主题。
- **[图片属性](/Manual/file_operations/editing_metadata/picture_properties.zh.md)**：这些是适用于图像的属性。它们以 **EXIF** 格式存储，因此图像格式必须支持使用 [EXIF 数据](http://en.wikipedia.org/wiki/EXIF)（例如 **JPEG**、**PNG**、**TIFF**）。
- **[音乐属性](/Manual/file_operations/editing_metadata/music_properties/README.zh.md)**：这些属性适用于 **MP3** 和 **WMA** 等音乐文件。
- **[视频属性](/Manual/file_operations/editing_metadata/video_properties.zh.md)**：这些属性适用于 **AVI** 和 **WMV** 等视频文件。
- **音乐和电影属性**：这些属性适用于音乐和视频文件。仅当您同时选择音乐和视频文件时才会显示此类别。
- **[扩展属性](/Manual/file_operations/editing_metadata/extended_properties.zh.md)**：这些属性标称可用于所有文件类型，例如 **评论**、**评级** 和 **标签**。如果选定的文件格式本机支持这些属性（例如，**JPEG** 文件支持），则信息将存储在文件本身中。如果选定的文件格式不支持这些属性（例如，**.txt** 文件），则 Opus 将尝试将信息存储在附加到文件上的 [备用数据流](http://en.wikipedia.org/wiki/Alternate_data_stream) 中。由于只有 NTFS 文件系统支持 ADS 系统，因此这些属性对于存储在其他文件系统上的文件不可用。如果文件列表中显示了 *评级* 列，则可以通过单击星星（而不是通过元数据面板）直接编辑文件的评级。
- **标准属性**：这些属性适用于所有文件 - 属性和时间戳。您可以通过元数据系统修改这些属性，作为使用 **[更改属性和时间](changing_attributes.zh.md)** 对话框的替代方法。这两个时间戳属性具有 **选择操作** 字段，该字段允许您输入一个*[时间偏移](/Manual/file_operations/editing_metadata/time_shifting.zh.md)* 字符串，该字符串将对日期字段的当前值执行相对调整。

### 编辑元数据

要编辑元数据显示中的值，只需单击它以调用编辑控件。使用的控件类型将取决于正在编辑的字段。例如，对于字符串，这将是一个文本编辑字段，但对于只能从某些选项中选择的属性，这可能是一个下拉列表。

要接受您对字段所做的更改，只需单击它（或另一个字段）。您还可以使用键盘在字段之间移动 - 按 <kbd>Tab</kbd> 键移动到下一个字段，或按 <kbd>Shift+Tab</kbd> 移动到上一个字段。您可以按 **Enter** 键接受您对字段所做的更改，或按 <kbd>Esc</kbd> 撤消对当前字段所做的更改。

当修改属性时，将在字段名称左侧用红色三角形表示它。

![](/Manual/images/media/13/metadata_edit_example.png)

### 一次更改多个文件

您只需一次选择多个文件（对于 **元数据面板**）或在调用 **编辑元数据** 命令时选择多个文件，就可以同时编辑多个文件的文件元数据。只能编辑所有选定文件共有的属性。例如，如果您一次选择四个图像文件，所有 **文档** 和 **图片属性** 字段都将按常显示，但如果您选择四个图像文件和一个音乐文件，将仅显示它们共有的几个 **文档** 字段。

元数据显示首次初始化时，它会显示所选文件的各个属性的当前值。如果选择了多个文件，并且它们对给定属性具有不同的值，则会显示指示*多个值*。如果您在选择了多个文件时编辑某个属性，新值将应用于所有文件。

### 使用多值字段

某些字段（例如标签、作者）支持多个值。要使用此功能，请用分号分隔每个值。当选择了多个文件时，您可以使用 `+` 和 `-` 前缀添加和删除特定值，同时保留其他值不变。

您可以在 [元数据/编辑器](/Manual/preferences/preferences_categories/file_operations/metadata/editor.zh.md) 配置页面中打开 **默认情况下添加多个值字段** 选项，以在这种情况下默认添加新值（无需键入 `+`）。
### 拖放复制元数据

使用拖放功能，可以将某些属性组合从一个文件复制到一个或多个目标文件。当您在元数据面板或单独对话框中编辑一个或多个文件的元数据时，您可以将一个其他文件拖放到属性列表中。如果您使用鼠标左键拖动，将复制一套默认属性；使用鼠标右键拖动将显示一个弹出菜单，您可以从中选择要从拖放文件中复制的属性。

![](/Manual/images/media/13/copy_metadata.png) 

### 应用更改

在 **设置元数据** 对话框中，完成元数据编辑后，单击 **确定** 按钮将更改应用到所选文件。

在 **元数据面板** 中，进行一项或多项更改也会启用面板标题栏中的 **应用** 和 **取消** 链接。完成所选文件的元数据编辑后，单击 **应用** 链接保存更改。您还可以单击 **取消** 链接，以放弃所有更改，并将所有属性重置为其初始值。

**元数据面板** 标题栏中的箭头按钮使您可以快速移动到下一个或上一个文件。如果您在单击这些箭头时按住 <kbd>Shift</kbd> 键，则对当前文件元数据所做的任何更改都将自动保存。

您可以在 [元数据/编辑器](/Manual/preferences/preferences_categories/file_operations/metadata/editor.zh.md) 配置页面上打开 **自动应用更改** 选项，无需单击 **应用** 即可保存更改。

更多信息：[文档属性](/Manual/file_operations/editing_metadata/document_properties.zh.md)  
[图片属性](/Manual/file_operations/editing_metadata/picture_properties.zh.md)  
[时间转换](/Manual/file_operations/editing_metadata/time_shifting.zh.md)  
[音乐属性](/Manual/file_operations/editing_metadata/music_properties/README.zh.md)  
[视频属性](/Manual/file_operations/editing_metadata/video_properties.zh.md)  
[扩展属性](/Manual/file_operations/editing_metadata/extended_properties.zh.md)  
[元数据的编程设置](/Manual/file_operations/editing_metadata/programmatic_setting_of_metadata.zh.md)