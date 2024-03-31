如果一个 [包含文件](/Manual/scripting/script_add-ins/include_files.zh.md) 实现可选的 **[oninitincludefile](../scripting_events/oninitincludefile.zh.md)** 事件，将 **IncludeFileInitData** 对象传递给它，让它提供其自身的信息。这完全是可选的；包含文件在没有此方法时也能正常工作，但是提供此方法可以提供说明、版权信息以及最低版本要求等信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
copyright</td><td>

*string*</td><td>
让你为包含文件提供版权信息。
</td></tr><tr><td>
desc</td><td>

*string*</td><td>
提供包含文件说明。
</td></tr><tr><td>
min_version</td><td>

*string*</td><td>
让你为包含文件指定的最小 Opus 版本。如果当前版本低于指定版本，包含文件将禁用。你可以仅指定主版本号（如“13”），或者指定主版本号和次要版本号（如“13.3”），或者指定特定测试版（如“13.3.1”代表 13.3 测试版 1）。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
为包含文件提供显示名称。
</td></tr><tr><td>
shared</td><td>

*bool*</td><td>

如果包含文件位于 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md) 中，将此属性设置为 **True** 可以让包含文件对包外的脚本可用。如果设置为 **False**，只有同包中的脚本才能包含它。
</td></tr><tr><td>
url</td><td>

*string*</td><td>
提供一个 URL，例如可用于链接到有关该包含文件的更多信息。
</td></tr><tr><td>
version</td><td>

*string*</td><td>
让你为包含文件提供版本号。
</td></tr></tbody>
</table>