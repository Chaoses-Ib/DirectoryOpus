# Print
**打印**内部命令可用于：

- 使用 Windows 照片打印向导打印照片和其他图像
- 直接打印受支持的图像文件
- 通过其已注册的处理程序打印其他文件
- 生成文件夹列表，并将其打印、保存到文件或复制到剪贴板
- 以 **CSV** 格式导出文件夹列表以导入到 Excel 等
- 显示已安装打印机的列表并允许您修改默认打印机

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
描述
</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

打印所选文件。如果仅选择图像文件（或根本没有选择文件），将启动 Windows 照片打印向导。非图像文件将通过其已注册的打印处理程序进行打印。

*示例：* `Print`
</td></tr><tr><td>
AS</td><td>
/K</td><td>

**txt**</td><td>

在将文件夹打印到磁盘或剪贴板时，使用纯文本格式。

*示例：* `Print FOLDER TO=clip AS=txt QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**csv**</td><td>

在将文件夹打印到磁盘或剪贴板时，使用 CSV（逗号分隔值）格式。

*示例：* `Print FOLDER TO /desktop/dirprint.csv AS=csv QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**tab**</td><td>

在将文件夹打印到磁盘或剪贴板时，使用制表符分隔格式。

*示例：* `Print FOLDER TO clip AS tab QUIET`
</td></tr><tr><td>
AUTOSIZECOLUMNS</td><td>
/K</td><td>

**yes**</td><td>

在将文件夹列表打印到打印机或纯文本文件中时，将自动计算列宽以适应其内容。

*示例：* `Print FOLDER "Brother HL-4050CDN" AUTOSIZECOLUMNS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

列不会自动调整大小 - 相反，将使用文件夹格式中的宽度。

*示例：* `Print FOLDER TO /desktop/dir.txt AS=txt AUTOSIZECOLUMNS=no`
</td></tr><tr><td>
CALCSIZES</td><td>
/K</td><td>

**yes**</td><td>

打印文件夹时计算文件夹大小。

*示例：* `Print FOLDER TO clip CALCSIZES=yes QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不要计算文件夹大小。

*示例：* `Print FOLDER TO clip CALCSIZES=no QUIET`
</td></tr><tr><td>
DEFAULTLIST</td><td>
/S</td><td>

*(无值)*</td><td>

显示已安装打印机的已生成列表（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。您可以使用此列表来更改默认打印机，并右键单击列表中的项以显示打印机的上下文菜单。您还可以通过将文件拖放到打印机的生成按钮上来打印文件。

*示例：* `Print DEFAULTLIST`
</td></tr><tr><td>
ENCODING</td><td>
/K</td><td>

**ansi**</td><td>

在将文件夹列表打印到文件时，指定应使用 **ANSI** 编码。最初，这是默认编码类型，但如果 *打印文件夹* 对话框以交互方式使用，它将记住上次手动选择的编码类型。使用此参数可覆盖上次使用的编码类型。

*示例：* `PRINT FOLDER TO /desktop/dirprint.txt ENCODING=ansi QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**utf8**</td><td>

将编码类型设置为带有 BOM（字节顺序标记）的 **UTF8**。

*示例：* `PRINT FOLDER TO /desktop/dirprint.txt ENCODING=bom QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**utf8nobom**</td><td>

将编码类型设置为不带 BOM 的 **UTF8**。

*示例：* `PRINT FOLDER TO /desktop/dirprint.txt ENCODING=utf8nobom`
</td></tr><tr><td>
FILTER</td><td>
/K</td><td>

*\<filter\>*</td><td>

在打印子文件夹的内容（通过 **FLATVIEW** 参数）时，使用 [filter](/Manual/file_operations/filtered_operations/README.zh.md)。这可能是您先前在配置中的 [**文件操作/过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面中创建的过滤器的名称，或者可能是过滤器的一个简单 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md) 根据文件名进行过滤。

*示例：* `Print FOLDER FILTER *.jpg FLATVIEW=nofolders QUIET`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

允许您在文本格式中定义一个过滤器，以在打印文件夹内容时过滤子文件夹的内容。这类似于 **FILTER** 参数，但过滤器不需要预先定义。

这是一个 **/R** 参数，因此 **FILTERDEF** 关键字之后的所有内容都将被视为参数值。

*示例：* `Print FOLDER FLATVIEW=nofolders QUIET FILTERDEF name match *.zip and size match > 2 mb`
</td></tr><tr><td>
FLATVIEW</td><td>
/K</td><td>

**no**</td><td>

在打印文件夹列表时，不要打印子文件夹的内容。

*示例：* `Print FOLDER FLATVIEW=no QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**mixed**</td><td>

以“混合”模式打印子文件夹的内容。这将文件和文件夹混合在一起，形成一个扁平列表。

*示例：* `Print FOLDER FLATVIEW=mixed TO clip QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**nofolders**</td><td>

以“混合 - 无文件夹模式”打印子文件夹的内容。将列出所有子文件夹中的文件，但不会显示文件夹本身。

*示例：* `Print FOLDER FLATVIEW=nofolders QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**grouped**</td><td>

以“分组”模式打印子文件夹的内容。各级文件和文件夹缩进，以反映树形层次结构。

*示例：* `Print FOLDER TO /desktop/dirtree.txt FLATVIEW=grouped QUIET`
</td></tr><tr><td>
FOLDER</td><td>
/O</td><td>

*(无值)*</td><td>

显示 [**打印文件夹](/Manual/additional_functionality/print_folder.zh.md)** 对话框，该对话框允许您打印或导出文件窗口中显示的当前文件夹的内容。

*示例：* `Print FOLDER`
</td></tr><tr><td>
</td><td>
</td><td>

**selected**</td><td>

打印文件夹功能将仅打印当前文件夹中的所选文件。

*示例：* `Print FOLDER=selected`
</td></tr><tr><td>
</td><td>
</td><td>

*\<path\>*</td><td>

指定要打印的文件夹路径。

*示例：* `Print FOLDER /desktop TO clip QUIET`
</td></tr><tr><td>
FONT</td><td>
/K</td><td>

*\<name\>,\<size\>*</td><td>

指定在打印到打印机时要使用的字体。

*示例：* `Print FOLDER FONT Arial,20 QUIET`
</td></tr><tr><td>
FORMAT</td><td>
/K</td><td>

*\<format name\>*</td><td>

使用指定的最爱文件夹格式来控制打印信息的列、排序顺序和类似的详细信息。

必须首先从配置中的 [**文件夹/文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md)** 页面创建命名的格式。

*示例：* `Print FOLDER FORMAT="My Format" QUIET`

**FORMAT** 参数还接受以下特殊关键字：

- **!current**：使用文件列表的当前格式，包括对其进行的任何临时编辑。
- **!default**：使用适用于当前文件夹的文件夹类型格式。例如，如果是网络驱动器，则使用 **网络驱动器**。
*- **!factory**: 使用硬编码的工厂-默认格式。
- **!folder**: 使用当前文件夹的格式。当在新窗口打开当前文件夹时，通常会获取此格式。
- **!user**: 使用**User Default**格式。

*示例:* `Print FOLDER FORMAT=!current QUIET`
</td></tr><tr><td>
HEADER</td><td>
/K</td><td>

**top**</td><td>

在每页顶部打印头文件（或打印到磁盘或剪贴板时，在清单顶部打印头文件）。

*示例:* `Print FOLDER HEADER=top QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**bottom**</td><td>

在每页底部打印尾部文件（或在清单底部打印尾部文件）。

*示例:* `Print FOLDER HEADER=bottom QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

打印头文件和尾部文件。

*示例:* `Print FOLDER HEADER=both QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

不打印头文件或尾部文件。

*示例:* `Print FOLDER HEADER=none QUIET`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

当与生成项目列表的命令一起使用时（参见 [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数会在列表之始添加一个小 عنوان。当列表为空时，会隐藏该标题。标题仅适用于具有可能在按钮自身相同级别上生成多个项目的命令。

当 **HEADING** 单独使用时，而不指定文本值，则主按钮的标记文本用于标题。

*示例:* `Print DEFAULTLIST HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题文本\>*</td><td>

如果希望标题文本与按钮标记不同，则可以指定标题文本。

*示例:* `Print DEFAULTLIST HEADING="Default Printer"`
</td></tr><tr><td>
KEYWORDS</td><td>
/S</td><td>

*(无值)*</td><td>

打印文件夹清单时，每列标题会显示关键字（有时称为“原始名称”），而不是显示名称。关键字唯一标识每列，并且不会因语言的不同而改变，而显示名称经过翻译，可能不唯一。

*示例:* `Print FOLDER AS=csv TO=clip FLATVIEW=no QUIET KEYWORDS`
</td></tr><tr><td>
NOWIZARD</td><td>
/S</td><td>

*(无值)*</td><td>

对于图像文件绕过 Windows Photo Printing Wizard；Opus 可以以其能够查看的原生图像格式打印任何映像。

*示例:* `Print NOWIZARD`
</td></tr><tr><td>
QUIET</td><td>
/S</td><td>

*(无值)*</td><td>

使用指定选项打印文件夹，而不先显示 *Print Folder* 对话框。

*示例:* `Print FOLDER QUIET`
</td></tr><tr><td>
SETDEFAULT</td><td>
/K</td><td>

*\<打印机名称\>*</td><td>

将指定打印机设为系统默认打印机。您提供的名称必须是打印机控制面板中显示的打印机的全称。如果名称包含空格，请确保在名称周围添加引号。

*示例:* `Print SETDEFAULT "Brother HL-4050CDN"`
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<打印机名称\>*</td><td>

将选中的文件或文件夹打印到指定打印机（覆盖默认打印机）。带此命令的按钮还可以接受拖放到其上的文件以进行打印。

*示例:* `Print TO "Brother HL-4050CDN"`
</td></tr><tr><td>
</td><td>
</td><td>

*\<文件名\>*</td><td>

将文件夹内容打印到指定磁盘文件。

*示例:* `Print TO dirlist.txt FOLDER C:\Data QUIET AS txt`
</td></tr><tr><td>
</td><td>
</td><td>

**clip**</td><td>

将文件夹清单打印到剪贴板。

*示例:* `Print FOLDER TO clip AS csv`
</td></tr></tbody>
</table>