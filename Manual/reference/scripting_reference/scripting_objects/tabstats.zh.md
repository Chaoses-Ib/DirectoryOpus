# TabStats

**TabStats** 对象提供了关于当前标签中显示的文件夹的各种信息和统计数据。请注意，**[Tab](tab.zh.md)** 对象提供了此对象的两个版本。**Tab.selstats** 会考虑 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)，在这种模式下，“checked” 和“selected” 属性的值将相同。如果对象是通过 **Tab.stats** 获取的，并且文件列表处于复选框模式，则这两组属性将不同。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
bigimage_h</td><td>

*int*</td><td>
返回文件夹中最大图像的宽度（以像素为单位）。
</td></tr><tr><td>
bigimage_w</td><td>

*int*</td><td>
返回文件夹中最大图像的高度（以像素为单位）。
</td></tr><tr><td>
bytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回文件夹中的总字节数。
</td></tr><tr><td>
checkbox_mode</td><td>

*bool*</td><td>

如果标签当前处于 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)，则返回 **True**。
</td></tr><tr><td>
checkedbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回已选中项的总字节数。
</td></tr><tr><td>
checkeddirbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回已选中文件夹的总字节数。
</td></tr><tr><td>
checkeddirs</td><td>

*int*</td><td>
返回已选中文件夹的总数。
</td></tr><tr><td>
checkedfilebytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回已选中文件的总字节数。
</td></tr><tr><td>
checkedfiles</td><td>

*int*</td><td>
返回已选中文件的总数。
</td></tr><tr><td>
checkeditems</td><td>

*int*</td><td>
返回已选中项的总数。
</td></tr><tr><td>
checkedmusiclength</td><td>

*int*</td><td>
返回所有已选中音乐文件的总时长（以秒为单位）。
</td></tr><tr><td>
dirbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回所有文件夹的总字节数。
</td></tr><tr><td>
dirs</td><td>

*int*</td><td>
返回文件夹的总数。
</td></tr><tr><td>
filebytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回所有文件的总字节数。
</td></tr><tr><td>
filedate_max</td><td>

*date*</td><td>
返回文件夹中最新的（最近的）文件日期。
</td></tr><tr><td>
filedate_min</td><td>

*date*</td><td>
返回文件夹中最早的（最旧的）文件日期。
</td></tr><tr><td>
files</td><td>

*int*</td><td>
返回文件的总数。
</td></tr><tr><td>
items</td><td>

*int*</td><td>
返回项目的总数。
</td></tr><tr><td>
largestfile</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回文件夹中最大文件的尺寸。
</td></tr><tr><td>
musiclength</td><td>

*int*</td><td>
返回所有音乐文件的总时长（以秒为单位）。
</td></tr><tr><td>
selbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回所有选中项的总字节数。
</td></tr><tr><td>
seldirbytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回所有选中文件夹的总字节数。
</td></tr><tr><td>
seldirs</td><td>

*int*</td><td>
返回选中文件夹的数量。
</td></tr><tr><td>
selfilebytes</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

以 **[FileSize](filesize.zh.md)** 对象的形式返回所有选中文件的总字节数。
</td></tr><tr><td>
selfiles</td><td>

*int*</td><td>
返回选中文件数量。
</td></tr><tr><td>
selitems</td><td>

*int*</td><td>
返回选中项的数量。
</td></tr><tr><td>
selmusiclength</td><td>

*int*</td><td>
返回所有选中音乐文件的总时长（以秒为单位）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

当脚本第一次访问某个 **TabStats** 对象时，会拍摄标签状态的快照。如果脚本随后对该标签进行了更改（例如，选择文件、创建新文件夹等），这些更改将不会反映在对象中。要使对象与标签重新同步，请调用 **TabStats.Update** 方法。
</td></tr></tbody>
</table>