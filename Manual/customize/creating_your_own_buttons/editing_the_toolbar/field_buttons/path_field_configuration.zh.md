# 路径字段配置

各种类型的 [路径字段]()（基本、面包屑、收藏夹、文件夹树、最新）通常在当前 [源文件列表](/Manual/basic_concepts/source_and_destination.zh.md) 上操作 - 在双栏文件窗口中，字段中显示的路径会随着你从左向右切换源文件而更新。如果需要，可以将所有这些字段配置为控制特定的文件列表。例如，这允许你使用双栏文件窗口拥有两个单独的路径字段，一个用于左边，一个用于右边。你可以通过在 [自定义](/Manual/customize/README.zh.md) 模式中编辑字段的按钮定义来配置此行为。

![](/Manual/images/media/edit_path_fields.png) 

从 **设置** 菜单中选择 **自定义**，然后右键单击路径字段（它将变回简单的框架 - 有关更多信息，请参阅 [字段按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/README.zh.md) 讨论），然后选择 **编辑**。命令编辑器对话框中的 **Args** 字段用于提供定义字段行为的各种关键字。可用的关键字包括：

- **left**：路径字段将始终控制左边（或上方）文件列表。
- **right**：路径字段将始终控制右边（或下方）文件列表。
- **dest**：路径字段将始终控制目标文件列表。
- **focus**：如果将路径字段配置为控制除源之外的文件列表，则添加 **focus** 关键字以及将自动将焦点设置为该文件列表（即每当文件夹更改时，该文件列表将成为新的源）。

对于面包屑路径字段，你可以通过 [地址栏/路径字段](/Manual/preferences/preferences_categories/location_bar/path_fields/README.zh.md) 配置部分配置其外观和行为。