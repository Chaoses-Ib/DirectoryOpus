# Format

**Format** 对象表示当前标签页的显示格式。可以通过 **[Tab](tab.zh.md).format** 属性获取。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
alpha_folders</td><td>

*bool*</td><td>

如果文件夹总是按字母顺序排序，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
autosize</td><td>

*bool*</td><td>

如果启用列宽自动调整大小，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
checkboxes</td><td>

*bool*</td><td>

如果 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md) 已启用，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
columns</td><td>

*collection:***[Column](column.zh.md)**</td><td>

返回一个包含所有当前添加到显示中的 **[Column](column.zh.md)** 对象的集合。
</td></tr><tr><td>
format_explain</td><td>

**[Vector](vector.zh.md)**:*string*</td><td>

返回一个 **[Vector](vector.zh.md)**，其中包含表示当前文件夹格式说明的字符串（与将鼠标悬停在状态栏中的格式锁定图标上显示的文本相同）。
</td></tr><tr><td>
frozen</td><td>

*int*</td><td>
返回冻结列的数目。列总是从左侧冻结，因此这也可以告诉您哪些列被冻结（如果有）。
</td></tr><tr><td>
getsizes</td><td>

*string*</td><td>

返回一个字符串，表示自动计算文件夹大小选项的状态。返回的字符串将是 *default*、*on* 或 *off* 之一。
</td></tr><tr><td>
group_by</td><td>

*string*</td><td>
如果启用分组，则返回列表按其分组的列的名称。
</td></tr><tr><td>
group_combine</td><td>

*string*</td><td>

返回一个字符串，表示当前分组合并模式。可能的值是 **normal**、**never** 和 **other**。
</td></tr><tr><td>
group_individual</td><td>

*bool*</td><td>

如果分组合并模式设置为 **从不合并**，则返回 **True**。注意，此选项已弃用，您应该使用 **group_combine** 代替。
</td></tr><tr><td>
group_reverse</td><td>

*bool*</td><td>

如果组按反向顺序排序，则返回 **True**。
</td></tr><tr><td>
hide_attr</td><td>

*object:***[FileAttr](fileattr.zh.md)**</td><td>

返回一个 **[FileAttr](fileattr.zh.md)** 对象，表示隐藏的文件属性（任何设置了这些属性的项目都将从显示中隐藏）。
</td></tr><tr><td>
hide_dirs</td><td>

*string*</td><td>
返回从显示中隐藏的文件夹的通配符模式。
</td></tr><tr><td>
hide_dirs_regex</td><td>

*bool*</td><td>

如果当前 **hide_dirs** 模式使用正则表达式，则返回 **True**。
</td></tr><tr><td>
hide_ext</td><td>

*bool*</td><td>

如果文件名扩展名被隐藏，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
hide_files</td><td>

*string*</td><td>
返回从显示中隐藏的文件的通配符模式。
</td></tr><tr><td>
hide_files_regex</td><td>

*bool*</td><td>

如果当前 **hide_files** 模式使用正则表达式，则返回 **True**。
</td></tr><tr><td>
hide_folder_attr</td><td>

*object:***[FileAttr](fileattr.zh.md)**  
or *string*</td><td>

返回一个 **[FileAttr](fileattr.zh.md)** 对象，表示隐藏的文件夹属性（任何设置了这些属性的文件夹都将从显示中隐藏）。如果单独的文件夹属性过滤器被禁用，此属性将返回字符串 **"off"**。
</td></tr><tr><td>
ignore_prefix</td><td>

*string*</td><td>
返回在对列表进行排序时被忽略的文件名前缀。
</td></tr><tr><td>
locked</td><td>

*bool*</td><td>

如果标签页中的文件夹格式被锁定，则返回 **True**。
</td></tr><tr><td>
manual_sort</td><td>

*bool*</td><td>

如果 [手动排序](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.zh.md) 已启用，则返回 **True**。
</td></tr><tr><td>
manual_sort_name</td><td>

*string*</td><td>
如果手动排序处于活动状态，则返回当前排序顺序的名称（如果有）。
</td></tr><tr><td>
manual_sort_order</td><td>

*object:***[排序顺序](sortorder.zh.md)**</td><td>

如果手动排序处于活动状态，则返回一个 **[排序顺序](sortorder.zh.md)** 对象，您可以使用该对象查询和更改排序顺序。
</td></tr><tr><td>
mix_type</td><td>

*string*</td><td>

返回一个字符串，表示当前文件/文件夹混合类型。返回的字符串将是 *mixed*、*files*（文件优先）或 *dirs*（文件夹优先）之一。
</td></tr><tr><td>
name_ext</td><td>

*bool*</td><td>

如果文件名和扩展名分别排序，则返回 **True**。
</td></tr><tr><td>
numeric_name</td><td>

*bool*</td><td>

如果启用数字名称排序，则返回 **True**。
</td></tr><tr><td>
reverse_sort</td><td>

*bool*</td><td>

如果总体排序顺序反转，则返回 **True**。
</td></tr><tr><td>
show_attr</td><td>

*object:***[FileAttr](fileattr.zh.md)**</td><td>

返回一个 **[FileAttr](fileattr.zh.md)** 对象，表示显示的文件属性（仅显示设置了这些属性的项目）。
</td></tr><tr><td>
show_dirs</td><td>

*string*</td><td>
返回显示的文件夹的通配符模式（仅显示与该模式匹配的文件夹）。
</td></tr><tr><td>
show_dirs_regex</td><td>

*bool*</td><td>

如果当前 **show_dirs** 模式使用正则表达式，则返回 **True**。
</td></tr><tr><td>
show_files</td><td>

*string*</td><td>
返回显示的文件的通配符模式。
</td></tr><tr><td>
show_files_regex</td><td>

*bool*</td><td>

如果当前 **show_files** 模式使用正则表达式，则返回 **True**。
</td></tr><tr><td>
show_folder_attr</td><td>

*object:***[FileAttr](fileattr.zh.md)**  
or *string*</td><td>

返回一个 **[FileAttr](fileattr.zh.md)** 对象，表示显示的文件夹属性（仅显示设置了这些属性的文件夹）。如果单独的文件夹属性过滤器被禁用，此属性将返回字符串 **"off"**。
</td></tr><tr><td>
sort_ext</td><td>

*bool*</td><td>

如果名称列按文件名扩展名而不是文件名排序，则返回 **True**。
</td></tr><tr><td>
sort_field</td><td>

*object:***[Column](column.zh.md)**</td><td>

返回一个 **[Column](column.zh.md)** 对象，表示当前排序字段。
</td></tr><tr><td>
thumb_size</td><td>

*int*</td><td>
返回自定义缩略图大小，如果未设置自定义大小，则返回 0。
</td></tr><tr><td>
thumb_stretch</td><td>

*string*</td><td>

如果格式覆盖了全局缩略图拉伸模式，则返回 *FitReduce*、*FitSmooth*、*FitPixelated*、*FillCropSmooth* 或 *FillCropPixelated* 之一。否则，返回 *none*。
</td></tr><tr><td>
view</td><td>

*string*</td><td>

以字符串形式返回当前 [视图模式](/Manual/basic_concepts/the_lister/view_modes.zh.md)。返回的字符串将是 *large*\_*icons*、*small*\_*icons*、*list*、*details*、*power*、*thumbnails* 或 *tile* 之一。
</td></tr><tr><td>
word_sort</td><td>

*bool*</td><td>

如果启用单词排序，则返回 **True**。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

当脚本第一次访问特定的 **Format** 对象时，将拍摄标签页格式的快照。如果脚本随后对该标签页进行了更改（例如，更改排序字段等），这些更改将不会反映在对象中。要将对象与标签页重新同步，请调用 **Format.Update** 方法。
</td></tr></tbody>
</table>