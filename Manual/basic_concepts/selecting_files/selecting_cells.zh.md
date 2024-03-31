# 选择单元格

除了选择文件来对它们执行操作外，在“详细信息”和“强大”模式下，您还可以选择单个单元格（或整列），并将它们的内容复制到剪贴板中。

### 选择单元格

使用按住 <kbd>Ctrl</kbd> 键的鼠标右键执行单元格选择：

- 要选择单个单元格，请按住 <kbd>Ctrl</kbd> 并右击该单元格
- 要选择整列，请按住 <kbd>Ctrl</kbd> 并右击列标题
- 要选择一组单元格，请按住 <kbd>Ctrl</kbd> 然后单击并用鼠标右键拖动以在您想要选择的单元格周围绘制一个套索

默认情况下，所选单元格以黄色突出显示。您可以从[Directory Opus 颜色](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.zh.md) 选项页面配置此颜色。

### 复制单元格数据

选择了一个或多个单元格后，右键单击选定的单元格之一**不**按 <kbd>Ctrl</kbd> 键。这将显示**复制突出显示的单元格**上下文菜单。

![](/Manual/images/media/13/cell_highlights.png)

上下文菜单上的命令可以用于以各种方式将突出显示的数据复制到剪贴板中。

### 取消选择单元格

- 要取消选择所选单元格，请按住 <kbd>Ctrl</kbd> 并再次右击它（选择操作是切换）。
- 要清除所有选择，请按 <kbd>Esc</kbd>，或单击文件列表中的任何地方使用鼠标左键。

### 配置上下文菜单

上下文菜单可以从[自定义/上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md) 标签页中进行配置。标准上下文菜单使用 `Clipboard COPYCOLUMNS` 命令来实现各种“复制到剪贴板”功能，并使用 `Select HIGHLIGHTCLEAR` 命令来实现“清除突出显示的单元格”命令。

脚本可以使用 **[项目](/Manual/reference/scripting_reference/scripting_objects/item.zh.md)。突出显示**属性来查询当前突出显示的任何单元格。