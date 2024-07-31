# IncludeFileInitData

如果一个 [包含文件](/Manual/scripting/script_add-ins/include_files.zh.md) 实现了可选的 **[OnInitIncludeFile](../scripting_events/oninitincludefile.zh.md)** 事件，一个 **IncludeFileInitData** 对象会被传递给它，让它提供关于自身的信息。这完全是可选的；即使没有这个方法，包含文件也能正常工作，但提供它可以让你获得描述、版权信息和最小版本要求等信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
copyright</td><td>

*string*</td><td>
让你提供包含文件的版权信息。
</td></tr><tr><td>
desc</td><td>

*string*</td><td>
提供包含文件的描述。
</td></tr><tr><td>
min_version</td><td>

*string*</td><td>
让你指定包含文件返回的 Opus 的最小版本。如果当前版本小于指定的版本，则包含文件将被禁用。你可以只指定主版本（例如 "13"），主版本和次版本（例如 "13.3"）或特定 Beta 版本（例如 "13.3.1" 用于 13.3 Beta 1）。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
提供包含文件的显示名称。
</td></tr><tr><td>
shared</td><td>

*bool*</td><td>

如果包含文件在 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md) 中，将此属性设置为 **True** 将使包含文件可供包外脚本使用。如果设置为 **False**，则只有同一包中的脚本可以包含它。
</td></tr><tr><td>
url</td><td>

*string*</td><td>
提供一个 URL，例如，你可以用它链接到更多关于包含文件的信息。
</td></tr><tr><td>
version</td><td>

*string*</td><td>
让你提供包含文件的版本号。
</td></tr></tbody>
</table>