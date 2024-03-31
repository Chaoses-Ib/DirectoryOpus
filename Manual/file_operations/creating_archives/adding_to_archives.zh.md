# 添加到压缩包文件

使用 Opus 存在多种方法可以将文件添加到压缩包文件。

- 你可以[创建一个新压缩包文件]()（如果需要 - 你还可以添加到现有压缩包文件），然后将其打开就好像它是一个文件夹，并正常复制或粘贴文件到其中。
- 你可以通过拖放文件到压缩包文件上方来将它们添加到压缩包文件中（同样，这个过程将压缩包文件当作文件夹一样处理）。
- 你可以使用工具栏上的 **压缩包文件** 命令（或附加到此按钮的下拉菜单中的变体命令）。
- 你可以通过右击想要添加的文件，然后使用上下文菜单（如果已启用）将其添加到一个新压缩包文件或现有压缩包文件中。

使用上下文菜单 **添加到压缩包文件** 命令，或从工具栏中选择 **压缩包文件** 命令，显示 [添加到压缩包文件对话框](/Manual/file_operations/creating_archives/add_to_archive_dialog/README.zh.md)。

### 压缩包文件上下文菜单

访问此功能最简单的方法是通过上下文菜单。在配置中的 [压缩包文件上下文菜单](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_context_menu.zh.md) 页面中，你可以启用或禁用上下文菜单命令，以将文件添加到各种压缩包文件格式。每当你右击一个或多个文件和文件夹时，将显示这些命令。

### 添加到指定的压缩包文件

这些命令将立即将选定的文件和文件夹添加到一个新的压缩包文件中。新压缩包文件将位于源文件所在的文件夹中，并且其名称将与第一个选定的文件相同。

![](/Manual/images/media/13/add_to_archive_-_menu.png)

例如，如果你右击名为 *Presentation.doc* 的文件，上下文菜单可能包含一个名为 **添加到“Presentation.7z”** 的命令 - 选择此命令将创建一个名为 *Presentation.7z* 的新的 7zip 压缩包文件，并将选定的文件添加到其中。

[配置](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_context_menu.zh.md) 页面允许你选择显示用于 *添加到指定压缩包文件* 命令的格式。

### 添加到压缩包文件

这些命令还会将所选文件和文件夹添加到一个新压缩包文件中，但不会立即创建压缩包文件，而是会给你一个文件名和路径、压缩包类型以及针对所选压缩包文件格式的各种参数的选择。

![](/Manual/images/media/13/archive_context_-_add_menu.png)

[配置](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_context_menu.zh.md) 页面还允许你选择为这些命令添加哪些格式，虽然此设置（例如 *添加到压缩包文件（RAR）*）仅将 *RAR* 设置为最初选择的格式；而 *添加到压缩包文件* 对话框允许你更改选定的格式。