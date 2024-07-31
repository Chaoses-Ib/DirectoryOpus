# GlobalFilters

**GlobalFilters** 对象提供关于全局文件和文件夹过滤器设置的信息（在 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面上的配置中配置）。它从 **[DOpus](dopus.zh.md)**.filters 属性获取。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
enable</td><td>

*bool*</td><td>

如果全局通配符过滤器已启用，则返回 **True**。
</td></tr><tr><td>
file</td><td>

*string*</td><td>

返回全局文件名过滤器通配符模式。如果通配符配置为使用正则表达式，它将在模式前面带有 **regex:** 前缀。
</td></tr><tr><td>
folder</td><td>

*string*</td><td>

返回全局文件夹过滤器通配符模式。如果通配符配置为使用正则表达式，它将在模式前面带有 **regex:** 前缀。
</td></tr><tr><td>
hidehidden</td><td>

*bool*</td><td>

如果全局隐藏隐藏文件的选项已开启，则返回 **True**。
</td></tr><tr><td>
hidesystem</td><td>

*bool*</td><td>

如果全局隐藏操作系统文件的选项已开启，则返回 **True**。
</td></tr></tbody>
</table>