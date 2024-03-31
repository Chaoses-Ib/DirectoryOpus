# 文件夹图像

**文件夹图像**页面允许你在特定文件夹或特定类型的文件夹中更改背景图像和颜色。它的操作类似于 [文件夹格式](folder_formats/README.zh.md) 页面。在此处定义的文件夹和颜色将覆盖 [图像](/Manual/preferences/preferences_categories/colors_and_fonts/images.zh.md) 和 [Directory Opus 颜色](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.zh.md) 页面上的相关全局设置。

文件夹列表分为不同的组：

## 文件夹

此组定义特定文件夹的图像和颜色。你也可以使用通配符字符串为路径定义图像。

## 系统文件夹

为某些特殊位置定义图像。此组中当前只有两个位置 - **计算机** 文件夹，当 Opus 显示文件夹本身而不是托管资源管理器时适用，和 **便携式设备** 文件夹，当查看 [mtp:](/Manual/basic_concepts/virtual_file_system/mtp.zh.md) 命名空间的根目录时适用。

## 内容类型

内容类型部分为 [文件类型组](/Manual/file_types/file_type_groups.zh.md) 定义图像。当 [内容类型](/Manual/basic_concepts/folder_options/content_types.zh.md) 系统启用时，当读取包含足够数量此类文件的文件夹时，将自动使用这些图像。

## 文件夹类型

此部分为特定类型的文件夹定义默认图像，当未定义特定图像时。类型有：

      * **压缩包文件**: ZIP 和其他压缩包文件。
      * **云存储**: 云存储文件夹（OneDrive、Dropbox 等）
      * **集合**: 一般 [[:basic_concepts:virtual_file_system:file_collections|文件集合]] 文件夹。 
      * **重复文件**: 用于显示 [[:additional_functionality:duplicate_file_finder|重复文件查找器]] 结果的文件集合。
      * **查找结果**: 用于显示 [[:basic_concepts:searching_and_filtering:find_files|查找工具]] 结果的文件集合。
      * **平面视图**: 每当文件列表放入 [[:basic_concepts:flat_view|平面视图]] 模式时适用。 
      * **FTP**: FTP 站点。 
      * **本地驱动器**: 位于本地驱动器（如固定硬盘 C:）上的文件夹。 
      * **网络驱动器**: 位于网络驱动器上的文件夹。
      * **便携式设备**: 位于便携式设备（如手机和照相机）上的文件夹。 
      * **可移动驱动器**: 可移动驱动器，如 USB 闪存驱动器。 
      * **搜索结果**: 用于呈现快速搜索结果的文件集合。
      * **同步**: 每当 [[:file_operations:copying_moving_and_deleting_files:copying_updated_files:synchronize|同步]] 工具使用时适用。 

## 使用文件夹列表

列表上方的工具栏允许你添加或移除特定文件夹和路径通配符。可以使用标准 Opus [通配符系统](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md) 或使用 [正则表达式](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.zh.md) 定义路径通配符。如果启用了 **展开别名** 选项，则 Opus 将尝试在执行模式匹配前展开输入字符串中的文件夹别名和环境变量。

要为特定文件夹或文件夹类型启用图像，请启用其复选框。当选中该项目时，对话框的底部将显示该图像的设置。

## 图像设置

![](/Manual/images/media/13/folder_images.png)

- **图像**: 这指定要使用的图像。路径可以使用别名或绝对路径指定。右侧的下拉箭头下拉了当前正在使用其他图像列表，便于将同一图像指定到多个文件夹。如果只想更改背景颜色，则可以将图像留空）。
- **图像适合**: 定义图像如何缩放以适合窗口。选项有：
  - **平铺**: 在窗口中平铺图像；如果它小于窗口的尺寸，则重复它以填充元素边界。
  - **拉伸**: 将图像拉伸到窗口尺寸（较小或较大）。
  - **保持纵横比**: 足够大以覆盖窗口的宽度或高度而不裁剪，并保留原始纵横比。
  - **填充纵横比**: 足够大以覆盖整个窗口，并在必要时裁剪图像（也保留纵横比）。
  - **平铺纵横比**: 类似于 **保持纵横比**，但图像随后平铺以完全填充窗口。
  - **顶部/左侧**: 将图像锚定到窗口的左上角，如果它大于窗口则裁剪。
  - **顶部/右侧**: 将图像锚定到右上角。
  - **底部/左侧**: 将图像锚定到左下角。
  - **底部/右侧**: 将图像锚定到右下角。
  - **居中**: 将图像置于元素内居中。
- **不透明度**: 指定图像的不透明度；100% 全不透明，0% 完全透明。
- **填充颜色**: 指定背景填充颜色。上方显示的棋盘格图案表示未选择颜色。
- **共享**: 图像将在整个文件窗口中与其他元素共享。
- **将设置应用到所有子文件夹**: 除非子文件夹也有自己的特定图像定义，否则定义的图像也将用于该路径下的任何子文件夹。