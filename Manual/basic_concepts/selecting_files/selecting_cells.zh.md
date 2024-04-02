# 选择单元格

除了选择文件来对它们执行操作外，在“详细信息”和增强模式下，您还可以选择单个单元格（或整列），并将它们的内容复制到剪贴板中。

### 选择单元格

按住 <kbd>Ctrl</kbd> 键使用鼠标右键来选择单元格：

- 要选择单个单元格，请按住 <kbd>Ctrl</kbd> 并右击该单元格
- 要选择整列，请按住 <kbd>Ctrl</kbd> 并右击列标题
- 要选择一组单元格，请按住 <kbd>Ctrl</kbd> 然后单击并用鼠标右键拖动以在您想要选择的单元格周围绘制一个套索

默认情况下，选定的单元格会以黄色突出显示。您可以在[Directory Opus 颜色](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.zh.md) 配置页面中配置此颜色。

### 复制单元格数据

选择一个或多个单元格后，**不**按住 <kbd>Ctrl</kbd> 键右击其中一个选定的单元格。这将显示**复制突出显示的单元格**上下文菜单。

![](/Manual/images/media/13/cell_highlights.png)

上下文菜单上的命令可用于以多种方式将突出显示的数据复制到剪贴板。

### 取消选择单元格

- 要取消选择选定的单元格，请按住 <kbd>Ctrl</kbd> 键并再次右击（选择操作为切换）。
- 要清除所有选定内容，请按 <kbd>Esc</kbd>，或在文件列表中的任何位置单击鼠标左键。

### 配置上下文菜单

可以从[自定义/上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md) 标签页配置上下文菜单。标准上下文菜单使用 `Clipboard COPYCOLUMNS` 命令来实现各种“复制到剪贴板”的功能，并使用 `Select HIGHLIGHTCLEAR` 命令来实现“清除突出显示的单元格”命令。

脚本可以使用 **[Item](/Manual/reference/scripting_reference/scripting_objects/item.zh.md).highlighted** 属性来查询当前任何突出显示的单元格。