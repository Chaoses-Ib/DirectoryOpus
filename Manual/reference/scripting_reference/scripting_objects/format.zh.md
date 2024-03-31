**Format** 对象表示标签的当前显示格式。可从 **[标签](tab.zh.md).format** 属性中获取。

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

如果启用列宽自动调整，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
checkboxes</td><td>

*bool*</td><td>

如果选中 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
columns</td><td>

*集合:***[列](column.zh.md)**</td><td>

返回 **[列](column.zh.md)** 对象的集合，这些对象表示当前添加到显示中的所有单个列。
</td></tr><tr><td>
format_explain</td><td>

**[向量](vector.zh.md)**:*字符串*</td><td>

返回 **[向量](vector.zh.md)**字符串，表示当前文件夹格式的说明（将鼠标悬停在状态栏中的格式锁定图标上时，可以看到相同的文本）。
</td></tr><tr><td>
frozen</td><td>

*int*</td><td>
返回冻结的列数。列始终从左侧冻结，因此它还告诉您冻结了哪些列（如果有的）。
</td></tr><tr><td>
getsizes</td><td>

*字符串*</td><td>

返回一个字符串，指示自动计算文件夹大小选项的状态。返回的字符串将是 *default*、*on* 或 *off* 之一。
</td></tr><tr><td>
group_by</td><td>

*字符串*</td><td>
如果启用分组，返回按其分组列表的列名称。
</td></tr><tr><td>
group_combine</td><td>

*字符串*</td><td>

返回一个字符串，指示当前组合并模式。可能的值有 **normal**、**never** 和 **other**。
</td></tr><tr><td>
group_individual</td><td>

*bool*</td><td>

如果组合并模式设置为 **从不合并**，则返回 **True**。请注意，此选项已被弃用，您应该改用 **group_combine**。
</td></tr><tr><td>
group_reverse</td><td>

*bool*</td><td>

如果按相反的顺序对组进行排序，则返回 **True**。
</td></tr><tr><td>
hide_attr</td><td>

*对象:***[文件属性](fileattr.zh.md)**</td><td>

返回 **[文件属性](fileattr.zh.md)** 对象，指示隐藏的文件属性（设置了这些属性的任何项都将从显示中隐藏）。
</td></tr><tr><td>
hide_dirs</td><td>

*字符串*</td><td>
返回已从显示中隐藏的文件夹的通配符模式。
</td></tr><tr><td>
hide_dirs_regex</td><td>

*bool*</td><td>

如果当前 **hide_dirs** 模式使用正则表达式，则返回 **True**。
</td></tr><tr><td>
hide_ext</td><td>

*bool*</td><td>

如果隐藏文件名扩展名，则返回 **True**，如果显示文件名扩展名，则返回 **False**。
</td></tr><tr><td>
hide_files</td><td>

*字符串*</td><td>
返回已从显示中隐藏的文件的通配符模式。
</td></tr><tr><td>
hide_files_regex</td><td>

*bool*</td><td>

如果当前 **hide_files** 模式使用正则表达式，则返回 **True**。
</td></tr><tr><td>
hide_folder_attr</td><td>

*对象:***[文件属性](fileattr.zh.md)**  
或 *字符串*</td><td>

返回一个 **[文件属性](fileattr.zh.md)** 对象，指示隐藏的文件夹属性（设置了这些属性的任何文件夹都将从显示中隐藏）。如果禁用单独的文件夹属性过滤器，则此属性将返回字符串 **"off"**。
</td></tr><tr><td>
ignore_prefix</td><td>

*字符串*</td><td>
返回在对列表排序时忽略的文件名前缀。
</td></tr><tr><td>
locked</td><td>

*bool*</td><td>

如果标签中锁定文件夹格式，则返回 **True**。
</td></tr><tr><td>
manual_sort</td><td>

*bool*</td><td>

如果启用 [手动排序](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.zh.md)，则返回 **True**。
</td></tr><tr><td>
manual_sort_name</td><td>

*字符串*</td><td>
如果启用手动排序，返回当前排序顺序的名称（如果有）。
</td></tr><tr><td>
manual_sort_order</td><td>

*对象:***[排序顺序](sortorder.zh.md)**</td><td>

如果启用手动排序，返回一个 **[排序顺序](sortorder.zh.md)** 对象，用于查询和更改排序顺序。
</td></tr><tr><td>
mix_type</td><td>

*字符串*</td><td>

返回一个字符串，指示当前文件/文件夹混合类型。返回的字符串将是 *mixed*、*files*（先列出文件）或 *dirs*（先列出文件夹）之一。
</td></tr><tr><td>
name_ext</td><td>

*bool*</td><td>

如果文件名和扩展名是单独排序，则返回 **True**。
</td></tr><tr><td>
numeric_name</td><td>

*bool*</td><td>

如果启用数字名称排序，则返回 **True**。
</td></tr><tr><td>
reverse_sort</td><td>

*bool*</td><td>

如果整体排序顺序被颠倒，则返回 **True**。
</td></tr><tr><td>
show_attr</td><td>

*对象:***[文件属性](fileattr.zh.md)**</td><td>

返回 **[文件属性](fileattr.zh.md)** 对象，指示显示的文件属性（只有设置了这些属性的项才会在显示中显示）。
</td></tr><tr><td>
show_dirs</td><td>

*字符串*</td><td>
返回显示的文件夹的通配符模式（仅匹配此模式的文件夹才会显示）。
</td></tr><tr><td>
show_dirs_regex</td><td>

*bool*</td><td>

如果当前 **show_dirs** 模式使用正则表达式，则返回 **True**。
</td></tr><tr><td>
show_files</td><td>

*字符串*</td><td>
返回显示的文件的通配符模式。
</td></tr><tr><td>
show_files_regex</td><td>

*bool*</td><td>

如果当前 **show_files** 模式使用正则表达式，则返回 **True**。
</td></tr><tr><td>
show_folder_attr</td><td>

*对象:***[文件属性](fileattr.zh.md)**  
or *字符串*</td><td>

返回一个 **[文件属性](fileattr.zh.md)** 对象，指示显示的文件夹属性（只有设置了这些属性的文件夹才会在显示中显示）。如果禁用单独的文件夹属性过滤器，则此属性将返回字符串 **"off"**。
</td></tr><tr><td>
sort_ext</td><td>

*bool*</td><td>

如果名称列按文件名扩展名而非文件名排序，则返回 **True**。
</td></tr><tr><td>
sort_field</td><td>

*对象:***[列](column.zh.md)**</td><td>

返回代表当前排序字段的 **[列](column.zh.md)** 对象。
</td></tr><tr><td>
thumb_size</td><td>

*int*</td><td>
返回自定义缩略图大小，如果没有设置自定义大小，则返回 0。
</td></tr><tr><td>
thumb_stretch</td><td>

*字符串*</td><td>

如果格式覆盖全局缩略图拉伸模式，则返回 *FitReduce*、*FitSmooth*、*FitPixelated*、*FillCropSmooth* 或 *FillCropPixelated* 之一。否则，返回 *none*。
</td></tr><tr><td>
view</td><td>

*字符串*</td><td>

返回当前 [视图模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 的字符串形式。返回的字符串将是 *large*\_*icons*、*small*\_*icons*、*list*、*details*、*power*、*thumbnails* 或 *tile* 之一。
</td></tr><tr><td>
word_sort</td><td>

*bool*</td><td>

如果启用词语排序，则返回 **True**。
<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

脚本第一次访问特定 **Format** 对象时，将会对该标签的格式进行快照。如果脚本随后对该标签进行更改（例如，更改排序字段等），这些更改将不会反映在对象中。若要重新将该对象与该标签同步，请调用 **Format.Update** 方法。
</td></tr></tbody>
</table>