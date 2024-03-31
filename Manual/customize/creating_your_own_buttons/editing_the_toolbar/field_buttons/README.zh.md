**字段按钮**

字段按钮是另一种特殊类型的按钮。它们用于将字段控件（例如，位置字段）放置在工具栏上。在自定义模式下，它们显示为一个简单的框架，可以通过单击和拖动边框来调整其大小。

![](/Manual/images/media/field_buttons_-_customize.png)

上图显示了默认菜单工具栏中的搜索字段和默认文件列表边界工具栏中的位置字段。您可以看到搜索字段在右侧有抓取手柄，可以让您调整字段的大小。位置字段没有，因为它设置为*全宽*模式，这意味着它会扩展以填充工具栏上的所有可用空间。

一旦我们退出自定义模式，您就能看到该框架恢复成功能完备的字段：

![](/Manual/images/media/field_buttons_-_no_customize.png)

请注意，在退出自定义模式时，兼容性文件按钮消失了；这是因为在截取屏幕截图时，文件窗口当前未显示具有兼容性文件的文件夹，因此该按钮自动隐藏。您会发现 Opus 工具栏上的许多按钮可以动态地改变其状态（选中或未选中，启用或禁用，隐藏或显示）。如果我们在截屏之前导航至*C:\Program* Files，兼容文件按钮将可见。

字段按钮是您唯一无法手动（从新按钮开始）创建的按钮类型。要向工具栏中添加字段按钮，您必须在**命令**页面上的列表中找到它的条目并将其拖动到工具栏。但是，一旦它位于工具栏上，您就可以更改字段的类型以及在自定义模式下右键单击他时配置某些属性。

![](/Manual/images/media/field_buttons_edit.png)

字段按钮的上下文菜单允许您配置仅适用于字段的两个选项：

- **全宽**：如果启用此选项，字段将使用工具栏上的所有可用空间（即未由其他按钮使用的任何空间）。如果同一工具栏上的两个或多个字段设置了此标志，它们将共享可用空间。
- **恢复焦点**：如果启用此选项，在字段中按 **Enter** 键将自动将焦点返回到文件列表。

**字段类型**子菜单允许您在各种类型的字段之间切换：

- **内容类型**：如果启用了文件夹[内容类型检测](/Manual/basic_concepts/folder_options/content_types.zh.md)，则会显示当前使用的内容类型格式。您还可以使用下拉列表立即切换到已定义的内容类型格式之一。

  ![](/Manual/images/media/content_type_field.png)

- **驱动器**：[驱动器列表](/Manual/basic_concepts/the_lister/navigation/drive_buttons_and_lists.zh.md)字段是您的磁盘驱动器的下拉列表。从列表中选择驱动器会将源文件列表导航到该位置。  

  ![](/Manual/images/media/drive_list_field.png)

- **过滤器**：[过滤器字段](/Manual/basic_concepts/searching_and_filtering/toolbar_filter_fields.zh.md)允许您通过输入[通配符模式](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md)来过滤当前文件夹中可见的项。

  ![](/Manual/images/media/filter_field.png)

- **标签**：标签字段除了显示静态标签外，没有任何功能。您可以使用它为其他控件提供标签，或只是在工具栏上显示静态文本字符串。

  下拉菜单中的标签字段以粗体字绘制，并左对齐，以便在视觉上与菜单中的其他项区分开来。

  ![](/Manual/images/media/image079.png)

- **路径（基本）**：基本路径（位置）字段是一个极简的文本字段，它显示当前路径，并允许您键入新的路径在文件窗口中导航。默认情况下，该字段控制当前源文件列表，但您可以[配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.zh.md)它来指定所链接到的显示。

  ![](/Manual/images/media/path_field_basic.png)

- **路径（面包屑）**：[面包屑](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.zh.md)路径（位置）字段是一个强大的导航工具，它提供对当前路径中先前位置的即时访问。此字段具有[许多可配置选项](/Manual/preferences/preferences_categories/location_bar/path_fields/README.zh.md)，可以修改其外观和行为。

  ![](/Manual/images/media/path_field_crumbs.png)

- **路径（收藏夹列表）**：收藏夹列表路径字段将基本路径字段与您[收藏的文件夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md)的下拉菜单结合在一起，您可以通过从下拉菜单中选择它们来导航到这些文件夹。默认情况下，该字段控制当前源文件列表，但您可以[配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.zh.md)它来指定所链接到的显示。

  ![](/Manual/images/media/path_field_dropdown.png)

- **路径（文件夹树）**：文件夹树路径字段将基本路径字段与包含导致当前位置的文件夹树层次结构的下拉列表结合在一起。这允许您从下拉列表中导航到树中的先前文件夹。默认情况下，该字段控件当前源文件列表，但您可以[配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.zh.md)它来指定所链接到的显示。

  ![](/Manual/images/media/path_field_dropdown.png)

- **路径（最近列表）**：最近列表路径字段将基本路径字段与您[最近访问的文件夹](/Manual/basic_concepts/the_lister/navigation/recent_and_history_lists.zh.md)的下拉菜单结合在一起。默认情况下，该字段控制当前源文件列表，但您可以[配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.zh.md)它来指定所链接到的显示。

  ![](/Manual/images/media/path_field_dropdown.png)

- **搜索字段**：搜索字段允许您使用索引的[Windows 搜索](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md)系统搜索当前文件夹。

  ![](/Manual/images/media/search_field1.png)

- **间隔符**：间隔符字段除了占用工具栏上的空间外，没有任何功能 - 它用于右对齐工具栏元素。

- **缩略图大小**：缩略图大小字段允许您动态调整当前文件夹中的缩略图大小。当文件窗口不处于缩略图模式时它将隐藏。

  ![](/Manual/images/media/thumbnail_size_slider.png)

  默认情况下，如果滑块位于正常工具栏上，它将影响窗口中的所有文件夹标签页；如果它位于地址栏工具栏上，则只影响它覆盖的那一侧。您可以通过编辑字段并将 `both`, `source`, `dest`, `left` 或 `right` 添加到 *Args* 字符串来更改此设置。（`both` 与默认设置的不同之处在于它只影响可见标签页，而不影响非活动标签页。）

  在默认情况下，滑块将使用配置中配置的纵横比设置缩略图大小；但是，如果您编辑字段并将 `preserve` 添加到 *Args* 字符串中，它将保留当前纵横比（这仅在使用 `Set THUMBNAILSIZE` 命令手动更改纵横比时才有用）。如果也指定了一侧，请在两个参数之间加上逗号；例如 `left,preserve`。
请参阅 [编辑工具栏]() 部分，了解更多关于如何编辑工具栏字段的信息。

更多信息：

[路径字段配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.zh.md)  
[面包屑配置](/Manual/preferences/preferences_categories/location_bar/path_fields/README.zh.md)  
[过滤器字段配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/filter_field_configuration.zh.md)  
[驱动列表配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/drive_list_configuration.zh.md)