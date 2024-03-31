# 全局过滤器

此页包含一些选项，可让你指定 Opus 在文件列表或文件夹树中绝不会显示的文件。虽然可以使用 [文件夹格式](../folders/folder_formats/README.zh.md) 系统（具体来说，为 [过滤器](/Manual/basic_concepts/folder_options/folder_options_dialog/filters.zh.md)页面选择显示和隐藏），针对每个文件夹进行过滤器配置，但它提供了一种无需配置文件夹格式即可在全局范围内隐藏文件的方法。

- **隐藏隐藏文件**：此选项会导致 Opus 隐藏已设置 **H** 属性但未设置 **S** 属性的文件和文件夹。你可以在 [菜单工具栏](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/menu_toolbar.zh.md) 上的 **文件夹选项** 菜单中的 **显示隐藏文件** 项来快速切换此选项。
- **隐藏操作系统文件**：此选项会导致 Opus 隐藏同时设置了 **H** 和 **S** 属性的文件和文件夹，这通常表示它们是特殊操作系统文件和文件夹。你可以在 [菜单工具栏](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/menu_toolbar.zh.md) 上的 **文件夹选项** 菜单中的 **显示系统文件** 项来快速切换此选项。

- **启用全局通配符过滤器**：启用此项后，你可以为要在全局范围内隐藏的文件和文件夹定义通配符过滤字符串。你可以根据文件名或文件扩展名匹配文件，或者使用 Opus [模式匹配语法](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md) 或者在启用 **使用正则表达式** 选项后使用 [正则表达式语法](/Manual/reference/wildcard_reference/regular_expression_syntax.zh.md)。例如，若要从不显示 desktop.ini 文件或 thumbs.db 文件，你可以指定模式 \<nobr\>`(desktop.ini|*thumbs*.db)`\</nobr\>。你可以输入多个模式，每行一个。

可以在文件夹标签中通过切换 [显示所有](/Manual/basic_concepts/searching_and_filtering/show_everything.zh.md) 模式来快速禁用所有过滤内容。