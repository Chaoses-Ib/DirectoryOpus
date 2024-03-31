# TabStats

**TabStats** 对象提供有关标签页中显示的当前文件夹的各种信息和统计信息。请注意，**[Tab](tab.zh.md)** 对象提供此对象的两个版本。**Tab.selstats** 考虑 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)，在此模式下，“已选中”和“已选定”属性的值相同。如果通过 **Tab.stats** 检索对象，并且文件列表处于复选框模式，则两组属性将不同。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
bigimage_h</td><td>

*int*</td><td>
返回文件夹中最大图像的宽度（像素）。
</td></tr><tr><td>
bigimage_w</td><td>

*int*</td><td>
返回文件夹中最大图像的高度（像素）。
</td></tr><tr><td>
bytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回文件夹中的总字节数。
</td></tr><tr><td>
checkbox_mode</td><td>

*bool*</td><td>

如果标签页当前处于 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)，则返回 **True**。
</td></tr><tr><td>
checkedbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回选中项中的总字节数。
</td></tr><tr><td>
checkeddirbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回选中文件夹中的总字节数。
</td></tr><tr><td>
checkeddirs</td><td>

*int*</td><td>
返回选中文件夹的总数。
</td></tr><tr><td>
checkedfilebytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回选中文件中的总字节数。
</td></tr><tr><td>
checkedfiles</td><td>

*int*</td><td>
返回选中文件的总数。
</td></tr><tr><td>
checkeditems</td><td>

*int*</td><td>
返回选中项的总数。
</td></tr><tr><td>
checkedmusiclength</td><td>

*int*</td><td>
返回所有选中音乐文件的总长度（秒）。
</td></tr><tr><td>
dirbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回所有文件夹中的总字节数。
</td></tr><tr><td>
dirs</td><td>

*int*</td><td>
返回文件夹的总数。
</td></tr><tr><td>
filebytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回所有文件中的总字节数。
</td></tr><tr><td>
filedate_max</td><td>

*date*</td><td>
返回文件夹中最新的（最近的）文件日期。
</td></tr><tr><td>
filedate_min</td><td>

*date*</td><td>
返回文件夹中最旧的（最早的）文件日期。
</td></tr><tr><td>
files</td><td>

*int*</td><td>
返回文件的总数。
</td></tr><tr><td>
items</td><td>

*int*</td><td>
返回项的总数。
</td></tr><tr><td>
largestfile</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回文件夹中最大文件的大小。
</td></tr><tr><td>
musiclength</td><td>

*int*</td><td>
返回所有音乐文件的总长度（秒）。
</td></tr><tr><td>
selbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回所有选定项中的总字节数。
</td></tr><tr><td>
seldirbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回所有选定文件夹中的总字节数。
</td></tr><tr><td>
seldirs</td><td>

*int*</td><td>
返回选定文件夹的数量。
</td></tr><tr><td>
selfilebytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象形式返回所有选定文件中的总字节数。
</td></tr><tr><td>
selfiles</td><td>

*int*</td><td>
返回选定文件的数量。
</td></tr><tr><td>
selitems</td><td>

*int*</td><td>
返回所选项目的数量。
</td></tr><tr><td>
selmusiclength</td><td>

*int*</td><td>
返回所有选定音乐文件的总长度（秒）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

当脚本首次访问特定 **TabStats** 对象时，会截取标签页状态的快照。如果脚本随后对该标签页进行了更改（例如，它选择了文件、创建了新文件夹等），对象不会反映这些更改。要重新同步对象与标签页，请调用 **TabStats.Update** 方法。
</td></tr></tbody>
</table>