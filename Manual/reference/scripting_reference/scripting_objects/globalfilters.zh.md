# GlobalFilters**

**GlobalFilters** 对象提供有关全局文件和文件夹过滤器设置（在“**[过滤](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)**”配置页面上配置）的信息。它从 **[DOpus](dopus.zh.md)**.filters 属性获取。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
enable</td><td>

*bool*</td><td>

如果启用全局通配符过滤器，则返回 **True**。
</td></tr><tr><td>
file</td><td>

*string*</td><td>

返回全局文件名过滤器通配符模式。如果将通配符配置为使用正则表达式，则该模式前面会带有一个 **regex:** 前缀。
</td></tr><tr><td>
folder</td><td>

*string*</td><td>

返回全局文件夹过滤器通配符模式。如果将通配符配置为使用正则表达式，则该模式前面会带有一个 **regex:** 前缀。
</td></tr><tr><td>
hidehidden</td><td>

*bool*</td><td>

如果处于隐藏隐藏文件全局选项的状态为启用，则返回 **True**。
</td></tr><tr><td>
hidesystem</td><td>

*bool*</td><td>

如果处于隐藏操作系统文件的全局选项的状态为启用，则返回 **True**。
</td></tr></tbody>
</table>